# Especificacao de Layout — Funil Medicos | Victor Viana

**Identidade Visual (Global)**
- **Fontes:** Fraunces (Headings, serif, italic accent) + Outfit (Body, sans-serif)
- **Paleta:**
  - Background: `#FBFAF9`
  - Dark/Slate: `#0F172A`
  - Text Main: `#1A1A1A`
  - Text Muted: `#52525B`
  - Accent: `#4F46E5`
  - Accent Light: `#818CF8`
  - Border: `#E5E7EB`
  - Success: `#10b981`
  - Error: `#ef4444`
- **Estetica Core:** Anthropic Minimalism + Hyros Tech. Noise texture overlay, serif italic accents, glassmorphism sutil, hover lift.
- **Efeito Global:** `.noise::after` com `natural-paper.png`, `opacity: 0.15`, `pointer-events: none`, `z-index: 9999`, `position: fixed`.

---

## Secao 1: Hero

### Arquetipo e Constraints
- **Arquetipo:** Split Assimetrico (60/40)
- **Constraints:** Noise Texture (Efeitos), Serif Italic Accent (Tipografia), Perspective Transform (Layout), Float Loop (Movimento)
- **Justificativa:** O split assimetrico prioriza a copy (lado esquerdo) enquanto a foto com perspectiva 3D cria profundidade e sofisticacao. Os floating cards simulam um sistema ativo, reforçando a promessa de automacao.

### Conteudo
- **Badge:** "Para Medicos Especialistas" com status dot pulsante
- **Headline:** Medico especialista: sua autoridade ja esta *construida.*
- **Subheadline:** Eu transformo ela em um sistema de vendas que funciona sem voce precisar produzir conteudo todos os dias. Eu crio o seu infoproduto, monto o funil completo e coloco para rodar. Voce entra com o conhecimento. O resto e comigo.
- **CTA:** Quero entender como funciona
- **Assinatura:** Victor Viana — Estrategista digital para medicos

### Layout
- `min-height: 85vh`, `display: flex`, `align-items: center`, `padding: 4rem 0 3rem`.
- Grid: `grid-template-columns: 1.2fr 1fr`, `gap: 4rem`, `align-items: center`.
- Lado esquerdo: badge, headline, subheadline, CTA, assinatura em stack vertical, `max-width: 600px`.
- Lado direito: foto com frame em perspectiva + 2 floating cards posicionados absolutamente.

### Tipografia
- **Badge:** Outfit, `font-size: 0.75rem`, `font-weight: 500`, `letter-spacing: 0.5px`, `text-transform: uppercase`, color `#52525B`.
- **Headline:** Fraunces, `font-size: clamp(2.5rem, 5vw, 4rem)`, `font-weight: 500`, `line-height: 1.1`, `letter-spacing: -2px`, color `#1A1A1A`. Palavra "construida" em `font-style: italic`, `color: #4F46E5`.
- **Subheadline:** Outfit, `font-size: 1.2rem`, `line-height: 1.7`, color `#52525B`, `max-width: 500px`.
- **CTA:** Outfit, `font-size: 1.1rem`, `font-weight: 600`.
- **Assinatura:** Outfit, `font-size: 0.85rem`, color `#52525B`, `letter-spacing: 0.5px`, `margin-top: 1.5rem`.

### Cores
- Fundo: `#FBFAF9` com noise texture overlay global.
- Badge: `background: white`, `border: 1px solid #E5E7EB`, `border-radius: 50px`. Status dot: `background: #4F46E5`, `box-shadow: 0 0 10px #4F46E5`.
- CTA: `background: #1A1A1A`, `color: white`, `box-shadow: 0 10px 20px -5px rgba(0,0,0,0.1)`.
- CTA hover: `transform: translateY(-2px)`, `box-shadow: 0 15px 30px -10px rgba(0,0,0,0.2)`.

