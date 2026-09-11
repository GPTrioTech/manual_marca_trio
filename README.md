# Manual de Marca TRIO

Fonte única de verdade da identidade do **Grupo TRIO — Eventos & Gastronomia**.
Reúne o manual de marca, os assets vetoriais e os design tokens usados em peças
de marketing e em desdobramentos digitais.

---

## Conteúdo

| Pasta | O que tem |
|---|---|
| [`manual/`](manual/) | O manual de marca completo, em Markdown |
| [`assets/svg/`](assets/svg/) | 62 SVGs: logotipo, assinaturas de espaços e elementos auxiliares |
| [`fonts/`](fonts/) | Os sete arquivos de fonte e as declarações `@font-face` |
| [`tokens/`](tokens/) | Cores, tipografia e espaçamento como variáveis CSS e JSON |
| [`docs/`](docs/) | Pendências abertas e divergências a resolver |

---

## Uso rápido

**Cores institucionais**

| | HEX | Papel |
|---|---|---|
| Bordô | `#510303` | Primária, títulos, CTAs |
| Bege | `#F9F8F4` | Fundo padrão |
| Preto | `#231D1A` | Texto corrido |
| Cinza | `#BFB8AF` | Superfície e divisória — **nunca texto** |

Os valores acima são RGB, para uso digital. A paleta CMYK/Pantone é **exclusiva de
impresso** e está documentada no [manual](manual/manual-de-marca.md#paleta-de-cores-cmyk).
Não misturar as duas.

**Tipografia**

Miller Headline (títulos) · General Sans (texto corrido) · Chivo Mono (labels e textos pontuais).

**Logotipo**

Sempre horizontal. Área de respiro equivalente a 50% da altura do logo em todos os lados.
Versão preferencial: `assets/svg/TRIO_logo-completo_bordo.svg`.

---

## Fontes

Os sete arquivos estão em [`fonts/`](fonts/), com as declarações `@font-face` prontas
em [`fonts/fontes.css`](fonts/fontes.css). Importar antes dos tokens:

```html
<link rel="stylesheet" href="fonts/fontes.css">
<link rel="stylesheet" href="tokens/tokens.css">
```

**Miller Headline é comercial (Font Bureau).** A licença desktop não cobre uso em web
nem redistribuição pública. Se este repositório permanecer público, remover os arquivos
`MillerHeadline-*` do versionamento — há uma linha pronta e comentada no `.gitignore`.

General Sans é gratuita (Fontshare). Chivo Mono é SIL OFL e pode ser redistribuída,
desde que o `OFL.txt` acompanhe os arquivos — ele ainda não está na pasta.

Detalhes de licença, pesos faltantes e observações técnicas em
[`fonts/README.md`](fonts/README.md).

---

## Visibilidade do repositório

Este repositório contém material estratégico — posicionamento, personas, público-alvo
e manifesto — além de uma fonte de licença comercial. Avaliar se deve permanecer público.

---

## Manutenção

Identidade visual original desenvolvida por **MRJOBIM – Branding Boutique** (2025).
Atualização, refinamentos tipográficos e consolidação do sistema de aplicação por
**Fernanda Barbarini – Consultoria de Branding** (2026).

Antes de usar qualquer valor de cor ou medida em produção, conferir
[`docs/pendencias.md`](docs/pendencias.md) — há divergências conhecidas entre o
manual e os assets originais que ainda aguardam validação.
