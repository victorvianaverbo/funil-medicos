# Especificação de Layout - Funil de Infoprodutos Médicos

**Identidade Visual (Global)**
- **Fontes:** Outfit (Headings/Botões) + Inter (Body). *Justificativa: Outfit traz modernidade geométrica, Inter garante máxima legibilidade corporativa, ideal para o nicho médico.*
- **Cores Principais:** 
  - Primary (Deep sky blue): `#0369a1`
  - Primary Light: `#0ea5e9`
  - Primary Dark: `#0c4a6e`
  - Accent (Teal): `#0d9488`
  - Accent Light: `#14b8a6`
  - Escuros/Texto: Main `#0f172a`, Muted `#475569`, Light `#94a3b8`
  - Fundo: Page `#f8fafc`, Surface `#ffffff`
- **Estética Core:** Clean, Glassmorphism, Premium Medical.

---

## Seção 1: Hero

### Arquétipo e Constraints
- **Arquétipo:** Split Assimétrico (Textos 55%, Visual Dashboard 45%)
- **Constraints:** Glassmorphism, Float Loop (animações levitando), Pulse/Ambient Motion (indicadores de status latejando)
- **Justificativa:** O dashboard lateral precisa transparecer tecnologia trabalhando sozinha, justificando as animações float/pulse.

### Conteúdo
- **Headline:** Médico, seu tempo clínico vale muito para você ainda lidar com "tecnologia e marketing".
- **Subheadline:** Em 21 dias eu te entrego o funil do seu infoproduto 100% no ar e faturando alto: copy, design, VSL e anúncios. Sem você apertar um botão e respeitando seu CRM.
- **CTA:** Quero delegar e faturar no digital

### Layout
- `min-height: 100vh`, `display: flex`, `align-items: center`.
- Container em grid `1fr 1fr`, `gap: 64px`.
- Padding topo/base: `120px 0 80px`.
- Lado esquerdo: Badge, Headline, Subheadline, CTA alinhados à esquerda em coluna.
- Lado direito: Visual englobando o "Dashboard" de fundo e painéis de vidro flutuando sobre ele.

### Tipografia
- **Headline:** Outfit, `font-weight: 800`, `font-size: clamp(2.5rem, 5vw, 3.5rem)`, `line-height: 1.1`, `letter-spacing: -1px`, Color: `#0f172a`.
- **Subheadline:** Inter, `font-weight: 400`, `font-size: 1.25rem`, `line-height: 1.6`, Color: `#475569`.
- **Badge:** Outfit, `font-weight: 600`, `font-size: 0.875rem`.

### Cores
- Fundo: `#f8fafc` com glows de background absolutos texturizados (`#0ea5e9` e `#14b8a6` com `blur(80px)` e `opacity: 0.4`).
- CTA: Background gradient `linear-gradient(135deg, #0369a1, #0ea5e9)`, Color: `#ffffff`, Box-shadow: `0 4px 14px 0 rgba(14, 165, 233, 0.39)`.

### Elementos Visuais
- **Dashboard Abstract:** Uma div central representando um sistema faturando. Background `#ffffff`, border `#e2e8f0`, com skeleton de gráficos.
- **Floating Cards:** Dois cards de vidro (Glassmorphism `rgba(255,255,255,0.9)`, `blur(8px)`) que exibem notificações ("Venda Realizada"). Ícones com fundo `#14b8a6`.
- **Pulse Dot:** Bolinha nativa sinalizando "Sistema Ativo" com animação de pulso verde (`#0d9488`).
- **Grid Overlay:** Background no fundo `background-image: linear-gradient(...)` para lembrar engenharia/tecnologia.

### Animações
- Floating cards: `animation: float 6s ease-in-out infinite`. Diferenciação de `animation-delay: 2s` para o segundo card.
- Pulse: `box-shadow` pulsando infinito de `0` a `10px` transparente rgba do green teal.
- Não usar entrada inicial no carregamento principal para evitar CLS imediato.

### Interatividade
- Botão CTA: `transform: translateY(-2px)` no hover, intensificando shadow.
- Cards flutuantes param sua animação (pause) no hover.

### Responsividade
- Tab (992px): Layout empilha (`grid-template-columns: 1fr`). Visual dashboard escala para o centro (`margin: 40px auto 0`). Flutuantes desaparecem ou simplificam.
- Mobile (768px): Padding `100px 0 60px`. Headline cai para `2.25rem`. Dashboard fica menor (`width: 90%`).

