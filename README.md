# J&L Tecnologia — Site institucional

Site estático (HTML + CSS + JS puro, sem build), tema dark com animações: blobs
de fundo em movimento, elementos aparecendo suavemente ao rolar a página,
contadores animados no hero e um carrossel infinito ("marquee") com as
organizações onde a equipe já atuou em projetos.

## Estrutura

```
index.html
styles.css
script.js
```

## Como testar localmente

```bash
python3 -m http.server 8000
```

Depois acesse `http://localhost:8000`. (Também funciona abrindo o `index.html`
direto no navegador, já que não tem build.)

## Como publicar no Vercel

**Opção 1 — sem Git, direto pelo site:**

1. Acesse [vercel.com](https://vercel.com) e faça login.
2. **Add New → Project** → escolha enviar uma pasta (drag and drop) e arraste
   esta pasta.
3. O Vercel detecta sozinho que é um site estático (sem build command, sem
   output directory). Clique em **Deploy**.

**Opção 2 — com GitHub (bom se for atualizar depois):**

```bash
cd jl-tecnologia
git init
git add .
git commit -m "site institucional J&L Tecnologia"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/SEU-REPO.git
git push -u origin main
```

Depois, em [vercel.com](https://vercel.com): **Add New → Project** → importe
esse repositório → Framework Preset **Other** → **Deploy**.

**Opção 3 — Vercel CLI:**

```bash
npm i -g vercel
cd jl-tecnologia
vercel
```

## O que já está configurado

- **WhatsApp**: `wa.me/5511964667068` com mensagem pré-pronta.
- **E-mail**: `jltecnologialtda2020@gmail.com`.
- **Seção "Experiência"**: lista as organizações onde a equipe já atuou em
  projetos (ONU/PNUD, Justiça Federal do Ceará, SEFAZ-RJ, EdenRed, ConectCar,
  Banco Carrefour, CVC, Dotz), com um aviso abaixo deixando claro que isso é
  experiência profissional da equipe em projetos — não contratos diretos da
  J&L. **Importante**: mantenha esse aviso visível se adicionar mais nomes;
  evita qualquer interpretação de que são clientes contratantes diretos.

## Como editar depois

- **Textos**: direto no `index.html`.
- **Lista de organizações (seção "Experiência")**: procure por `marquee-chip`
  no `index.html` — cada organização aparece duas vezes (lista original +
  cópia duplicada, necessária pro loop do carrossel ficar contínuo). Edite
  as duas listas juntas.
- **Cores**: topo do `styles.css`, dentro de `:root { ... }` (`--red`,
  `--navy`, `--blue`, etc.).
- **Números do hero** (6+ anos, 9 organizações, 100%): no `index.html`,
  atributo `data-count` de cada `<span class="hstat-num">`.
- **Velocidade do carrossel**: no `styles.css`, propriedade `animation` de
  `.marquee-track` (hoje `32s` — aumente o número para deixar mais lento).
