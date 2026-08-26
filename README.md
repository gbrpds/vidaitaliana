# Quiz → WhatsApp (Assessoria Imobiliária na Itália)

Página única que substitui o link direto do WhatsApp na bio. Em vez da pessoa
editar uma mensagem na mão (e mandar qualquer coisa), ela responde um quiz curto
e o sistema gera **sozinho** um link `wa.me` com a mensagem perfeita, pronta pra enviar.

## Como funciona

1. A pessoa abre o link e responde 4 perguntas (nome, objetivo, cidadania/visto, região).
2. No final aparece a prévia da mensagem e um botão **"Enviar no WhatsApp"**.
3. O WhatsApp abre já com o texto escrito — ela só aperta enviar.

Não tem servidor, não guarda dados em lugar nenhum. É só um arquivo `index.html`.

## Configurar (o que você precisa mexer)

Abra `index.html` e vá até o bloco **`const CONFIG = { ... }`** no topo do `<script>`:

- **`numeroWhatsApp`** — número do Alexandre no formato internacional, só dígitos.
  - Brasil: `55` + DDD + número → ex.: `"5531999998888"`
  - Itália: `39` + número → ex.: `"393401234567"`
  - Enquanto estiver vazio (`""`), a página funciona mas avisa que falta o número.
- **`mentor`** — nome de quem recebe (aparece no "Ciao, ___!").
- **`perguntas`** — dá pra adicionar/remover/reordenar. Cada uma é `tipo: "escolha"`
  (botões) ou `tipo: "texto"` (campo aberto, com sugestões opcionais).
- **`montarMensagem`** — o texto exato que vira a mensagem do WhatsApp.

## Publicar (colocar no ar de graça)

Qualquer hospedagem de site estático serve. Rápidos:

- **GitHub Pages:** Settings → Pages → Branch: `main` (ou a sua) → `/root`. O link fica `https://SEU_USUARIO.github.io/vidaitaliana/`.
- **Netlify / Vercel / Cloudflare Pages:** arraste a pasta ou conecte o repositório.

Depois é só colocar esse link na bio no lugar do link antigo do WhatsApp.

## Testar localmente

Abra o `index.html` no navegador, ou rode um servidor simples:

```bash
python3 -m http.server 8000
# depois acesse http://localhost:8000
```
