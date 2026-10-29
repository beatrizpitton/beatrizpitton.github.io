# AGENTS.md — Guia de manutenção

Este arquivo orienta pessoas e agentes de IA que forem editar o portfólio de **Beatriz Pitton**. Leia a `spec.md` antes de mudanças grandes. Em caso de conflito, a `spec.md` vence.

---

## 1. Contexto

Site pessoal de página única, publicado no GitHub Pages, para apresentar Beatriz Pitton — estudante de Administração (2º semestre) na Atitus Educação, em Muliterno, RS — e três cases ilustrativos de gestão, finanças e estratégia.

**Objetivo do site:** gerar convites para entrevistas de estágio e demonstrar método, clareza e capacidade de comunicação.

**Stack:** HTML5 + CSS + JavaScript vanilla, tudo dentro de `index.html`.
**Build:** nenhum.
**Dependências:** apenas Google Fonts (Fraunces e Inter), com fallback local.

---

## 2. Regras invioláveis

1. **Arquivo único.** CSS e JS devem permanecer embutidos em `index.html`. Não criar `style.css`, `script.js`, bundler ou `package.json`.
2. **Sem frameworks.** Nada de React, Vue, Tailwind, Bootstrap, jQuery ou similares.
3. **Sem JavaScript externo.** Nenhum CDN, tag manager ou widget de terceiros.
4. **Português do Brasil.** Todo texto visível, comentários e mensagens de erro.
5. **Nada de credencial inventada.** Cursos, certificações, empregos e resultados não confirmados não podem ser publicados como reais.
6. **Cases ilustrativos são identificados.** O selo “Projeto-exemplo” e o aviso de dados ilustrativos devem permanecer enquanto os números forem fictícios.
7. **Acessibilidade não é opcional.** Toda mudança deve preservar navegação por teclado, foco visível, contraste e textos alternativos.
8. **Sem rastreamento.** Não adicionar analytics, cookies, pixels ou formulários que enviem dados sem consentimento.
9. **Sem `innerHTML` com conteúdo de usuário.** Os cases são clonados de `<template>`; mantenha esse padrão.
10. **Não quebrar as âncoras.** `#sobre`, `#competencias`, `#projetos`, `#formacao` e `#contato` são usadas em links externos.

---

## 3. Mapa de arquivos

```text
Projeto Padrão/
├── index.html    # site completo (HTML + CSS + JS embutidos)
├── spec.md       # especificação funcional e de design
├── AGENTS.md     # este guia
└── assets/       # opcional: cv.pdf, foto.jpg, og-image.png
```

- `index.html` é a única fonte de verdade do site.
- `assets/` não existe na v1.0. Só crie quando houver arquivo real.
- `spec.md` e `AGENTS.md` não são publicados como páginas; ficam no repositório.

---

## 4. Como visualizar

**Opção 1 — duplo clique:** abra `index.html` no navegador. O site funciona sem servidor.

**Opção 2 — servidor local** (recomendado para testar o formulário e o `file://`):

```powershell
python -m http.server 8000
# depois acesse http://localhost:8000
```

Não há comando de build, teste automatizado ou lint configurado.

---

## 5. Estrutura do `index.html`

A ordem dos blocos é intencional. Não reorganize sem motivo.

| Bloco | O que contém |
| --- | --- |
| `<head>` | Metadados, SEO, Open Graph, JSON-LD, favicon, fontes e boot de tema |
| `<style>` | Reset, tokens, base, layout, componentes, modal, responsivo, impressão |
| `<body>` | Skip link, header, `main` com seções, footer |
| `<template>` | Conteúdo completo dos três cases (um por template) |
| `<dialog>` | Casca do modal; o conteúdo é clonado do template |
| `<script>` | Módulos comentados: tema, menu, filtro, modal, reveal, nav ativa, formulário, cópia de e-mail |

### 5.1 IDs e contratos entre HTML e JS

| Elemento | ID / atributo | Contrato |
| --- | --- | --- |
| Header | `#topo` | Link da marca e “voltar ao topo” |
| Navegação | `#nav` | Controlada por `#menu-toggle` |
| Tema | `#theme-toggle` | `aria-pressed` reflete o tema escuro |
| Filtros | `[data-filter]` | Valores: `todos`, `processos`, `financas`, `estrategia` |
| Cards | `[data-category]` | Precisa bater com um `data-filter` |
| Gatilho do case | `[data-case]` | Valor deve ser o sufixo do template |
| Templates | `#case-processos`, `#case-financas`, `#case-estrategia` | Conteúdo do modal |
| Modal | `#case-dialog`, `#case-content` | Casca e área injetada |
| Formulário | `#contact-form`, `#form-status` | Validação e feedback |
| E-mail | `#copy-email` | Copia `data-copy` |

**Regra:** `data-case="processos"` abre `#case-processos`. Se renomear um, renomeie o outro.

---

## 6. Design tokens

Ficam no início do `<style>`, em `:root` e `[data-theme="dark"]`.