---

## Seção 2: O Problema

### Arquétipo e Constraints
- **Arquétipo:** Split Vertical (Conteúdo Texto E | Cards Visuais D)
- **Constraints:** Hover Slide (cards que se deslocam), Stagger (animações sequenciais ao entrar), Highlight Box
- **Justificativa:** Dividir o texto à esquerda (a dor emocional) dos cards lógicos à direita (o checklist do erro e o jeito certo) dá clareza. O hover nos cards atrai atenção para a transição do "erro" para a "solução".

### Conteúdo
- **Título:** Você domina a medicina. E a internet?
- **Parágrafo 1:** O maior erro dos médicos no digital é tentar aprender tráfego, design e copywriting depois de 12h de plantão.
- **Parágrafo 2:** Agências generalistas só fazem posts "bonitinhos" no Instagram, e não criam negócios de verdade com faturamento previsível.
- **Parágrafo 3:** O seu conhecimento salva vidas. O que falta é uma engenharia de vendas ética e validada por trás dele.

### Layout
- Padding: `100px 0`. Background: `#ffffff`.
- Grid: `grid-template-columns: 1fr 1fr`, `gap: 80px`, `align-items: center`.
- Esquerda: Textos em stack, e uma "highlight-box" (caixa de destaque) puxando o Parágrafo 3.
- Direita: Coluna com dois cards empilhados. Um "Problema" e um "Solução Correta".

### Tipografia
- **Título:** Outfit, `font-size: 2.5rem`, `line-height: 1.2`, Color: `#0f172a`.
- **Parágrafos:** Inter, `font-size: 1.125rem`, Color: `#475569`.
- **Textos dos Cards:** Outfit `1.25rem` no título, Inter `1rem` no texto interno.

### Cores
- Fundo da seção: `#ffffff`.
- Card Errado: Border `#e2e8f0`, ícone de erro background `#fee2e2` color `#ef4444`.
- Card Certo: Border `rgba(13, 148, 136, 0.2)`, ícone sucesso background `#ccfbf1` color `#0d9488`. Shadow base `0 10px 30px rgba(13, 148, 136, 0.05)`.
- Highlight Box (Esquerda): BG `rgba(3, 105, 161, 0.05)`, Border left `4px solid #0369a1`.

### Elementos Visuais
- Caixas de layout "Problem/Solution" bem estruturadas, sem imagens pesadas, foco em tipografia limpa.

### Animações
- Revelação ao scroll (Data-AOS): Textos à esquerda dão `fade-up`, duração `800ms`, trigger à 20% do bottom, `disableMutationObserver: true`. Cards à direita entram com delay em stagger (`200ms` e `400ms`).

### Interatividade
- Hover nos cards à direita: `transform: translateX(8px)` com `transition: transform 0.3s ease`.

### Responsividade
- Dispositivos (<992px): Grid empilha (`1fr`), gap `48px`. Cards ocupam largura total, e perdem parte da discrepância lateral se não couber.

---

## Seção 3: A Solução

### Arquétipo e Constraints
- **Arquétipo:** Bento Box (Grid Irregular/Mosaico)
- **Constraints:** Hover Lift, Progress Bar (Simulação visual de preenchimento)
- **Justificativa:** Como são 4 pontos (Copy, LPs, Automação, Tráfego), o Bento grid quebra a monotonia dos cards lado a lado, criando células de tamanhos diferentes, refletindo sistemas integrados.

### Conteúdo
- **Título:** Como o Funil de Vendas de R$ 30 Mil/Mês vai funcionar:
- **Bullet 1:** Copy persuasiva mas ética (totalmente alinhada com as normas do CFM).
- **Bullet 2:** Landing Pages de Alta Conversão (design premium, confiança instantânea).
- **Bullet 3:** Automação completa (Páginas, VSL e E-mails integrados, enquanto você atende).
- **Bullet 4:** Tráfego focado (Anúncios validados para trazer alunos qualificados).