### Elementos Visuais
- **Foto:** `border-radius: 16px`, `overflow: hidden`, `box-shadow: 0 40px 80px -20px rgba(0,0,0,0.15)`. `transform: perspective(1000px) rotateY(-3deg)`. Hover: `rotateY(0deg)`, `transition: 0.5s`. `filter: contrast(1.05)`.
- **Float Card A (esquerda-baixo):** `bottom: -20px`, `left: -30px`. Background white, `border: 1px solid #E5E7EB`, `border-radius: 12px`, `padding: 1rem 1.25rem`, `box-shadow: 0 20px 40px -10px rgba(0,0,0,0.1)`. Conteudo: "Operacao / Funil Completo / ✓ Vendas automaticas".
- **Float Card B (direita-cima):** `top: 20px`, `right: -20px`. Mesmo estilo. Conteudo: "CFM / 100% Etico / Normas respeitadas".
- **Animacao Float:** `@keyframes float-slow { 0%,100% { translateY(0) } 50% { translateY(-8px) } }`, `duration: 5s`, `ease-in-out`, `infinite`. Card B: `animation-delay: -2s`.

### Responsividade
- `<992px`: Grid empilha `1fr`. Texto `order: 1`, visual `order: 2`, `max-width: 400px`, `margin: 0 auto`. Subheadline centralizada. Float cards `display: none`.
- `<768px`: Headline `font-size: 2.25rem`, `letter-spacing: -1px`.

---

## Secao 2: Quem Ja Confiou (Clientes)

### Arquetipo e Constraints
- **Arquetipo:** Editorial List + Sticky Sidebar
- **Constraints:** Hover Slide (Interacao), Stagger Reveal (Movimento), Perspective Card (Layout)
- **Justificativa:** A lista editorial com linhas separadas por borda fina cria elegancia de revista. O hover slide (padding-left animado) convida a exploracao. A sidebar sticky com cards mantém o contexto emocional (erro vs acerto) visivel enquanto o usuario percorre a lista.

### Conteudo
- **Titulo:** Medicos que confiam *no meu trabalho.*
- **Clientes (7):** Cada um com nome, descricao e seguidores
- **Selo CFM:** imagem resultado-cfm.png
- **Card Foto:** victor-premiacao.png
- **Card Erro:** O Erro Comum — Tentar fazer tudo sozinho depois do plantao...
- **Card Acerto:** O Caminho Certo — Delegar para quem ja fez isso antes...

### Layout
- `padding: var(--section-py) 0`, `background: white`, `border-top: 1px solid #E5E7EB`.
- Titulo: largura total, `margin-bottom: 3rem`.
- Grid: `grid-template-columns: 1.1fr 0.9fr`, `gap: 5rem`, `align-items: start`.
- Esquerda: lista de clientes + selo CFM.
- Direita: `.cards-stack` com `position: sticky`, `top: 100px`. Card foto + card erro + card acerto em stack vertical `gap: 1.5rem`.

### Tipografia
- **Titulo:** Fraunces, `clamp(2rem, 4vw, 3.5rem)`, `line-height: 1.1`, `letter-spacing: -1.5px`. "no meu trabalho." em `font-style: italic`, `color: #4F46E5`.
- **Client Name:** Outfit, `font-weight: 700`, `color: #1A1A1A`.
- **Client Desc:** Outfit, `font-size: 0.9rem`, `color: #52525B`.
- **Client Followers:** Outfit, `font-size: 0.8rem`, `font-weight: 500`, `color: #52525B`, `white-space: nowrap`, alinhado a direita com `margin-left: auto`.
- **Card h3:** Fraunces, `font-size: 1.35rem`, `letter-spacing: -0.5px`.
- **Card p:** Outfit, `font-size: 0.95rem`, `line-height: 1.6`, `color: #52525B`.

### Cores
- Fundo secao: `white`.
- Client item: `padding: 1.25rem 0`, `border-bottom: 1px solid #E5E7EB`. First child: `border-top` tambem.
- Client item hover: `padding-left: 1rem`, `background: linear-gradient(90deg, rgba(79,70,229,0.03), transparent)`, `transition: 0.3s ease`.
- Icone check: `color: #4F46E5`, `font-size: 1.25rem`.
- Card Erro: `border: 1px solid rgba(239,68,68,0.2)`, `background: #FBFAF9`. Icon: `background: rgba(239,68,68,0.1)`, `color: #ef4444`.
- Card Acerto: `background: #1A1A1A`, `color: white`, `border: none`. Texto p: `color: #94A3B8`. Icon: `background: rgba(79,70,229,0.2)`, `color: #818CF8`.