| Token | Claro | Escuro | Uso |
| --- | --- | --- | --- |
| `--paper` | `#F6F3EC` | `#131310` | Fundo |
| `--paper-2` | `#EFEBE1` | `#1A1A16` | Seção alternada |
| `--ink` | `#1B1B18` | `#EDE9DF` | Texto |
| `--ink-soft` | `#4A4841` | `#C9C4B8` | Texto secundário |
| `--muted` | `#5F5C54` | `#A8A395` | Legendas |
| `--line` | `#DAD4C7` | `#2E2D27` | Bordas |
| `--line-strong` | `#C3BCAB` | `#44423A` | Divisores |
| `--accent` | `#24503F` | `#8FBFAA` | Destaque |
| `--accent-soft` | `#E3EAE4` | `#1E2C27` | Fundo de destaque |
| `--accent-ink` | `#F6F3EC` | `#10201A` | Texto sobre acento |

**Tipografia:** títulos em Fraunces, corpo em Inter. Fallbacks: Georgia e system UI.
**Escala:** use `clamp()` para títulos; não criar tamanhos fixos novos.
**Espaçamento:** múltiplos de 4 px.
**Bordas:** 1 px; raio de 3 a 6 px; sombra apenas no modal.

Ao alterar cores, verifique contraste de pelo menos 4,5:1 para texto normal nos dois temas.

---

## 7. Voz e conteúdo

- Primeira pessoa, direta, sem clichês de currículo.
- Explicar o problema antes da ferramenta.
- Resultados sempre ligados a um desafio.
- Nada de “apaixonada por desafios”, “proativa” ou barras de proficiência.
- Cases ilustrativos: selo visível e aviso de dados fictícios.
- Não publicar certificação, nota, prêmio ou experiência sem confirmação.

---

## 8. Adicionar um projeto

1. **Crie o template** antes do `<dialog>`:

```html
<template id="case-NOVO">
  <article class="case">
    <header class="case-head">
      <p class="case-kicker">Categoria · ANO · Projeto-exemplo</p>
      <h2 id="case-title">Título do case</h2>
      <p class="case-summary">Resumo em uma ou duas linhas.</p>
      <dl class="case-meta">
        <div><dt>Escopo</dt><dd>...</dd></div>
        <div><dt>Ferramentas</dt><dd>...</dd></div>
        <div><dt>Período</dt><dd>...</dd></div>
      </dl>
    </header>
    <div class="case-body">
      <section><h3>Contexto</h3><p>...</p></section>
      <section><h3>O desafio</h3><p>...</p></section>
      <section><h3>O que eu fiz</h3><ol><li>...</li></ol></section>
      <section>
        <h3>Resultados</h3>
        <div class="metrics">
          <div><strong>00%</strong><span>Legenda</span></div>
        </div>
        <p class="case-disclaimer">Dados ilustrativos...</p>
      </section>
      <section class="case-learning"><h3>Aprendizado</h3><blockquote>...</blockquote></section>
    </div>
  </article>
</template>
```

2. **Crie o card** dentro de `.projects-grid`:

```html
<article class="project-card" data-category="processos">
  <span class="project-number">04</span>
  <div class="project-main">
    <div class="project-top">
      <span class="chip">Processos</span>
      <span class="project-year">2026</span>
    </div>
    <h3>
      <button class="project-title" type="button" data-case="NOVO" aria-haspopup="dialog">
        Título do case
      </button>
    </h3>
    <p>Resumo curto do card.</p>
    <ul class="tags"><li>Tag</li><li>Tag</li></ul>
  </div>
  <span class="project-arrow" aria-hidden="true">...</span>
</article>
```

3. **Categoria nova?** Adicione um botão em `.filters` com `data-filter="nova"` e use `data-category="nova"` nos cards. Não é preciso mexer no JS.
4. **Numeração:** mantenha a sequência `01`, `02`, `03`…
5. **Teste:** clique no card, abra com teclado (Tab + Enter), feche com ESC, filtre por categoria e confira o mobile.

### 8.1 Editar um case existente

- O texto do modal fica no `<template>` correspondente.
- O resumo do card fica no `<article class="project-card">`.
- Mantenha os dois alinhados; o card é a promessa, o modal é a entrega.
- Se os dados deixarem de ser ilustrativos, remova o selo “Projeto-exemplo” do card, do kicker e o `.case-disclaimer`.

---

## 9. Editar dados pessoais

| Dado | Onde está |
| --- | --- |
| Nome | `<title>`, Hero, footer, JSON-LD, `spec.md` |
| Curso, semestre, instituição | Hero, Sobre, Formação, JSON-LD |
| Cidade | Hero, Sobre, JSON-LD |
| E-mail | Hero (ficha), Contato, footer? e `data-copy` |
| Links (LinkedIn, GitHub) | LinkedIn pendente; GitHub: `https://github.com/beatrizpitton` |
| Foto | Ainda não existe; adicionar em Sobre com `alt` descritivo |
| CV | Ainda não existe; ver seção 12 |

