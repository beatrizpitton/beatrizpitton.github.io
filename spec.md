# Especificação — Portfólio Pessoal de Beatriz Pitton

| Campo | Valor |
| --- | --- |
| Versão | 1.0 |
| Data | 22 de outubro de 2026 |
| Status | Aprovado para implementação |
| Responsável | Beatriz Pitton |
| Implementação | Arquivo único `index.html` (HTML + CSS + JS embutidos) |
| Publicação | GitHub Pages |

---

## 1. Visão geral

Site pessoal de uma página para apresentar Beatriz Pitton, estudante de Administração na Atitus Educação (Muliterno, RS), e seu portfólio de projetos. O site deve funcionar como uma peça de posicionamento profissional: demonstrar método, clareza e capacidade de transformar análise em decisão.

Não é um currículo expandido. É um **portfólio de casos**: cada projeto apresenta contexto, desafio, ações, resultados e aprendizado.

### 1.1 Princípio editorial

> Boa administração é menos sobre ferramentas e mais sobre clareza: entender o problema, organizar a informação e comunicar a decisão.

Toda decisão de design e conteúdo deve reforçar esse princípio.

---

## 2. Objetivos e métricas

### 2.1 Objetivo primário

Conseguir convites para entrevistas de estágio em administração, operações, projetos ou análise de dados.

### 2.2 Objetivos secundários

- Documentar o aprendizado do curso de forma pública e incremental.
- Criar uma base reutilizável para candidaturas (link único no currículo e no LinkedIn).
- Praticar escrita profissional em português.

### 2.3 Métricas de sucesso

| Métrica | Meta |
| --- | --- |
| visitante entende formação e disponibilidade | em até 15 segundos |
| visitante abre ao menos um case | ≥ 40% das sessões |
| contatos qualificados por mês | ≥ 3 |
| Lighthouse (Performance, Acessibilidade, Boas práticas, SEO) | ≥ 95 |
| erros no console | 0 |
| peso total da página (sem fontes) | ≤ 120 KB |

Sem analytics na versão 1.0. As métricas acima são avaliadas por teste manual com 3 a 5 pessoas e pelo Lighthouse.

---

## 3. Público-alvo

### Persona 1 — Recrutadora de RH

- Tem de 30 a 60 segundos por candidato.
- Quer saber: curso, semestre, instituição, cidade, disponibilidade e contato.
- Não lê textos longos. Precisa de hierarquia clara e botão de contato visível.

### Persona 2 — Gestora de pequena ou média empresa

- Quer evidência de raciocínio e organização.
- Valoriza casos com problema, método e resultado, mesmo que ilustrativos.
- Desconfia de jargão e de números sem contexto.

### Persona 3 — Professor ou orientador

- Busca consistência metodológica e clareza na documentação.
- Pode indicar a aluna para projetos, monitorias ou vagas.

---

## 4. Posicionamento e tom de voz

### 4.1 Frase de posicionamento

**“Transformo complexidade em processos claros — e análise em decisão.”**

### 4.2 Tom

- Primeira pessoa, direto, sem arrogância.
- Frases curtas. Preferir verbos concretos.
- Explicar o “porquê” antes da ferramenta.
- Assumir o que ainda está em aprendizado (2º semestre) sem diminuir a entrega.

### 4.3 Evitar

- “Apaixonada por desafios”, “proativa”, “dinâmica” e clichês de currículo.
- Barras de proficiência sem critério.
- Resultados inventados apresentados como reais.
- Excesso de emojis, gradientes e sombras.
- Mais de uma cor de destaque.

---

## 5. Escopo

### 5.1 Dentro do escopo (v1.0)

- Página única responsiva com as seções: Hero, Sobre, Competências, Projetos, Formação, Contato e Footer.
- Três cases ilustrativos, claramente marcados como exemplo.
- Tema claro e escuro com persistência em `localStorage`.
- Filtro de projetos por categoria.
- Modal acessível com o case completo.
- Formulário de contato com validação e envio via `mailto:`.
- SEO básico, Open Graph, JSON-LD e favicon embutido.
- Publicação no GitHub Pages.
- Documentação em `spec.md` e `AGENTS.md`.

