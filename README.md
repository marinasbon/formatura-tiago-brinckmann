# Formatura de Tiago Brinckmann

Site de uma página (RSVP) para a formatura em Direito do Tiago Brinckmann, PUCRS, 16 de janeiro de 2027.

É um site 100% estático (HTML + CSS + JS, sem backend). A confirmação de presença é enviada pelo WhatsApp (o site monta a mensagem e abre o `wa.me` com o número configurado).

## Estrutura

- `index.html` — página inteira (estilo, markup e script).
- `render.yaml` — Blueprint do Render para deploy como *Static Site*.

## Antes de publicar: preencha o `CONFIG`

Abra `index.html`, procure por `const CONFIG` (perto do fim do arquivo) e preencha:

```js
const CONFIG = {
  whatsapp: "5551999999999", // número do Tiago com DDI+DDD, só dígitos
  prazo: "20 de dezembro",   // prazo para confirmar (ou "" para não mostrar)
  eventos: {
    colacao: { horario: "", local: "", endereco: "" },
    festa:   { horario: "", local: "", endereco: "" }
  }
};
```

Enquanto `horario`/`local` estiverem vazios, o site mostra uma lacuna ("a definir").

## Deploy no Render (sem dormir)

Este é um **Static Site**, não um Web Service — no plano gratuito do Render, Static Sites ficam sempre ativos e não entram em modo de espera (diferente de Web Services free, que "dormem" após inatividade).

Passos:

1. Suba este repositório para o GitHub (veja abaixo).
2. No [dashboard do Render](https://dashboard.render.com), clique em **New** → **Blueprint**.
3. Conecte o repositório `formatura-tiago-brinckmann`. O Render vai detectar o `render.yaml` automaticamente.
4. Confirme a criação — não precisa de build command nem de variáveis de ambiente.
5. Em poucos segundos o site estará no ar em uma URL `https://formatura-tiago-brinckmann.onrender.com` (pode trocar o nome/domínio depois nas configurações do serviço).

Alternativa sem Blueprint: **New** → **Static Site**, aponte para o repo, deixe o *Build Command* vazio e o *Publish Directory* como `./`.
