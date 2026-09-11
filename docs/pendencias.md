# Pendências e divergências

Lista consolidada do que ainda precisa de validação ou de novo material.
Conferir antes de usar qualquer valor em produção.

---

## 1. Divergências dentro do manual original

| # | Onde | O que acontece | Status |
|---|---|---|---|
| 1.1 | Paleta RGB | O cinza institucional aparece como `191, 184, 185` e `#BFB8AF`. Os dois não batem: `#BFB8AF` equivale a `191, 184, 175`. | Aberto — adotado o HEX nos tokens |
| 1.2 | Paleta de espaços × assinaturas | A tabela atribui Pantone 4271 U ao Pérgola e 446 U ao Metropolitan. As páginas de assinatura dizem o inverso. | Aberto |
| 1.3 | Redução máxima | A versão com assinatura descritiva aparece com limite de 4,5 mm e a versão isolada com 20 mm, o que parece invertido para um lockup mais complexo. | Aberto |
| 1.4 | Página 39 | Intitulada "Assinatura espaços \| SP Hall", mas todo o conteúdo se refere ao Trivento. | Corrigido na transcrição |
| 1.5 | Emojis aprovados | Os conjuntos da página 20 são imagens no PDF e não foram transcritos com precisão. | Aberto — consultar PDF |

---

## 2. Assets: duas gerações misturadas

O pacote de assets recebido mistura arquivos de duas fases da identidade.

**Agosto/2025 (MR JOBIM).** Cada asset vinha em 5 variantes numeradas. Só três estavam
na paleta atual:

| Variante | Cor | Situação |
|---|---|---|
| 1 | `#510303` bordô | Na paleta |
| 2 | `#B2A26F` dourado | **Fora da paleta** — descartada |
| 3 | `#EFE6D5` creme | **Fora da paleta** — descartada |
| 4 | `#F9F8F4` bege | Na paleta |
| 5 | `#231D1A` preto | Na paleta |

O cinza institucional `#BFB8AF` não existia em nenhum arquivo do pacote.

**Janeiro/2026 (Terraço e Trivento).** Já seguem a lógica nova, com nomes explícitos
de cor (BRANCO / PRETO / BORDO). Usados como referência para o restante.

### 2.1 Cores de assinatura divergentes

As assinaturas coloridas de 2025 usam tons que não correspondem à paleta de espaços
do manual de 2026:

| Espaço | Asset 2025 | Manual 2026 |
|---|---|---|
| Dezenove | `#A0836B` marrom | `#253746` azul profundo |
| Metropolitan | `#563A08` | `#636968` |
| Sky Lounge | `#0E1721` | `#3E4A54` |
| Pérgola | `#564E26` | `#937F70` |
| River One | `#E2DDDB` | `#79776A` |
| One | `#9B9998` | `#ABAEAB` |
| SP Hall | `#675F4A` | `#67604B` |
| Garden | `#354C2C` | `#354C2C` ✓ único que coincide |

Por isso **nenhuma assinatura na cor do próprio espaço foi incluída** em `assets/svg/`.
O sistema vigente é: fundo na cor do espaço, assinatura em branco por cima.

---

## 3. A pedir à agência

- [ ] **Assinaturas de espaço em SVG branco, oficiais.** O pacote original só trazia PNG
      para as assinaturas em branco de oito dos dez espaços. As SVG em `assets/svg/`
      são derivadas por recoloração.
- [ ] **Re-export das assinaturas** na paleta de espaços de 2026, seguindo a nomenclatura
      de Terraço e Trivento.
- [ ] **Versão CMYK dos assets.** O pacote atual é só RGB.

---

## 3.1 Fontes — situação atual

Os arquivos estão em [`../fonts/`](../fonts/). O que ainda falta:

- [ ] **Licença web da Miller Headline.** Os arquivos são `.otf`, formato desktop. Servir
      a fonte em web exige licença separada da Font Bureau. Sem ela, será preciso uma
      serifa didone substituta para digital — o que dividiria a identidade entre canais.
      Enquanto não estiver resolvida, o uso seguro é em peça exportada como imagem ou PDF.
- [ ] **Decidir a visibilidade do repositório.** Miller Headline num repositório público
      é redistribuição não licenciada. Há uma linha pronta e comentada no `.gitignore`
      para excluí-la.
- [ ] **Itálicos e Semibold da General Sans.** O manual especifica Light, Light Italic,
      Regular, Italic, Semibold e Semibold Italic. Há Light, Regular e Medium — nenhum
      itálico e nenhum Semibold. Disponíveis gratuitamente na Fontshare.
- [ ] **`OFL.txt` da Chivo Mono.** A licença exige que acompanhe a fonte. Copiar do
      pacote baixado do Google Fonts para `fonts/`.
- [ ] **Cortes faltantes da Miller Headline.** O manual lista oito; há três
      (Light, Light Italic, Roman). Suficiente para título, mas não há peso encorpado.

Observação técnica: o `GeneralSans-Regular.woff2` tem a tabela de nomes corrompida
(família gravada como `false`, estilo como `Light`). O `usWeightClass` é 400 e os
contornos foram verificados como Regular. Não afeta a renderização, porque o
`@font-face` declara o nome da família explicitamente.

---

## 4. Arquivos derivados neste repositório

Não vieram do pacote original. Foram gerados recolorindo o vetor existente — a forma é
idêntica, só o preenchimento muda. **Validar antes de uso em produção.**

- Todas as versões em `cinza` (logotipo e elementos auxiliares)
- Versões `branco` e `bordo` das assinaturas dos oito espaços de 2025

---

## 5. Correções já aplicadas aos assets

- **viewBox recortado.** Os originais vinham num canvas de 1920×1080 com a arte pequena
  no centro — no logo completo, cerca de 86% do arquivo era espaço vazio.
- **Preto do Terraço e Trivento.** Os arquivos "PRETO" não declaravam cor nenhuma, o que
  os fazia renderizar em preto puro `#000000` em vez do `#231D1A` da marca.
- **Nomenclatura.** Padronizada em `TRIO_[elemento]_[cor].svg`, sem acentos e sem os
  sufixos de exportação soltos (`-01`, `-03`, `-04`, `-05`, `-06`).

---

## 6. Restrições de acessibilidade

- `#BFB8AF` sobre `#F9F8F4` rende cerca de **1,5:1**. O cinza é superfície e divisória,
  nunca texto nem placeholder.
- Texto branco sobre o accent do Terraço (`#C6A992`) rende cerca de **2:1**. Sobre accents
  claros — Terraço, One, Pérgola — usar preto.
- Bordô sobre bege passa com folga.