### Layout
- Padding: `100px 0`, Background: `#f8fafc`.
- **Header:** Título centralizado, largura máxima `700px`, margin bottom `64px`.
- **Bento Grid:** `display: grid`, `grid-template-columns: repeat(3, 1fr)`, `grid-template-rows: auto auto`, `gap: 24px`.
- Distribuição: 
  - Card 1 (Copy): `grid-column: span 1` (quadrado vertical)
  - Card 2 (LPs): `grid-column: span 2` (retângulo horizontal)
  - Card 3 (Automação): `grid-column: span 2` (retângulo horizontal)
  - Card 4 (Tráfego): `grid-column: span 1` (quadrado vertical)

### Tipografia
- Título principal: Outfit, `font-size: 2.5rem`, `font-weight: 700`, alinhamento centro.
- Bullet Titles (cards): Outfit, `font-size: 1.25rem`, `font-weight: 600`, color: `#0f172a`.
- Bullet Texts: Inter, `font-size: 1rem`, color: `#475569`, `line-height: 1.6`.

### Cores
- Fundo Seção: `#f8fafc`.
- Cards: Background `#ffffff`, border `1px solid #e2e8f0`. Ícones `#14b8a6` (Copy) e gradients alternandos nos grandes para diferenciar.

### Elementos Visuais
- Gráficos abstratos SVG: No Card de LPs (span 2), um ícone simulando janelas. No Card de Automação, uma "Progress Bar" ou trilha contínua conectando pontos (steps de emails/páginas).

### Animações
- Staggered `fade-up`: Todos os Bento cards sobem com atrasos sequenciais (`100ms`, `200ms`, `300ms`, `400ms`).

### Interatividade
- Hover Lift nos cards: `transform: translateY(-4px)`, boxShadow `0 20px 40px rgba(15, 23, 42, 0.05)`, duração 400ms.

### Responsividade
- `<992px`: Grid vira `grid-template-columns: repeat(2, 1fr)`. Cards 1 e 4 ficam span 1, Cards 2 e 3 ficam span 2.
- `<768px`: Todos os cards ficam `grid-column: span 1` em coluna simétrica.

---

## Seção 4: A Minha Engenharia na Prática (Resultados)

### Arquétipo e Constraints
- **Arquétipo:** Layered / Overlapping Grid Empilhados
- **Constraints:** Dark Mode (Alto Contraste), Scroll Reveal (Text Gradient)
- **Justificativa:** Resultados marcantes (financeiros) demandam fundo escuro para contrastar, transmitindo sobriedade corporativa. Camadas criam profundidade.

### Conteúdo
- **Título:** Estratégias que já geraram mais de R$ 2,5 Milhões
- **Item 1:** Em 4 meses, começamos um infoproduto do completo ZERO. O resultado?
- **Item 2:** Funil Low Ticket operando sozinho todos os dias na internet.
- **Item 3:** Perpetuo rodando com pico de faturamento em campanhas: R$ 302.281,03 lucrados e um prêmio Hotmart Black (R$ 1.804.309,82+ ganhos totais).

### Layout
- Background: Escuro Deep Dark `#0c4a6e` a `#0f172a`.
- Padding topo/base: `120px 0`.
- Cards de Métricas (`max-width: 800px`) distribuídos empilhados visualmente, com gap lateral simulado e offset de cima para o meio (um em cima do outro, quebrando simetria vertical por margens aleatórias ou stagger vertical rígido).

### Tipografia
- Título principal: Outfit, `2.5rem`, color `#ffffff`.
- Texto Principal do Card: Outfit, `font-weight: 700`, `font-size: 1.5rem` a `2.5rem` nos números "R$".
- Subtexto: Inter, `1rem`, color `#cbd5e1`.

### Cores
- Fundo Global: Radial gradient focado central `#0c4a6e`(10% luz) caindo para `#0f172a`(bordas).
- Cards das métricas: Background `#1e293b` (slate-800) transparente a 60%, blur 20px. Border top `1px rgba(255,255,255,0.1)`.
- Textos dos prêmios (R$ 1.8M): Text-gradient linear (`#14b8a6` a `#0ea5e9`).

### Elementos Visuais
- Os cards são placas de vidro polidas e escuras (Dark Glassmorphism). O selo figurativo do Hotmart Black em contorno dourado ou branco suave texturizado ao invés de inserção de img raster.

### Animações
- Revelação `zoom-y-out` ou `fade-up`. 

### Interatividade
- Hover Highlight: a borda rgba muda sutilmente de 0.1 para 0.3 de branco sólido. Efeito sútil sem invadir o espaço.