### 5.2 Fora do escopo (v1.0)

- Backend, banco de dados, login ou CMS.
- Blog ou páginas adicionais.
- Internacionalização (PT/EN).
- Analytics, cookies ou rastreamento.
- Download de currículo em PDF (previsto, mas o arquivo ainda não existe).
- Foto pessoal (prevista, mas ainda não fornecida).
- Integração com LinkedIn ou GitHub (links pendentes).
- Formspree (endpoint ainda não fornecido; `mailto:` é o padrão).

---

## 6. Arquitetura da informação

Página única, com navegação por âncoras.

| Ordem | Seção | Âncora | Objetivo |
| --- | --- | --- | --- |
| 0 | Header fixo | `#topo` | Navegação, tema, menu mobile |
| 1 | Hero | — | Nome, posicionamento, CTAs, ficha rápida |
| 2 | Sobre | `#sobre` | Contexto pessoal e forma de trabalhar |
| 3 | Competências | `#competencias` | Áreas de conhecimento e ferramentas |
| 4 | Projetos | `#projetos` | Cases filtráveis com modal |
| 5 | Formação | `#formacao` | Graduação, trilha de certificações |
| 6 | Contato | `#contato` | E-mail, formulário e disponibilidade |
| 7 | Footer | — | Créditos, ano e retorno ao topo |

### 6.1 Jornada esperada

1. Chega por link direto, LinkedIn ou currículo.
2. Lê nome, curso e proposta no Hero.
3. Rola para Projetos ou vai direto ao Contato.
4. Abre um case para avaliar método.
5. Copia o e-mail ou envia mensagem pelo formulário.

---

## 7. Conteúdo por seção

### 7.1 Hero

- Selo: “Estudante de Administração · 2º semestre”.
- Nome: Beatriz Pitton.
- Frase de posicionamento com uma palavra em itálico.
- Parágrafo curto: curso, instituição e cidade.
- CTAs: “Ver projetos” (primário) e “Vamos conversar” (secundário).
- Ficha rápida: formação, semestre, base, foco, status e e-mail.
- Indicador “Aberta a estágios”.

### 7.2 Sobre

- Biografia em 3 parágrafos curtos.
- Origem do interesse por administração.
- O que estuda hoje e como usa os trabalhos da faculdade como laboratório.
- Crença de trabalho (clareza antes de ferramenta).
- Citação curta em destaque.

### 7.3 Competências

Quatro blocos, sem barras de progresso:

1. **Processos & Operações** — AS-IS/TO-BE, BPMN, gargalos, padronização, checklists.
2. **Análise de Dados** — planilhas, indicadores, dashboards, leitura crítica de métricas.
3. **Finanças** — DRE simplificada, custos fixos e variáveis, margem de contribuição, ponto de equilíbrio.
4. **Estratégia & Mercado** — pesquisa com clientes, SWOT, matriz de decisão, cenários.

Faixa de ferramentas: Excel, Power BI (básico), Notion, Canva, Google Workspace, Trello, BPMN.

### 7.4 Projetos

- Três cases iniciais, marcados como **Projeto-exemplo**.
- Filtros: Todos, Processos, Finanças, Estratégia.
- Cada card mostra número, categoria, ano, título, resumo curto e tags.
- O detalhe abre em modal com: contexto, desafio, o que foi feito, resultados e aprendizado.
- Aviso visível de que os dados são ilustrativos.

### 7.5 Formação

- Graduação em Administração, Atitus Educação — em andamento, 2º semestre.
- Trilha de certificações **planejadas** (Excel, Power BI, gestão de processos), sem inventar conclusões.
- Texto honesto: “Ainda não publiquei certificações”.

### 7.6 Contato

- Convite claro para estágio ou conversa.
- E-mail em destaque: `pittonbeatriz2@gmail.com`.
- Botão “Copiar e-mail”.
- Formulário: nome, e-mail, mensagem e campo honeypot.
- Aviso de que o envio abre o aplicativo de e-mail e nada é armazenado no site.
- Prazo de resposta: até 2 dias úteis.