### Elementos Visuais
- **Card Foto:** `padding: 0`, `overflow: hidden`, `border: none`, `border-radius: 16px`. Img: `filter: contrast(1.05)`. Hover: img `transform: scale(1.03)`, `transition: 0.6s cubic-bezier(0.16, 1, 0.3, 1)`.
- **Selo CFM:** `max-width: 200px`, `opacity: 0.7`. Hover: `opacity: 1`, `transition: 0.3s`.

### Animacoes
- Titulo: `fade-up`, `800ms`.
- Client items: `fade-up` com stagger `50ms` entre cada (delays: 50, 100, 150, 200, 250, 300, 350).
- Cards direita: `fade-left` com stagger `100ms`.
- Selo CFM: `fade-up`, `delay: 400ms`.

### Interatividade
- Client item hover: `padding-left: 1rem` + gradient background. `transition: all 0.3s ease`.
- Cards hover: `transform: translateY(-4px)`, `box-shadow: 0 20px 40px rgba(0,0,0,0.06)`, `transition: 0.4s cubic-bezier(0.16, 1, 0.3, 1)`.
- Card foto hover: img `scale(1.03)`.

### Responsividade
- `<992px`: Grid empilha `1fr`, `gap: 3rem`. Cards-stack `position: static`. Client-followers `display: none`.
- `<768px`: Titulo `font-size: 1.75rem`.

---

## Secao 3: O Que Eu Construo

### Arquetipo e Constraints
- **Arquetipo:** Bento Box Assimetrico
- **Constraints:** Hover Lift (Interacao), Stagger Fade-up (Movimento), Glassmorphism sutil (Efeitos)
- **Justificativa:** O bento box quebra a monotonia de cards iguais — celulas de tamanhos variados criam ritmo visual e hierarquia. Os cards largos (Landing Pages e Automacao) recebem destaque por serem os servicos mais impactantes.

### Conteudo
- **Titulo:** O que eu construo *para voce.*
- **Subtitulo:** Cada peca do seu sistema digital e criada com um unico objetivo: vender enquanto voce atende.
- **Card 1 (1col):** Copy persuasiva e etica — Totalmente alinhada com as normas do CFM.
- **Card 2 (2col):** Landing Pages de Alta Conversao — Design premium que gera confianca instantanea em cada clique.
- **Card 3 (2col):** Automacao completa — Paginas, VSL e WhatsApp integrados, trabalhando por voce enquanto voce atende.
- **Card 4 (1col):** Trafego focado — Anuncios validados para trazer apenas pessoas altamente qualificadas.

### Layout
- `padding: var(--section-py) 0`, `background: #FBFAF9`.
- Header centralizado, `max-width: 700px`, `margin: 0 auto`.
- Bento grid: `grid-template-columns: repeat(3, 1fr)`, `gap: 1.25rem`, `margin-top: 3rem`.
- Card 1: `span 1`. Card 2: `span 2`. Card 3: `span 2`. Card 4: `span 1`.

### Tipografia
- **Titulo:** Fraunces, `clamp(2rem, 4vw, 3.5rem)`, `letter-spacing: -1.5px`. "para voce." em italic `#4F46E5`.
- **Subtitulo:** Outfit, `font-size: 1.15rem`, `color: #52525B`, `max-width: 700px`.
- **Card h3:** Fraunces, `font-size: 1.25rem`, `letter-spacing: -0.5px`.
- **Card p:** Outfit, `font-size: 0.95rem`, `color: #52525B`.

