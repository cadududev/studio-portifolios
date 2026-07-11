# Studio Portfólios

Coleção de **5 modelos criativos de portfólio** para profissionais que estão começando — pensados para áreas como Direito, Saúde, Marketing, Fotografia e Design (não para desenvolvedores). Inclui uma tela de apresentação, um questionário interativo de 11 passos e um fluxo direto para transformar as respostas do cliente em um portfólio pronto.

## 🚀 Como abrir

Não precisa instalar nada. Basta dar **duplo clique em `index.html`** (abre no navegador). Tudo é HTML/CSS/JS puro, sem build.

## 📁 Estrutura

```
portfolio/
├── index.html                → Tela de apresentação (vitrine + assinatura Cadu)
├── questionario.html         → Questionário interativo (11 passos)
├── README.md                 → Este arquivo
├── Tasks.md                  → Anotações internas / TODOs
├── assets/
│   ├── favicon.svg            → Ícone da aba (quadrado gradiente laranja)
│   └── css/
│       ├── showcase.css        → Estilos da tela de apresentação
│       └── base-cta.css        → CTA fixa "Usar este modelo como base"
└── templates/
    ├── advogado.html          → Modelo "Sóbrio & Confiável"
    ├── nutricionista.html      → Modelo "Fresco & Acolhedor"
    ├── marketing.html          → Modelo "Vibrante & Ousado"
    ├── fotografo.html          → Modelo "Minimal & Galeria"
    └── designer.html           → Modelo "Criativo & Bold"
```

## 🎨 Os 5 modelos

| Modelo | Estilo | Indicado para |
|---|---|---|
| **Advogado** | Sóbrio, marinho + dourado, tipografia clássica | Advogados, contadores, consultores, corretores |
| **Nutricionista** | Leve, verdes naturais, acolhedor | Nutricionistas, terapeutas, personais, psicólogos |
| **Marketing** | Vibrante, gradientes, números de impacto | Social media, publicitários, gestores de tráfego |
| **Fotógrafo** | Minimal, fundo escuro, galeria | Fotógrafos, videomakers, artistas visuais |
| **Designer** | Bold, tipografia gigante, cores fortes | Designers, ilustradores, arquitetos |

## 🧭 Fluxos disponíveis

Existem **dois caminhos** que o cliente pode seguir a partir de `index.html`:

### Caminho A — Personalizado do zero
1. Cliente clica em **"Personalizar o meu portfólio"** ou no card do questionário.
2. Passa pelos 11 passos: área → identidade → estilo → cores → fontes → imagens → seções → objetivos → redes → contato → resumo.

### Caminho B — Usando um modelo como base
1. Cliente clica em um dos 5 modelos e visualiza.
2. Aparece um **CTA fixo no rodapé**: *"Usar este modelo como base →"*.
3. Ao clicar, vai pra `questionario.html?base=<modelo>` que:
   - Mostra um **banner** indicando o modelo escolhido.
   - **Pula 4 passos** que já estão definidos pelo template (área, estilo, cores, fontes).
   - Fica com 7 passos, focados só no conteúdo pessoal do cliente.

Nos dois caminhos, o resultado final é a **mesma tela de resumo** com botões de envio via WhatsApp e e-mail.

## ✨ Recursos do questionário

- **11 passos** com barra de progresso (ou 7 quando entra via `?base=X`).
- **Modo escuro/claro** com preferência salva em `localStorage`.
- Campos condicionais com **"Outra opção"** — em Área, Estilo e Fontes, ao escolher "Outra", aparece uma caixa aberta pra o cliente descrever com as próprias palavras.
- Passo de **imagens** com campo de link condicional (aparece se o cliente já tem fotos): aceita Google Drive, WeTransfer, iCloud, Dropbox, Google Fotos.
- Passo de **redes sociais** com campos separados (Instagram, LinkedIn, YouTube, TikTok, site) + botão **"Adicionar outra rede social"** dinâmico.
- Passo de **seções** com opções pré-definidas + campo aberto pra adicionar seções personalizadas (Blog, FAQ, Prêmios, etc).
- **Múltipla seleção** nos passos de imagens, seções e objetivos.
- **Validação** por passo: o botão "Continuar" só libera com os campos obrigatórios preenchidos.
- **Mensagem final estruturada** em 5 seções temáticas (Sobre mim, Identidade visual, Conteúdo, Redes, Contato), com abertura personalizada *"Olá Cadu! Me chamo X..."* e fechamento acolhedor.
- Campos vazios são automaticamente omitidos da mensagem enviada pra deixar limpa.

## ✏️ Como personalizar um modelo (a partir do briefing)

Cada modelo tem um **bloco editável no topo** do arquivo, marcado assim:

```js
// ✏️ EDITE AQUI — ...
const CONFIG = {
  nome:      "...",
  profissao: "...",
  tagline:   "...",
  // cores, textos, contatos...
};
// FIM DA ÁREA DE EDIÇÃO
```

Edite só esse bloco. **O restante da página se monta sozinho** a partir dele:
- Troque **textos** (nome, frase, sobre, serviços).
- Troque **cores** nos campos `cor...` (use códigos hexadecimais, ex.: `#3f7d5c`).
- Adicione **fotos** colando uma URL (`https://...`) nos campos de imagem. Deixe `""` para usar um placeholder.
- Adicione ou remova itens das listas (`servicos`, `areas`, `projetos`, etc.) livremente.

> ⚠️ Os modelos em `templates/` e o bloco `CONFIG` são **ferramentas suas** (do desenvolvedor) para montar o portfólio. O cliente nunca encosta neles.

## ⚙️ Configurar o destino dos briefings (faça uma vez)

No topo de `questionario.html` há um bloco `DESTINO`:

```js
const DESTINO = {
  whatsapp: "5511913297171",             // seu nº com DDI (vazio esconde o botão)
  email: "carlos.devads@gmail.com"       // e-mail que recebe os briefings
};
```

Já preenchidos com os contatos do Cadu. Ajuste se mudar de número ou e-mail.

## 💬 Contato de dúvidas no `index.html`

O rodapé tem uma CTA *"Possui dúvida? Fale comigo pelo WhatsApp"* que abre o WhatsApp já com uma mensagem pré-definida:

> Olá Cadu! 👋 Vi seu Studio de Portfólios e tenho uma dúvida:

Para trocar o número, edite os dois `href` no `index.html` (topo do hero — no `.dev-brand` — e rodapé — na `.wpp-help`).

## 🎨 Identidade "Cadu — Desenvolvedor"

- **Topo do `index.html`**: cartão estilizado como um editor de código (mock do VS Code) com o nome do Cadu, cursor piscando, e link para WhatsApp.
- **Rodapé**: assinatura discreta com `</>`, nome com gradiente e "DESENVOLVEDOR" em monospace.
- Ambos usam a mesma paleta laranja/âmbar do Studio.

## 🌐 Publicar grátis

Como é só um conjunto de arquivos estáticos, dá pra hospedar de graça em:
- **Netlify** (arraste a pasta em app.netlify.com/drop)
- **GitHub Pages**
- **Vercel**
- **Cloudflare Pages**

## 💡 Dicas de imagens

- Para fotos rápidas de teste: [Unsplash](https://unsplash.com) (clique com o botão direito → copiar endereço da imagem).
- Use imagens otimizadas (largura ~1200px) para a página carregar rápido.