### 7.7 Footer

- “© 2026 Beatriz Pitton”.
- Nota “Feito à mão em HTML, CSS e JS”.
- Link “Voltar ao topo”.

---

## 8. Modelo de conteúdo dos projetos

Cada case deve seguir a mesma estrutura, para permitir comparação e leitura rápida.

| Campo | Regra |
| --- | --- |
| `id` | Slug curto, sem acentos (ex.: `processos`) |
| `categoria` | Processos, Finanças ou Estratégia |
| `ano` | Ano do trabalho |
| `titulo` | 6 a 12 palavras, com verbo ou pergunta |
| `resumo` | 1 a 2 linhas, até 180 caracteres |
| `contexto` | 2 a 4 frases: empresa, rotina e problema |
| `desafio` | 1 a 2 frases: a pergunta que precisava ser respondida |
| `acoes` | Lista ordenada de 3 a 5 passos concretos |
| `resultados` | 2 a 3 métricas com número e legenda |
| `aprendizado` | 1 frase, em primeira pessoa |
| `ferramentas` | 3 a 5 tags |
| `aviso` | “Projeto-exemplo” e dados ilustrativos, quando aplicável |

### 8.1 Regras

- Nunca publicar número real sem fonte ou autorização.
- Cases ilustrativos levam o selo “Projeto-exemplo” no card e no modal.
- O resultado deve responder ao desafio, não apenas listar atividades.
- O aprendizado deve revelar critério, não elogiar a si mesma.

---

## 9. Design system

### 9.1 Direção

Editorial minimalista: papel, tinta, tipografia serifada, linhas finas e muito espaço em branco. Referências: revistas de arquitetura, relatórios de consultoria e cadernos de projeto.

### 9.2 Cores

| Token | Claro | Escuro | Uso |
| --- | --- | --- | --- |
| `--paper` | `#F6F3EC` | `#131310` | Fundo principal |
| `--paper-2` | `#EFEBE1` | `#1A1A16` | Fundo alternado |
| `--ink` | `#1B1B18` | `#EDE9DF` | Texto principal |
| `--ink-soft` | `#4A4841` | `#C9C4B8` | Texto secundário |
| `--muted` | `#5F5C54` | `#A8A395` | Legendas e metadados |
| `--line` | `#DAD4C7` | `#2E2D27` | Bordas suaves |
| `--line-strong` | `#C3BCAB` | `#44423A` | Divisores e chips |
| `--accent` | `#24503F` | `#8FBFAA` | Destaque |
| `--accent-soft` | `#E3EAE4` | `#1E2C27` | Fundos de destaque |
| `--accent-ink` | `#F6F3EC` | `#10201A` | Texto sobre acento |

Contraste mínimo: 4,5:1 para texto normal e 3:1 para texto grande. O acento nunca é usado sozinho para transmitir informação.

### 9.3 Tipografia

| Papel | Fonte | Escala |
| --- | --- | --- |
| Display / títulos | Fraunces (serifada) | `clamp(3.4rem, 9vw, 7.2rem)` no Hero; `clamp(2rem, 4vw, 3rem)` em H2 |
| Corpo / interface | Inter (sans) | 16–18 px, linha 1,6 |
| Metadados | Inter | 11–13 px, caixa alta, `letter-spacing: .08em` |

Fallbacks: Georgia / Palatino para serifada; system UI para sans. Fontes via Google Fonts com `preconnect` e `display=swap`.

### 9.4 Layout

- Largura máxima: 1120 px.
- Padding lateral: `clamp(20px, 5vw, 40px)`.
- Grid editorial: coluna de título (220 px) + conteúdo.
- Escala de espaço: 4, 8, 12, 16, 24, 32, 48, 64, 96, 112 px.
- Bordas de 1 px; raio de 3 a 6 px; sombras apenas no modal.
- Breakpoints: 1000 px, 860 px, 720 px, 560 px.

### 9.5 Componentes