### Cores
- Cards: `background: white`, `border: 1px solid #E5E7EB`, `border-radius: 12px`, `padding: 2rem`.
- Icones: `color: #4F46E5`, `font-size: 1.5rem`, `margin-bottom: 1rem`.
- Hover: `box-shadow: 0 20px 40px rgba(0,0,0,0.05)`.

### Animacoes
- Header: `fade-up`, `800ms`.
- Cards: `fade-up` stagger `50ms` (delays: 50, 100, 150, 200).

### Interatividade
- Card hover: `transform: translateY(-5px)`, `box-shadow: 0 20px 40px rgba(0,0,0,0.05)`, `transition: 0.4s cubic-bezier(0.16, 1, 0.3, 1)`.

### Responsividade
- `<992px`: Grid `repeat(2, 1fr)`. Cards largos `span 2`.
- `<768px`: Grid `1fr`. Todos `span 1`.

---

## Secao 4: Para Quem E

### Arquetipo e Constraints
- **Arquetipo:** Grid Modular 2x2
- **Constraints:** Hover Background Shift (Interacao), Fade-up Stagger (Movimento)
- **Justificativa:** Grid 2x2 limpo e simetrico para 4 criterios — cada panel com icone + texto curto. O hover sutil muda o background para criar feedback visual elegante sem poluicao.

### Conteudo
- **Titulo:** Isso e para voce *se...*
- **Item 1:** Voce e medico especialista e quer criar e vender o seu infoproduto
- **Item 2:** Nao tem tempo de aprender marketing, trafego e ferramentas digitais
- **Item 3:** Quer que alguem cuide de tudo, do produto ate as vendas
- **Item 4:** Quer criar uma renda que nao depende da sua agenda de atendimentos

### Layout
- `padding: var(--section-py) 0`, `background: white`, `border-top: 1px solid #E5E7EB`.
- Titulo centralizado.
- Grid: `grid-template-columns: 1fr 1fr`, `gap: 1.5rem`, `margin-top: 3rem`.
- Cada panel: `display: flex`, `align-items: flex-start`, `gap: 1rem`, `padding: 2rem`.

### Tipografia
- **Titulo:** Fraunces, `clamp(2rem, 4vw, 3.5rem)`. "se..." em italic `#4F46E5`.
- **Panel text:** Outfit, `font-size: 1.1rem`, `color: #1A1A1A`, `line-height: 1.5`.

### Cores
- Panels: `background: #FBFAF9`, `border-radius: 12px`, `border: 1px solid #E5E7EB`.
- Panel hover: `background: #F1F5F9`, `transform: translateY(-2px)`, `transition: 0.3s`.
- Icones: `color: #4F46E5`, `font-size: 1.5rem`.

### Animacoes
- Titulo: `fade-up`, `800ms`.
- Panels: `fade-up` stagger `50ms` (delays: 50, 100, 150, 200).

### Responsividade
- `<992px`: Grid `1fr`.

---

## Secao 5: Sobre Victor Viana

### Arquetipo e Constraints
- **Arquetipo:** Split Assimetrico com Galeria Empilhada
- **Constraints:** Dark Mode (Cor), Overlapping Images (Layout), Clip Reveal (Movimento), Monospace Meta (Tipografia)
- **Justificativa:** Fundo escuro cria ruptura visual dramatica. A galeria com duas fotos sobrepostas (main + secondary com offset) lembra portfolio de diretor criativo. O meta-data monospace adiciona DNA tech, alinhando com a identidade Hyros.

### Conteudo
- **Badge:** "Quem sou eu" com status dot
- **Meta:** // VICTOR_VIANA
- **Nome:** Victor Viana
- **Credencial 1:** Mais de 6 anos em projetos digitais no mercado da saude — participei de operacoes que somam mais de R$10 milhoes em vendas
- **Credencial 2:** Pos-graduado em Administracao pela FGV

### Layout
- `padding: var(--section-py) 0`, `background: #0F172A`, `color: white`, `overflow: hidden`.
- Grid: `grid-template-columns: 0.8fr 1.2fr`, `gap: 5rem`, `align-items: center`.
- Esquerda: galeria com `position: relative`, `min-height: 450px`.
- Direita: badge + border-left accent + meta + titulo + lista de credenciais.