### Responsividade
- Simples e legível. No mobile, textos de 2.5rem devem cair para `1.75rem` e empilhamento rigoroso linear (`margin-bottom: 24px` nativo).

---

## Seção 5: Pra Quem é Isto?

### Arquétipo e Constraints
- **Arquétipo:** Split Horizontal (Um cabeçalho imponente listando 2 blocos textuais logo abaixo).
- **Constraints:** Glassmorphism limpo de fundo claro, Imagem Blur Background (Blobs abstratos orgânicos azuis ao fundo).
- **Justificativa:** Clarabóias azuis turquesa de fundo quebram o peso do escuro, dando o tom de renascimento, fôlego e avanço prospectivo (quem os serve).

### Conteúdo
- **Título:** Este serviço Premium é exclusivo para...
- **Benefício 1:** Médicos com autoridade que já têm (ou vão gravar) um infoproduto, precisam escalar os resultados de forma profissional e exigem excelência na comunicação.
- **Benefício 2:** Especialistas que não têm tempo a perder tentando montar quebra-cabeças no marketing digital sozinhos.

### Layout
- Padding `100px 0`. Fundo `#ffffff`.
- Section Titulo alinhado no topo central (Max Width `600px`).
- Dois grandes "Painéis", `grid-template-columns: 1fr 1fr`, gap `32px`.

### Tipografia
- Título: Outfit, `2.5rem`, color `#0f172a`.
- Benefícios: Inter, `1.25rem`, leading `1.6`, color `#475569`. Sem títulos internos. Checkmark de chumbo.

### Cores
- Glows de Fundo: Spots absolutos de `#0ea5e9` com opacity `0.10` e blurs `120px` nos laterais.
- Painéis: Background `#f8fafc`. Ícones de Check: SVG estilizado em `#0369a1`.

### Elementos Visuais
- Duas colunas massivas em white-space brutalista, sem bordas pesadas, deixando os textos alinhados à esquerda fluirem à vontade.

### Animações
- Fade-up clássico no load da seção com staggered columns.

### Interatividade
- Hover nas colunas faz hover de fundo suave de `#f8fafc` -> `#f1f5f9`.

### Responsividade
- `<992px`: Grid muda para empilhamento vertical `1fr`. Margin base dos painéis `20px`.

---

## Seção 6: CTA Intermediário

### Arquétipo e Constraints
- **Arquétipo:** Container Narrow (Focus Center)
- **Constraints:** Text Highlight, Hover Shadow/Scale profundo.
- **Justificativa:** É uma interrupção da leitura focada no convencimento de reputação. O limite estreito canaliza o olhar unicamente para o botão.

### Conteúdo
- **Título:** Sua reputação médica não merece uma estratégia barata.
- **CTA:** Quero uma operação que vende todo dia

### Layout
- Container estreito `max-width: 800px`, texto totalmente centralizado. Fundo `#f8fafc`. Padding `120px 0`.

### Tipografia
- Título: Outfit, `3rem` (`clamp(2rem, 4vw, 3rem)`), `font-weight: 800`, line height `1.1`. Color: `#0f172a`.
- Palavra "barata" pode ser aplicada com `font-style: italic` ou um peso menor cromaticamente cinza.
- Botão CTA: O global premium da página.

### Cores
- Simplicidade brutal, texto muito preto/azul muito escuro no fundo muito claro. Foco todo no botão `primary` que tem o gradiente vivo.

---

## Seção 7: Sobre o Especialista

### Arquétipo e Constraints
- **Arquétipo:** Off-Grid Element / Asymmetric Split (A foto escapa um pouco para cima do margin base).
- **Constraints:** Color Overlay (Na foto/placeholder), Text Stagger sequencial listado.
- **Justificativa:** O especialista é a vitrine. O layout precisa de elegância de livro didático ou panfleto premium. Off-grid breaks criam aquele ar de portfólio rico.

### Conteúdo
- **Título:** Gian, o estrategista por trás dos grandes números
- **Parágrafo 1:** Diferente das agências genéricas, eu sou um Estrategista e Copywriter especializado em conversão. Ao contrário de quem promete números vazios, eu entrego engenharia.
- **Bullets:** Mais de R$ 2,5 milhões faturados como Copywriter e Co-produtor; Vencedor prêmio Hotmart Black; Certificado AWAI; +R$ 250 mil em 4 lançamentos do zero; Formações fortes (Empiricus, Leandro Ladeira, O Novo Mercado).

