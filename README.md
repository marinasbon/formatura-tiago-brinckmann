# Formatura de Tiago Brinckmann

Site de uma página (RSVP) para a formatura em Direito do Tiago Brinckmann, PUCRS, 16 de janeiro de 2027.

É um site 100% estático (HTML + CSS + JS, sem backend). A confirmação de presença é enviada pelo WhatsApp (o site monta a mensagem e abre o `wa.me` com o número configurado).

## Estrutura

- `index.html` — página inteira (estilo, markup e script).

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

Depois de editar, só dar commit e push — o GitHub Pages republica automaticamente.

## Deploy: GitHub Pages

O site já está publicado via GitHub Pages, direto da branch `main`:

**https://marinasbon.github.io/formatura-tiago-brinckmann/**

Por ser um site puramente estático, servido pela CDN do GitHub, não existe "modo de espera" — fica sempre ativo, de graça. O único requisito é que o repositório seja público (necessário para Pages grátis).

Qualquer `git push` na branch `main` atualiza o site automaticamente em 1–2 minutos.