### Tipografia
- **Meta:** JetBrains Mono, `font-size: 0.75rem`, `color: #818CF8`, `letter-spacing: 2px`.
- **Nome:** Fraunces, `clamp(2rem, 4vw, 3.5rem)`, `color: white`.
- **Credenciais:** Outfit, `font-size: 1rem`, `color: #CBD5E1`, `line-height: 1.6`.

### Cores
- Fundo: `#0F172A`.
- Border left accent: `4px solid #4F46E5`.
- Badge dark: `background: rgba(255,255,255,0.05)`, `border: 1px solid rgba(255,255,255,0.1)`, `color: #94A3B8`.
- Icones credenciais: `color: #818CF8`.

### Elementos Visuais
- **Main img:** `width: 280px`, `height: 370px`, `top: 0`, `left: 10%`, `z-index: 2`. `border-radius: 16px`, `box-shadow: 0 30px 60px rgba(0,0,0,0.4)`, `border: 1px solid rgba(255,255,255,0.1)`.
- **Secondary img:** `width: 220px`, `height: 220px`, `bottom: 0`, `right: 0`, `z-index: 3`. `border-color: rgba(79,70,229,0.3)`.
- Ambas: hover img `transform: scale(1.05)`, `transition: 0.6s cubic-bezier(0.16, 1, 0.3, 1)`.

### Animacoes
- Main img: `fade-right`, `800ms`.
- Secondary img: `fade-up`, `delay: 200ms`.
- Badge + texto: `fade-left` com stagger `100ms`.

### Responsividade
- `<992px`: Grid `1fr`, `gap: 3rem`. Galeria `max-width: 400px`, `margin: 0 auto`.
- `<768px`: Galeria `min-height: 300px`. Main img `220x300px`. Secondary `160x160px`.

---

## Secao 6: O Que Esta Incluido no Servico

### Arquetipo e Constraints
- **Arquetipo:** Modular Grid 3x2 com Container Narrow
- **Constraints:** Hover Lift (Interacao), Stagger Reveal (Movimento), Subtle Border Animation (Efeitos)
- **Justificativa:** Grid modular limpo de 6 servicos. Container narrow centralizado com titulo serif mantem a elegancia editorial. Hover lift nos cards com animacao sutil na borda cria feedback premium.

### Conteudo
- **Titulo:** O que esta incluido *no servico.*
- **Subtitulo:** Voce nao precisa contratar designer, redator, gestor de trafego ou tecnico de plataforma. Eu cuido de tudo:
- **Item 1:** Definicao do produto ideal — Para a sua especialidade e publico.
- **Item 2:** Copy completa — Pagina, anuncios.
- **Item 3:** Design de todas as pecas — Estetica premium e funcional.
- **Item 4:** Configuracao tecnica — Hotmart, dominio, pixel, etc.
- **Item 5:** Gestao de Anuncios — Criacao e gestao dos anuncios pagos.
- **Item 6:** Acompanhamento — Resultados e ajustes continuos.

### Layout
- `padding: var(--section-py) 0`, `background: #FBFAF9`.
- Header centralizado, `max-width: 700px`.
- Grid: `grid-template-columns: repeat(3, 1fr)`, `gap: 1.25rem`, `margin-top: 3rem`.
- Todos os cards `span 1` (grid uniforme 3x2).

### Tipografia
- **Titulo:** Fraunces, `clamp(2rem, 4vw, 3.5rem)`. "no servico." em italic `#4F46E5`.
- **Subtitulo:** Outfit, `font-size: 1.15rem`, `color: #52525B`.
- **Card h3:** Fraunces, `font-size: 1.25rem`, `letter-spacing: -0.5px`.
- **Card p:** Outfit, `font-size: 0.95rem`, `color: #52525B`.

### Cores
- Cards: `background: white`, `border: 1px solid #E5E7EB`, `border-radius: 12px`, `padding: 2rem`.
- Hover: `transform: translateY(-5px)`, `box-shadow: 0 20px 40px rgba(0,0,0,0.05)`, `border-color: rgba(79,70,229,0.3)`.