Header fixo, marca, navegação, alternador de tema, menu mobile, botões, chips, cards de competência, cards de projeto, filtros, timeline, painel de certificações, formulário, modal de case, footer.

### 9.6 Movimento

- Transições de 200 a 300 ms para hover e foco.
- Revelação de seções com `IntersectionObserver` (16 px, 600 ms).
- `prefers-reduced-motion: reduce` desliga transformações e animações.
- Nada de parallax, autoplay ou animação contínua.

---

## 10. Requisitos funcionais

| ID | Requisito | Prioridade |
| --- | --- | --- |
| RF-01 | Navegação por âncoras com header fixo e `scroll-padding` | Must |
| RF-02 | Tema claro/escuro, persistido e inicializado antes da pintura | Must |
| RF-03 | Menu mobile acessível com `aria-expanded`, fechamento por ESC e clique | Must |
| RF-04 | Filtro de projetos por categoria, com estado `aria-pressed` | Must |
| RF-05 | Modal de case com `<dialog>`, ESC, clique no backdrop, foco devolvido | Must |
| RF-06 | Formulário validado que monta um `mailto:` com assunto e corpo | Must |
| RF-07 | Botão de copiar e-mail com feedback visual | Should |
| RF-08 | Revelação suave no scroll, respeitando movimento reduzido | Should |
| RF-09 | Indicação da seção ativa na navegação | Should |
| RF-10 | Ano do footer atualizado automaticamente | Could |
| RF-11 | Conteúdo principal e resumos legíveis sem JavaScript | Must |
| RF-12 | Suporte a endpoint Formspree quando configurado | Could |

---

## 11. Requisitos não funcionais

| ID | Requisito |
| --- | --- |
| RNF-01 | Um único `index.html`, sem build e sem frameworks de CSS/JS |
| RNF-02 | Nenhuma dependência de JavaScript externo |
| RNF-03 | Página abaixo de 120 KB sem as fontes |
| RNF-04 | LCP < 2,5 s e CLS < 0,1 em conexão 4G |
| RNF-05 | Layout íntegro de 360 px a 1440 px |
| RNF-06 | WCAG 2.2 nível AA |
| RNF-07 | Funcionar nas duas últimas versões de Chrome, Edge, Firefox e Safari |
| RNF-08 | Código comentado por blocos e com tokens reutilizáveis |
| RNF-09 | Nenhum cookie, analytics ou coleta de dados |
| RNF-10 | Conteúdo em português do Brasil, revisado |

---

## 12. SEO e metadados

- `lang="pt-BR"`.
- `<title>`: “Beatriz Pitton — Portfólio de Administração”.
- Meta description com curso, instituição e foco (até 160 caracteres).
- Open Graph: tipo `profile`, locale `pt_BR`, título e descrição.
- Twitter Card: `summary`.
- JSON-LD `Person`: nome, cargo, e-mail, cidade, instituição e áreas de conhecimento.
- Favicon SVG embutido com monograma “BP”.
- Canonical: `https://beatrizpitton.github.io/`; `og:url` correspondente.
- Um único `<h1>`; hierarquia de headings sem saltos.

---

## 13. Acessibilidade

- Skip link para o conteúdo.
- Landmarks: `header`, `nav`, `main`, `section`, `footer`.
- Foco visível com contraste de 3:1.
- Navegação completa por teclado.
- Modal com título associado, foco preso pelo `<dialog>` e retorno ao gatilho.
- Filtros como botões com `aria-pressed`.
- Formulário com `<label>` explícito, `autocomplete` e mensagens em `role="status"`.
- Ícones decorativos com `aria-hidden="true"`.
- Texto alternativo em imagens futuras.
- Respeito a `prefers-reduced-motion`.
- Alvos de toque com pelo menos 40 px.

---

## 14. Privacidade e LGPD

- O site não usa cookies, analytics ou rastreadores.
- O formulário não envia dados para servidor: monta um `mailto:` no dispositivo.
- O e-mail é público por decisão da titular.
- Nenhum dado sensível é coletado.
- Se o Formspree for ativado, a política deve informar o processamento externo.