Ao trocar o e-mail, atualize **todos** os lugares: link `mailto:`, texto visível, `data-copy`, JSON-LD e `spec.md`.

---

## 10. Acessibilidade — checklist rápido

- [ ] Todo botão tem `type="button"` quando não é submit.
- [ ] Todo ícone decorativo tem `aria-hidden="true"`.
- [ ] O modal mantém `aria-labelledby="case-title"` e o `<h2>` clonado.
- [ ] Filtros atualizam `aria-pressed`.
- [ ] Menu mobile atualiza `aria-expanded` e `aria-label`.
- [ ] O foco volta ao gatilho ao fechar o modal.
- [ ] Nenhum texto usa apenas cor para transmitir significado.
- [ ] Contraste AA nos dois temas.
- [ ] Navegação completa por Tab, Shift+Tab, Enter, Espaço e ESC.
- [ ] `prefers-reduced-motion` continua respeitado.

---

## 11. Performance e SEO

**Orçamento:** ≤ 120 KB sem fontes; nenhuma imagem obrigatória; JS em módulos comentados, sem dependências (≈ 300 linhas).

**Antes de publicar:**

- [ ] `<title>` e meta description corretos.
- [ ] Um único `<h1>`.
- [ ] JSON-LD válido (testar no Rich Results Test).
- [x] Canonical e `og:url` apontam para `https://beatrizpitton.github.io/`.
- [ ] Favicon carregando.
- [ ] Nenhum link relativo quebrado.
- [ ] Lighthouse ≥ 95 nas quatro categorias.

---

## 12. Pendências conhecidas

| Item | Ação |
| --- | --- |
| LinkedIn | Adicionar link em Contato e `sameAs` no JSON-LD |
| Foto | Adicionar em Sobre com `alt` e `loading="lazy"` |
| CV em PDF | Criar `assets/cv.pdf` e transformar o CTA secundário em download |
| Formspree | Criar conta e preencher `FORM_ENDPOINT` no JS |
| Imagem Open Graph | Opcional: criar `assets/og-image.png` e a meta `og:image` |
| Projetos reais | Substituir os três templates e remover o selo de exemplo |
| Certificações | Substituir “planejado” por cursos concluídos |

**Ativar o Formspree:** no script, procure `const FORM_ENDPOINT = ""` e insira `https://formspree.io/f/SEU_ID`. O código já envia via `fetch` e mantém o fallback `mailto:` quando vazio.

**Ativar o CV:** adicione `assets/cv.pdf` e troque o botão “Vamos conversar” por um link `href="assets/cv.pdf" download`. Mantenha o contato como CTA secundário.

---

## 13. Definição de pronto

Uma mudança só está pronta quando:

1. Funciona em `file://` e em servidor local.
2. Funciona nos temas claro e escuro.
3. Funciona em 360 px e 1440 px.
4. Passa no checklist de acessibilidade.
5. Não adiciona dependências externas.
6. Não inventa dados.
7. Foi testada com teclado.
8. O console está limpo.

---

## 14. Deploy

1. Repositório público: `beatrizpitton/beatrizpitton.github.io` (site de usuário).
2. Envie `index.html`, `spec.md` e `AGENTS.md` para a raiz da branch `main`.
3. GitHub → Settings → Pages → Deploy from a branch → `main` / `/ (root)`.
4. Aguarde a publicação e abra `https://beatrizpitton.github.io/`.
5. Ao adicionar LinkedIn, atualize Contato e o `sameAs` do JSON-LD.

Não é necessário `.nojekyll` para esta estrutura. Se adicionar uma pasta com `_` no nome, crie o arquivo vazio `.nojekyll`.

---

## 15. Armadilhas comuns

- **Template sem card ou card sem template:** o botão abre um modal vazio. Confira o par `data-case` ↔ `id`.
- **Duas categorias com o mesmo card:** o filtro mostra o card em ambas; é intencional? Se não, escolha uma.
- **`<h2 id="case-title">` duplicado:** existe em cada template, mas só um é clonado por vez. Não adicione esse ID fora dos templates.
- **Alterar `--accent` para uma cor clara:** o texto branco do botão perde contraste. Teste os dois temas.
- **Adicionar imagem sem `alt`:** quebra a acessibilidade. Descreva a imagem ou marque como decorativa.
- **Usar `innerHTML` para o case:** permite injeção de HTML e quebra o padrão. Clone o template.
- **Remover o aviso de dados ilustrativos:** só faça isso quando os números forem reais e verificados.
- **Editar o e-mail em um só lugar:** o site fica inconsistente. Use a lista da seção 9.
- **Adicionar biblioteca de animação:** aumenta o peso e fere a regra de arquivo único sem dependências.

---

## 16. Contato do projeto

- Titular: Beatriz Pitton
- E-mail: pittonbeatriz2@gmail.com
- GitHub: `https://github.com/beatrizpitton`
- Site: `https://beatrizpitton.github.io/`
- Curso: Administração, 2º semestre — Atitus Educação
- Local: Muliterno, RS

Última atualização: outubro de 2026.
