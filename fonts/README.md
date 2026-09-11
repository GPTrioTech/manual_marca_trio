# Fontes

Sete arquivos, 264 KB no total. Declarações em [`fontes.css`](fontes.css).

| Arquivo | Família | Peso | Uso |
|---|---|---|---|
| `GeneralSans-Light.woff2` | General Sans | 300 | Texto corrido |
| `GeneralSans-Regular.woff2` | General Sans | 400 | Texto corrido |
| `GeneralSans-Medium.woff2` | General Sans | 500 | Texto corrido, ênfase |
| `MillerHeadline-Light.otf` | Miller Headline | 300 | Títulos |
| `MillerHeadline-LightItalic.otf` | Miller Headline | 300 itálico | Títulos |
| `MillerHeadline-Roman.otf` | Miller Headline | 400 | Títulos |
| `ChivoMono-Regular.ttf` | Chivo Mono | 400 | Labels, overlines, textos pontuais |

---

## Licenças

**Miller Headline — comercial, Font Bureau.**
Os arquivos são `.otf`, formato desktop. A licença desktop **não cobre uso em web**;
servir a fonte num site exige licença web separada. Verificar antes de publicar
qualquer landing page. Não redistribuir estes arquivos fora da organização — o que
inclui deixá-los num repositório público.

**General Sans — gratuita, Fontshare (Indian Type Foundry).**
Uso pessoal e comercial liberado. Redistribuição permitida.

**Chivo Mono — SIL Open Font License 1.1.**
Open source. Pode ser redistribuída, **desde que o arquivo `OFL.txt` acompanhe a fonte**.
Ele não está aqui: copiar do pacote original baixado do Google Fonts para esta pasta.

---

## Lacunas em relação ao manual

**General Sans.** O manual especifica Light, Light Italic, Regular, Italic, Semibold e
Semibold Italic. O pacote tem Light, Regular e Medium — **nenhum itálico e nenhum
Semibold**. Os que faltam estão disponíveis gratuitamente na Fontshare.

**Miller Headline.** O manual lista oito cortes; há três aqui (Light, Light Italic,
Roman). Para peças de marketing os três costumam bastar, já que o uso é de título,
mas não existe nenhum peso mais encorpado disponível.

---

## Observações técnicas

O `GeneralSans-Regular.woff2` tem a tabela de nomes corrompida: a família está gravada
como `false` e o estilo como `Light`. O `usWeightClass` é 400 e os contornos foram
verificados — é de fato o peso Regular, visivelmente distinto do Light e do Medium.
Como o `@font-face` declara o nome da família explicitamente, isso não afeta a
renderização. Só vale saber, caso a fonte apareça com nome estranho em algum
programa de design.

Os `.otf` do Miller Headline pesam cerca de 40 KB cada, contra os ~23 KB de um woff2
equivalente. Converter reduziria o carregamento, mas depende da licença web estar
resolvida.
