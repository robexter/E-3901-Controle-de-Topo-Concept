# E-3901 — Refluxo de Topo Concept • V2.0

One-page interativa, responsiva e instalável como PWA por GitHub Pages (HTTPS).

## Como publicar no GitHub Pages

1. Extraia o ZIP; envie **o conteúdo da pasta** (não a própria pasta) para a raiz de um repositório GitHub, ou copie os arquivos preservando a estrutura de caminhos.
2. A raiz precisa conter `index.html`, `style.css`, `app.js`, `manifest.webmanifest`, `sw.js` e a pasta `assets/`.
3. Em Settings → Pages, selecione Deploy from a branch, branch `main`, pasta `/ (root)`. Abra a URL HTTPS fornecida pelo GitHub Pages.
4. Use **Instalar App** quando o navegador oferecer instalação. No iPhone, no Safari, use Compartilhar → Adicionar à Tela de Início.
5. Para publicar correções posteriores, altere o identificador `CACHE` em `sw.js` e recarregue o PWA. Isso evita ficar preso a arquivos antigos; eventualmente pode ser necessário reabrir o app.

## Laboratório

- Ajuste setpoints TIC-249, LIC-163, perturbações térmicas, desequilíbrio do vaso, restrições, limite de rotação, modo da bomba, ganho didático e parâmetros de seleção.
- Comande pausa, reinício, pulsos, velocidade de simulação e cenários de falhas; acompanhe tendências e a animação do fluxograma.
- Abra qualquer lâmpada (✦) para visualizar a explicação técnica em painel lateral. Um painel substitui o anterior.
- Complete a avaliação CIC com 12 questões por tentativa, com ordem reembaralhada e posições das respostas corretas distribuídas entre A/B/C/D.

## Escopo e limitações de segurança

**Protótipo didático não validado, não conectado a controle real.** Os ganhos, inércias, fluxos, restrições, limites e conversão CPV→rotação são simulações hipotéticas; a programação do ZDY-179 reproduz somente a expressão visível no desenho original. RV/RV2 são modelados como saídas dos FICs para ilustrar a seleção. O SP=50% e a entrada/ação do ZDIC-179 não podem ser inferidos integralmente da imagem. A direção da linha FCV-180 deve ser checada no P&ID. Não usar como procedimento de operação ou de intervenção no SDCD.

A imagem original está preservada em `assets/esquema-original.png`.

## Arquivos

- `index.html`: estrutura e conteúdo técnico integral
- `style.css`: responsividade web e mobile
- `app.js`: simulador, tendências, cenários, paineis e quiz
- `sw.js`: cache offline e atualização
- `manifest.webmanifest`: metadados e ícones PWA
- `assets/icon-192.png`, `assets/icon-512.png`: ícones PWA
- `assets/esquema-original.png`: esquema de origem


## Refinamentos V2.0

- Seleção dos modos AUTO/MANUAL individualmente para TIC-249, LIC-163, FIC-179 e FIC-180.
- Rastreamento simplificado das integrais do controlador durante a operação manual (transição didática).
- Falha de válvula travada separando MV de saída do FIC da posição física da FCV.
- Falha no FT-179 com viés de +12 índices e resposta térmica à vazão física.
- Diagnóstico CIC: tabela PV/SP/MV, explicação causal dinâmica e linha do tempo de eventos.
- Dois novos cenários: FCV-179 travada e FIC-180 em manual, total de dez.
- Comparação de hipótese operacional com diagnóstico do cenário e exportação CSV de tendências.
- Tendência separada para X, Y e CPV do ZDY.
- Layout de quatro abas responsivo, cache PWA V2 e tratamento de recursos offline.

Todo valor numérico dinâmico é didático. A lógica CPV=max(RV−70,RV1−60) vem da figura; a conversão em rotação permanece uma hipótese. A arquitetura e as proteções reais precisam de validação documental e em engenharia.

### Atualizar uma PWA já instalada

O cache do service worker utiliza um novo identificador `v2-20261021`. Envie os arquivos da V2 à raiz do repositório substituindo os da V1, aguarde a publicação do GitHub Pages, abra o endereço publicado conectado à Internet e recarregue. O navegador precisa visitar a origem para detectar e ativar a atualização; se ainda mostrar a V1, feche e reabra a PWA e atualize a página no navegador. Evite enviar o ZIP diretamente: extraia os arquivos antes do upload.

O arquivo `E3901_Refluxo_Topo_Concept_V2_PREVIA.html` é uma prévia isolada (não instala PWA), separada do pacote.