### Layout
- Padding: `120px 0`. Background `#ffffff`.
- Grid de 12 colunas ou simplesmente flex box lateral: `45% (foto) 55% (texto)`.
- Espaço lateral `64px`. A foto (`aspect-ratio: 4/5`) flutua `-40px` top em relação à linha do texto se vista de forma paralela.

### Tipografia
- Título: Outfit, `2.5rem`, color `#0f172a`.
- Parágrafo Principal: Inter `1.125rem`, `#475569`.
- Bullets: `1rem` `#0f172a`.

### Cores
- Elemento de foto (ou seu emulador cinza) terá uma moldura sutil de fundo deslocada uns `20px` para baixo/direita preenchida com `#0ba5e9` de opacidade 0.2, servindo como Box Shadow criativo (Editorial Shadow).
- Bullets com checks de `#0d9488`.

### Elementos Visuais
- O Frame fotográfico solto e assimétrico faz a magia de não ser apenas uma "seção padrão". 
- Os bullet-points formam uma listagem densa, cheia de gatilhos corporativos.

### Animações
- Revelação da capa deslizando e texto seguindo com delay.

### Responsividade
- `<768px`: Torna-se colunas de 100%, sem margin negativa. Título cai levemente, texto central/left.

---

## Seção 8: FAQ e Objeções

### Arquétipo e Constraints
- **Arquétipo:** Rule of Thirds (Apenas esquerda: Titulo + Espaço / Direita: Expansíveis Accordion).
- **Constraints:** Accordion Reveal, Smooth Height transition com Rotating Chevron Icons.
- **Justificativa:** Simples, confiante (nicho médico adora clareza). Não enche espaço, vai direto ao ponto.

### Conteúdo
- **3 Perguntas:** 1) Regras CRM? Jamais (Ética). 2) O que inclui em 21 dias? O ecossistema completo. 3) E se não tiver produto pronto? Validamos oferta primeiro.

### Layout
- Padding `100px 0`. Background `#f8fafc`.
- `display: flex`, gap `64px`. Lado esquerdo (33%) título, lado direito (67%) faq list.
- Título com atributo `position: sticky; top: 120px` para quem o tiver visível na viewport grande.

### Tipografia
- Titulo: Outfit `2.5rem`, color `#0f172a`.
- Perguntas: Outfit `1.25rem` `#0f172a`. Respostas: Inter `1rem` `#475569`.

### Cores
- Acordions: BG `#ffffff`, bottom-border `1px solid #e2e8f0`. Icon e pergunta ao fazer hover transicionam o color `#0f172a` para `#0369a1`.

### Elementos Visuais
- Chevrons ou setas pequenas de 16px. Rotacionadas via JS ou css checkbox-hack em classe estendida (`transform: rotate(180deg)`).

### Interatividade
- Hover Color nos headers. Transition suave na abertura do content `max-height`.

### Responsividade
- Mobile: `100% width` layout sequencial. Sticky cai nativamente, flutuando normalmente o flex.

---

## Seção 9: Fechamento Final

### Arquétipo e Constraints
- **Arquétipo:** Spotlight Maximize Absolute (Única coisa preenchendo o fundo imenso e noturno).
- **Constraints:** Minimalista Supremo.
- **Justificativa:** Dá um "vazio" na página que engaiola a decisão final na mente do cliente sem pontos de fuga.

### Conteúdo
- **Título:** Não quero te vender um "cursinho".
- **Parágrafo:** Meu compromisso é pegar sua bagagem médica e transformá-la num sistema ativo de vendas no digital. A decisão final ainda é sua: tentar criar mais um post na internet ou ligar uma máquina de vendas de mais de R$ 30.000 mensais sob demanda.
- **CTA:** Quero falar sobre meu infoproduto

### Layout
- Padding Extremo `160px 0`. Background preenchendo toda a div `#0f172a`.
- `max-width: 700px` container box em texto center.

### Tipografia
- Outfit gigante: `3rem+` branco absoluto.
- Parágrafo de chumbo largo: `1.25rem`, `#cbd5e1`.
- Botão massificado, robusto centralizado.

### Animações
- Tudo sobe à uma duração maior de transição (ex: `1200ms`) num silêncio visual, como epílogo de filme.

---
