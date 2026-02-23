import React, { useState } from 'react';
import { 
  Menu, X, Droplets, ShieldCheck, Car, Wind, 
  CheckCircle2, Instagram, Facebook, Phone, 
  ChevronDown, MessageCircle, Star 
} from 'lucide-react';

export default function App() {
  const [isMenuOpen, setIsMenuOpen] = useState(false);
  const [openFaq, setOpenFaq] = useState(null);

  const whatsappLink = "https://wa.me/5551998585571"; // 

  const services = [
    { title: "Remoção de Manchas", desc: "Tratamento especializado para manchas difíceis em diversos tecidos.", icon: <Droplets /> },
    { title: "Sofás & Poltronas", desc: "Higienização profunda que remove sujidade e devolve o aspecto de novo.", icon: <CheckCircle2 /> },
    { title: "Colchões", desc: "Eliminação total de ácaros e bactérias para um sono saudável.", icon: <ShieldCheck /> },
    { title: "Setor Automotivo", desc: "Limpeza detalhada de bancos e carpetes do seu veículo.", icon: <Car /> }
  ];

  const faqs = [
    { q: "Quanto tempo demora a secagem?", a: "Dependendo do tecido e da ventilação, leva entre 4 a 12 horas." },
    { q: "Os produtos são seguros para pets?", a: "Sim, utilizamos produtos biodegradáveis e atóxicos, seguros para crianças e animais." },
    { q: "Vocês atendem em domicílio?", a: "Sim! Levamos toda a nossa estrutura profissional até o conforto da sua casa." }
  ];

  const testimonials = [
    { name: "Mariana Silva", text: "Meu sofá parecia novo de novo! O serviço de remoção de manchas foi impecável.", stars: 5 },
    { name: "João Pedro", text: "Excelente atendimento. O processo de oxi-sanitização tirou todo o cheiro de mofo.", stars: 5 }
  ];

  return (
    <div className="min-h-screen bg-slate-50 font-sans text-slate-900 scroll-smooth">
      {/* Navigation */}
      <nav className="fixed w-full z-50 bg-white/95 backdrop-blur-md border-b border-slate-200">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between h-20 items-center">
            <div className="flex items-center gap-2">
              {/*<img width="2000" height="2000" alt="Design sem nome (1)" src="https://github.com/user-attachments/assets/c85a45a2-c720-4bc4-bd8d-7fbd9543519b" />
*/}
              <div className="h-12 w-12 bg-blue-600 rounded-lg flex items-center justify-center text-white font-bold text-xl">
                CC
              </div>
              <span className="text-xl font-black tracking-tighter text-blue-700 uppercase">
                Higienizações
              </span>
            </div>
            
            <div className="hidden md:flex items-center space-x-8">
              <a href="#inicio" className="text-sm font-semibold hover:text-blue-600 transition">Início</a>
              <a href="#servicos" className="text-sm font-semibold hover:text-blue-600 transition">Serviços</a>
              <a href="#resultados" className="text-sm font-semibold hover:text-blue-600 transition">Resultados</a>
              <a href={whatsappLink} className="bg-blue-600 text-white px-6 py-2.5 rounded-full text-sm font-bold hover:bg-blue-700 transition flex items-center gap-2">
                <MessageCircle size={18} /> Orçamento Grátis
              </a>
            </div>

            <div className="md:hidden">
              <button onClick={() => setIsMenuOpen(!isMenuOpen)} className="p-2 text-slate-600">
                {isMenuOpen ? <X /> : <Menu />}
              </button>
            </div>
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <section id="inicio" className="pt-32 pb-20 lg:pt-48 lg:pb-32 px-4 bg-gradient-to-br from-slate-900 via-blue-900 to-blue-800 text-white relative">
        <div className="max-w-7xl mx-auto flex flex-col lg:flex-row items-center gap-12">
          <div className="lg:w-1/2 text-center lg:text-left">
            <span className="bg-blue-500/20 border border-blue-400/30 px-4 py-2 rounded-full text-blue-200 text-xs font-bold mb-6 inline-block uppercase tracking-widest">
              Especialistas em Limpeza Profissional
            </span>
            <h1 className="text-4xl md:text-6xl font-extrabold leading-tight mb-6">
              Dê uma vida nova aos seus <span className="text-blue-400">estofados.</span>
            </h1>
            <p className="text-lg text-blue-100/80 mb-10 max-w-xl">
              Higienização profunda, impermeabilização e esterilização com Ozônio. Sua casa livre de ácaros e bactérias.
            </p>
            <div className="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
              <a href={whatsappLink} className="bg-blue-500 hover:bg-blue-600 text-white px-8 py-4 rounded-xl font-bold flex items-center justify-center gap-3 transition shadow-lg">
                <Phone size={20} /> Falar com Especialista
              </a>
            </div>
          </div>
          <div className="lg:w-1/2 relative">
             <div className="aspect-video bg-slate-800/50 rounded-3xl border border-white/10 overflow-hidden flex items-center justify-center">
                {/* Imagem de um sofá limpo aqui */}
                <div className="text-blue-400/30 font-black text-6xl">ANTES & DEPOIS</div>
             </div>
          </div>
        </div>
      </section>

      {/* Services Grid */}
      <section id="servicos" className="py-24 px-4 max-w-7xl mx-auto">
        <h2 className="text-3xl md:text-5xl font-black text-center mb-16">Soluções Completas</h2>
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
          {services.map((s, idx) => (
            <div key={idx} className="bg-white p-8 rounded-3xl border border-slate-100 shadow-sm hover:shadow-xl transition duration-300">
              <div className="w-14 h-14 bg-blue-50 text-blue-600 rounded-2xl flex items-center justify-center mb-6">
                {React.cloneElement(s.icon, { size: 28 })}
              </div>
              <h3 className="text-xl font-bold mb-3">{s.title}</h3>
              <p className="text-slate-500 text-sm">{s.desc}</p>
            </div>
          ))}
        </div>
      </section>

      {/* FAQ & Results */}
      <section id="resultados" className="py-24 px-4 bg-slate-100">
        <div className="max-w-7xl mx-auto grid grid-cols-1 lg:grid-cols-2 gap-16">
          
          {/* FAQ Accordion */}
          <div>
            <h2 className="text-3xl font-black mb-8">Dúvidas Frequentes</h2>
            <div className="space-y-4">
              {faqs.map((f, i) => (
                <div key={i} className="bg-white rounded-2xl border border-slate-200 overflow-hidden">
                  <button 
                    onClick={() => setOpenFaq(openFaq === i ? null : i)}
                    className="w-full p-5 text-left flex justify-between items-center font-bold"
                  >
                    {f.q} <ChevronDown className={`transition-transform ${openFaq === i ? 'rotate-180' : ''}`} />
                  </button>
                  {openFaq === i && <div className="p-5 pt-0 text-slate-600 border-t border-slate-50">{f.a}</div>}
                </div>
              ))}
            </div>
          </div>

          {/* Testimonials */}
          <div className="bg-blue-600 rounded-[2.5rem] p-10 text-white relative overflow-hidden">
            <h2 className="text-3xl font-black mb-8 relative z-10">O que nossos clientes dizem</h2>
            <div className="space-y-6 relative z-10">
              {testimonials.map((t, i) => (
                <div key={i} className="bg-white/10 backdrop-blur-md p-6 rounded-2xl border border-white/10">
                  <div className="flex text-yellow-400 mb-3">
                    {[...Array(t.stars)].map((_, s) => <Star key={s} size={16} fill="currentColor" />)}
                  </div>
                  <p className="italic mb-4">"{t.text}"</p>
                  <p className="font-bold text-blue-200">— {t.name}</p>
                </div>
              ))}
            </div>
            <div className="absolute -bottom-10 -right-10 text-9xl font-black text-white/10">"</div>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-slate-900 text-white py-12 px-4 text-center">
        <div className="max-w-7xl mx-auto">
          <div className="flex flex-col items-center gap-6">
             <div className="flex items-center gap-2">
                <div className="h-8 w-8 bg-blue-600 rounded flex items-center justify-center font-bold">CC</div>
                <span className="font-black text-xl uppercase">Higienizações</span>
             </div>
             <div className="flex gap-4">
                <Instagram className="cursor-pointer hover:text-blue-400" />
                <Facebook className="cursor-pointer hover:text-blue-400" />
             </div>
             <p className="text-slate-500 text-sm">© {new Date().getFullYear()} CC Clean. Todos os direitos reservados.</p>
          </div>
        </div>
      </footer>
    </div>
  );
}