### Animacoes
- Header: `fade-up`, `800ms`.
- Cards: `fade-up` stagger `50ms` (delays: 0, 50, 100, 150, 200, 250).

### Interatividade
- Card hover: `translateY(-5px)` + shadow + `border-color: rgba(79,70,229,0.3)`, `transition: 0.4s cubic-bezier(0.16, 1, 0.3, 1)`.

### Responsividade
- `<992px`: Grid `repeat(2, 1fr)`.
- `<768px`: Grid `1fr`.

---

## Secao 7: Fotos Autoridade (Erico + Icaro)

### Arquetipo e Constraints
- **Arquetipo:** Gallery Wall (2 colunas)
- **Constraints:** Hover Scale (Interacao), Fade-up Stagger (Movimento)
- **Justificativa:** Duas fotos lado a lado, sem texto, sem titulo. A simplicidade maximiza o impacto visual — as fotos com Erico Rocha e Icaro de Carvalho falam por si. O hover scale sutil convida a atencao.

### Layout
- `padding: 3rem 0`.
- Grid: `grid-template-columns: 1fr 1fr`, `gap: 1.5rem`, `max-width: 700px`, `margin: 0 auto`.

### Elementos Visuais
- Fotos: `border-radius: 16px`, `box-shadow: 0 20px 40px rgba(0,0,0,0.08)`, `object-fit: cover`, `width: 100%`, `height: 100%`.
- Hover: `transform: scale(1.02)`, `transition: 0.4s`.

### Animacoes
- Foto 1: `fade-up`, `800ms`.
- Foto 2: `fade-up`, `delay: 100ms`.

### Responsividade
- `<768px`: Grid `1fr`, `max-width: 350px`.

---

## Secao 8: Fechamento e Formulario

### Arquetipo e Constraints
- **Arquetipo:** Contained Center (Focus Container)
- **Constraints:** Dark Mode (Cor), Glow Border (Efeitos), Serif Italic Accent (Tipografia)
- **Justificativa:** Fundo escuro cria epílogo cinematografico. Container estreito centralizado canaliza o olhar para o formulario. Borda com glow indigo sutil no form wrapper cria sensacao premium/tech.

### Conteudo
- **Titulo:** Quer entender se faz sentido *para o seu caso?*
- **Texto:** Preencha o formulario abaixo. E rapido. Vou analisar o seu perfil e, se fizer sentido trabalharmos juntos, eu mesmo entro em contato pelo WhatsApp para conversarmos.

### Layout
- `padding: var(--section-py) 0`, `background: #0F172A`, `color: white`.
- Container: `max-width: 800px`, `text-align: center`.
- Form wrapper: `max-width: 600px`, `margin: 3rem auto 0`.

### Tipografia
- **Titulo:** Fraunces, `clamp(2rem, 4vw, 3rem)`, `letter-spacing: -1.5px`, `color: white`. "para o seu caso?" em italic `#818CF8`.
- **Texto:** Outfit, `font-size: 1.2rem`, `color: #94A3B8`, `max-width: 600px`.

### Cores
- Fundo: `#0F172A`.
- Form wrapper: `background: #1E293B`, `border: 1px solid rgba(79,70,229,0.2)`, `border-radius: 20px`, `padding: 2.5rem`, `box-shadow: 0 0 50px rgba(79,70,229,0.1)`.
- Inputs: `background: rgba(255,255,255,0.05)`, `border: 1px solid rgba(255,255,255,0.1)`, `color: white`, `border-radius: 8px`.
- Input focus: `border-color: #4F46E5`, `box-shadow: 0 0 0 3px rgba(79,70,229,0.15)`.

### Animacoes
- Titulo: `fade-up`, `800ms`.
- Texto: `fade-up`, `delay: 100ms`.
- Form wrapper: `fade-up`, `delay: 200ms`.

### Responsividade
- Mobile: titulo `font-size: 1.75rem`. Form wrapper `padding: 1.5rem`.

---