---

## 15. Deploy

### Opção A — Site de usuário (escolhida)

1. Repositório: `beatrizpitton/beatrizpitton.github.io`.
2. Branch `main`, arquivos na raiz.
3. Settings → Pages → Deploy from a branch → `main` / `/ (root)`.
4. URL: `https://beatrizpitton.github.io/`.

### Opção B — Site de projeto

1. Criar o repositório `portfolio`.
2. Enviar `index.html` para a raiz.
3. Settings → Pages → `main` / `/ (root)`.
4. URL: `https://beatrizpitton.github.io/portfolio/`.

O site usa apenas âncoras relativas, portanto funciona nas duas opções. O canonical e o `og:url` já apontam para `https://beatrizpitton.github.io/`; se a opção B for usada, atualize os dois.

---

## 16. Critérios de aceite

- [ ] A página abre localmente com duplo clique, sem servidor.
- [ ] Header, Hero, Sobre, Competências, Projetos, Formação, Contato e Footer estão presentes.
- [ ] Nome, curso, semestre, instituição, cidade e e-mail corretos.
- [ ] Os três cases abrem no modal e podem ser fechados por botão, ESC e backdrop.
- [ ] O filtro exibe apenas a categoria escolhida e “Todos” restaura os três.
- [ ] O tema alterna sem “flash” e permanece após recarregar.
- [ ] O menu mobile abre, fecha e não prende o foco.
- [ ] O formulário valida campos vazios e e-mail inválido e abre o cliente de e-mail.
- [ ] O botão de copiar e-mail exibe confirmação.
- [ ] Layout testado em 360, 768, 1024 e 1440 px.
- [ ] Navegação por teclado e skip link funcionam.
- [ ] Lighthouse ≥ 95 nas quatro categorias.
- [ ] Nenhum erro no console.
- [ ] Todos os dados ilustrativos estão sinalizados.
- [ ] Links quebrados: nenhum.

---

## 17. Roadmap

| Versão | Entrega |
| --- | --- |
| 1.0 | Site completo com três cases ilustrativos |
| 1.1 | Substituir cases por projetos reais e adicionar CV em PDF |
| 1.2 | Foto pessoal, LinkedIn e imagem Open Graph |
| 1.3 | Formspree e, se necessário, uma página de agradecimento |
| 2.0 | Estudos de caso em páginas próprias, com mais profundidade |

---

## 18. Riscos e mitigações

| Risco | Impacto | Mitigação |
| --- | --- | --- |
| Cases ilustrativos serem confundidos com reais | Alto | Selo “Projeto-exemplo” e aviso no card e no modal |
| Pouco conteúdo real no início | Médio | Estrutura preparada para substituição incremental |
| Fonte externa indisponível | Baixo | Fallbacks locais de Georgia e system UI |
| Formulário `mailto:` falhar em dispositivos sem cliente | Médio | E-mail visível e botão de copiar |
| Imagem Open Graph ausente | Baixo | Adicionar `assets/og-image.png` e a meta `og:image` |
| Excesso de animação | Baixo | Movimento discreto e respeito a reduced motion |

---

## 19. Pendências de conteúdo

| Item | Status | Onde entra |
| --- | --- | --- |
| LinkedIn | Pendente | Contato/Sobre |
| Foto pessoal | Opcional | Sobre |
| Currículo em PDF | Opcional | CTA do Hero |
| ID do Formspree | Opcional | Constante no JS |
| Imagem Open Graph | Opcional | `assets/og-image.png` e meta `og:image` |
| Projetos reais | Pendente | Substituir os três templates |
| Certificações concluídas | Pendente | Seção Formação |

---

## 20. Estrutura de arquivos

```text
Projeto Padrão/
├── index.html    # site completo (HTML + CSS + JS embutidos)
├── spec.md       # esta especificação
├── AGENTS.md     # guia para manutenção e agentes
└── assets/       # opcional: cv.pdf, foto.jpg, og-image.png
```

O site não depende da pasta `assets/` para funcionar. Ela só é criada quando houver arquivos reais.
