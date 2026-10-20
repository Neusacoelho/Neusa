# Regressão da base reutilizável

Este checklist complementa o [guia principal — ESTRUTURA.md](ESTRUTURA.md). Use-o nas páginas que você modificar, para conferir se conteúdo, componentes e navegação continuam funcionando. Não é necessário assumir a manutenção dos países dos colegas nem impor o visual de Portugal às outras páginas.

Uma alteração local exige conferir a página alterada e seus links de ida e volta. Uma alteração compartilhada, quando autorizada, exige combinar com a equipe a conferência dos consumidores afetados. Testar uma página não autoriza modificar seus arquivos.

## Relação atual de páginas e componentes

Os caminhos abaixo partem da raiz do projeto. Cabeçalho gerado significa `header.tc-cabecalho[data-tc-cabecalho]`; rodapé gerado significa `footer.tc-rodape[data-tc-rodape]`. Com a configuração válida, `assets/js/site.js` substitui o conteúdo desses elementos. Componentes próprios permanecem no HTML e não são substituídos.

| Página | Cabeçalho | Rodapé |
| --- | --- | --- |
| `modelos/pais-principal.html` | Gerado. | Gerado; HTML mínimo sem JavaScript. |
| `modelos/pais-interna.html` | Gerado. | Gerado; HTML mínimo sem JavaScript. |
| `template-modelo/index.html` | Gerado. | Gerado; HTML mínimo sem JavaScript. |
| `template-modelo/cultura.html` | Gerado. | Gerado; HTML mínimo sem JavaScript. |
| `template-modelo/gastronomia.html` | Gerado. | Gerado; HTML mínimo sem JavaScript. |
| `teste-modelo/index.html` | Gerado. | Gerado; HTML mínimo sem JavaScript. |
| `portugal.html` | Próprio, com script inline. | Próprio. |
| `portugal-fotos.html` | Gerado. | Gerado; HTML completo de quatro colunas também sem JavaScript. |
| `paises/portugal/cultura.html` | Próprio, com script inline. | Próprio. |
| `paises/portugal/gastronomia.html` | Gerado. | Próprio, sem `data-tc-rodape`. |
| `paises/portugal/pontos-turisticos.html` | Gerado. | Próprio, sem `data-tc-rodape`. |
| `paises/portugal/curiosidades.html` | Gerado. | Gerado; HTML completo de quatro colunas também sem JavaScript. |

São **dez cabeçalhos e oito rodapés gerados**. Essas dez páginas carregam `assets/css/base.css`, `assets/css/componentes.css`, `assets/css/pais.css` e `assets/js/site.js`; as páginas com estilos locais os carregam depois dos compartilhados. Portugal principal e Cultura usam `estilo.css`, `portugal.css` e seus scripts próprios; Cultura também usa `cultura.css` local. Não acrescente marcadores de geração nem troque essas dependências durante uma conferência.

`portugal.html` e `portugal-fotos.html` permanecem na raiz por compatibilidade; as quatro internas estão em `paises/portugal/`. Os modelos básicos têm espaços reservados para fotografias; o template visual usa ilustrações SVG fictícias e a demonstração usa dados fictícios. Esses exemplos não comprovam o conteúdo de um país real.

## Como interpretar os registros

| Situação | O que significa neste documento |
| --- | --- |
| **Recomendado** | Um item do checklist abaixo, a executar quando uma página ou componente for alterado. Não representa aprovação. |
| **Realizado nesta etapa** | Conferência documental dos caminhos, das referências e dos componentes presentes nos arquivos reais. Não foram executados novos testes de navegador. |
| **Histórico** | Os resultados datados de 17/10/2026 e 15/10/2026, preservados ao final com o escopo e as limitações da época. Não aprovam automaticamente as páginas atuais. |
| **Pendente** | Toda verificação de navegador que ainda não foi executada para a versão alterada, inclusive a confirmação das correções recentes de menu e botões nessa nova conferência. |

Ao usar o checklist, registre quais itens foram realizados, os resultados reais e o que ficou pendente. Não copie uma aprovação histórica para um teste novo. A relação atual acima substitui a lista antiga de três consumidores para planejar futuras verificações.

## Como repetir a conferência

Abra as páginas afetadas diretamente no navegador, mantendo a estrutura do projeto. Não há pacote de testes, dependência de desenvolvimento ou compilação para instalar. Para copiar o exemplo visual, consulte também o [LEIA-ME](../template-modelo/LEIA-ME.md).

Antes de trabalhar, reconheça as alterações preexistentes, inclusive arquivos locais novos. Preserve os arquivos dos colegas e não restaure nem inclua mudanças fora do escopo. Alterações em `index.html` da raiz ou na navegação compartilhada dependem de coordenação e autorização da equipe.

Os itens seguintes são **testes recomendados**, não resultados desta atualização documental. Comece por 390, 768 e 1440 px, com e sem JavaScript; depois confira os limites e cenários adicionais pertinentes à mudança.

### Aparência e carregamento

- Teste as páginas afetadas em **390, 768 e 1440 px**, com e sem JavaScript: conteúdo, imagens, cartões, cabeçalho, botões e rodapé.
- Para o rodapé gerado, confira também 480/481 e 768/769 px: uma coluna até 480 px, duas até 768 px e quatro acima disso, com JavaScript. Rodapés próprios devem preservar o comportamento local.
- Para o menu compartilhado e o da principal de Portugal, confira 980/981 px. As larguras 320, 360, 600 e 1280 px usadas nas conferências iniciais continuam úteis como verificações adicionais.
- Confira que a página não exige rolagem horizontal e que textos, cartões e rodapé permanecem legíveis.
- Com JavaScript, até 980 px o botão Menu aparece e a navegação começa fechada no menu compartilhado e na principal de Portugal. A partir de 981 px, a navegação aparece sem esse botão. Sem JavaScript, confira a navegação HTML disponível, sem exigir os painéis interativos.
- Abra os países e confira que os links cabem na tela e podem ser rolados quando necessário.
- Confira turquesa, azul-marinho e branco, foco visível e leitura dos botões.
- Verifique também zoom de 200% no navegador e uma janela baixa, inclusive com o menu aberto.
- No console e na aba Rede (Network), confira que não há erros de JavaScript nem falhas inesperadas de carregamento de CSS, scripts e imagens.
- Diferencie os espaços de fotografia dos modelos básicos, as quatro ilustrações locais do template visual e as fotografias reais de Portugal. Confira imagens no HTML e fundos definidos por `url(...)` no CSS.

### Agrupamentos e preservação dos rodapés

Os itens sobre quatro blocos, links gerados e medidas descrevem o rodapé compartilhado com JavaScript. Para rodapés próprios, compare o comportamento anterior da página, sem exigir conteúdo idêntico nem alterar o trabalho de seu responsável.

- Confira os quatro blocos: TURISMO.COM, Explorar, Serviços e Informações.
- Serviços deve conter somente Hospedagem, Alimentação e Compras. Contato deve estar em Informações e continuar também no cabeçalho.
- Explorar contém Início e o país configurado. Confira uma configuração com `data-galeria-url` válido e outra sem ele; a galeria não deve aparecer quando não estiver configurada.
- No desktop, confira o contêiner de até 1180 px e a proporção `2fr repeat(3, 1fr)`, comparando tipografia, alinhamentos e espaçamentos com Cultura.
- Compare o cabeçalho antes/depois: estrutura, links, foco e comportamento devem permanecer iguais fora das mudanças autorizadas.
- Numa mudança compartilhada autorizada, compare também os rodapés próprios de Gastronomia e Pontos Turísticos: não devem ser substituídos nem sofrer mudanças inesperadas. Portugal principal e Cultura podem servir de comparação visual, sem exigir uma migração.
- Gastronomia e Pontos Turísticos carregam `site.js` para o cabeçalho, mas não têm `data-tc-rodape`. Portugal principal e Cultura não utilizam o gerador. Não adicione marcadores durante o teste.
- Confira que os créditos fotográficos e o conteúdo dessas páginas continuam disponíveis. Não altere seus HTML, CSS ou fotografias para realizar esta conferência.

### Teclado

Os passos de expansão abaixo descrevem o menu compartilhado e o menu corrigido da principal de Portugal. Nos demais componentes próprios, confira o comportamento existente separadamente e registre divergências, sem pressupor que usem a mesma lógica.

1. Recarregue e pressione Tab: “Pular para o conteúdo” deve aparecer com foco visível.
2. Pressione Enter: o foco deve chegar ao `main`.
3. Recarregue. Em tela pequena, percorra com Tab o link de salto, a marca e o botão Menu.
4. Abra Menu com Enter. Tab deve alcançar Início e depois Países.
5. Abra Países com Espaço e avance com Tab pelos links. Shift+Tab deve permitir o caminho de volta.
6. Com foco em um país, Escape fecha a lista e devolve o foco ao botão Países.
7. Outro Escape fecha o menu móvel e devolve o foco ao botão Menu.
8. Com o painel aberto, avance além do último link: o foco deve sair do cabeçalho e os painéis devem fechar.
9. Repita a expansão de Países no desktop. O foco nunca deve ficar preso ou oculto.
10. Percorra os links do rodapé com Tab e Shift+Tab. O foco deve ficar visível, na ordem Explorar, Serviços e Informações, sem links ocultos ou cortados.

Confira o link “Pular para o conteúdo” quando presente: ele deve aparecer ao receber foco e levar ao `main` correspondente. Preserve o indicador de foco de **3 px** nos controles e links, inclusive nos fundos escuros. O destino do salto deve receber foco sem acrescentar uma borda indevida ao conteúdo inteiro.

### Clique, foco e mudança de largura

- Sem abertura prévia por hover, os botões devem alternar a abertura e o fechamento dos painéis com um clique. Na principal de Portugal, o primeiro clique após abrir Países por hover confirma a abertura; o próximo fecha. Confira ambos os caminhos.
- Clique fora do cabeçalho para fechar os painéis.
- Selecione um link e confira seu destino e o fechamento do painel.
- Com foco na navegação desktop, reduza a largura para menos de 981 px: se a navegação for ocultada, o foco deve ir ao botão Menu.
- Com foco no botão Menu, aumente a largura: o foco deve passar para o primeiro link da navegação visível.
- Uma lista de países aberta não deve permanecer aberta após atravessar esse limite.

### Hover e estados acessíveis do menu

- No menu compartilhado de `site.js`, Países abre por botão. Passar o mouse deve permitir o destaque visual dos links, sem abrir um painel independentemente de `aria-expanded`.
- Na principal `portugal.html`, o script próprio aceita hover com mouse e sincroniza o painel com `aria-expanded`. Confira entrada e saída do ponteiro, abertura por clique e fechamento por Escape, inclusive quando o painel foi aberto por hover.
- Se houver foco dentro do submenu, ele não deve desaparecer apenas porque o ponteiro saiu. Escape deve fechar o painel e devolver o foco ao controle correspondente quando apropriado, sem reabertura imediata pelo hover.
- Confira também `aria-controls` com IDs existentes e únicos. Nenhum estado visual deve indicar um painel aberto enquanto seu controle informa `aria-expanded="false"`.
- Cultura mantém uma implementação própria: registre seu comportamento sem atribuir a ela as correções específicas da principal e sem alterá-la durante o teste.

### Botões `tc-botao`

- Confira todos os `tc-botao` presentes nas páginas afetadas, incluindo `tc-botao-contorno`, em 390, 768 e 1440 px, com e sem JavaScript.
- Verifique ausência de sublinhado em normal, hover, focus e visited. Para o estado visitado, abra o destino e retorne à página.
- Teste Tab, Shift+Tab e Enter, preservando o contorno de foco visível de 3 px, cores, dimensões, alinhamento e espaçamento. Enter deve seguir um destino real.
- Na variante preenchida compartilhada, preserve o hover `#008b98`; a variante de contorno mantém seu tratamento próprio. Compare com a aparência anterior da página afetada.
- Confira que links comuns, breadcrumbs, créditos, menus e botões com outras classes mantêm seus estilos próprios. Não interprete um sublinhado legítimo de link comum como defeito do componente.

### Sem JavaScript e com falha do script

Desative JavaScript no navegador e recarregue cada página afetada nas três larguras principais. Diferencie as alternativas existentes:

- Nos modelos básicos, nas três páginas do template e em `teste-modelo/index.html`, a navegação HTML básica, o conteúdo e o rodapé mínimo devem aparecer.
- Os links básicos presentes em cada HTML devem funcionar, incluindo Início, país, interna ou âncoras locais, conforme a página.
- Nesses modelos e exemplos, o rodapé mínimo é intencional: as quatro colunas completas só aparecem com o script. Na Galeria e em Curiosidades de Portugal, o HTML já contém as quatro colunas; elas devem permanecer sem JavaScript.
- Em Portugal principal, confira especialmente os links do cabeçalho em 390 e 768 px: a correção recente mantém a navegação utilizável sem o script inline. Nos demais componentes próprios, registre o resultado real sem presumir que receberam a mesma correção.
- O link de salto e o foco visível devem continuar disponíveis.
- Não deve haver controle ativo que prometa abrir um painel e não funcione; botões ocultos ou desativados devem ser coerentes com a navegação HTML disponível.
- Nas páginas que carregam `assets/js/site.js`, repita bloqueando apenas esse arquivo na aba Network: a alternativa HTML também deve permanecer. Esse bloqueio não testa os scripts inline de Portugal principal ou Cultura.
- Reative JavaScript e retire o bloqueio ao terminar.

### Estrutura e caminhos

- Verifique um `main`, um `h1` e IDs sem duplicação em cada página.
- Confira que cada `aria-controls` aponta para o painel correspondente.
- Compare `aria-expanded` com a visibilidade de cada painel durante os testes.
- Confira os links antes e depois da montagem do cabeçalho e do rodapé.
- Teste a navegação de ida e volta entre os modelos e seus links para o início.
- Confirme que as âncoras internas encontram elementos reais.
- Depois de copiar um modelo para outra pasta, repita tudo: os caminhos do HTML e `data-raiz` precisam acompanhar a nova profundidade.
- Confirme que os modelos não carregam `estilo.css`, `portugal.css`, fontes externas ou bibliotecas.
- Confira `tc-site`, `data-raiz`, `data-pais-nome`, `data-pais-url` e, quando houver galeria existente, `data-galeria-url`. Não confunda o caminho do HTML até a raiz com os caminhos do país e da galeria, que partem da raiz.
- Confira os três CSS compartilhados na ordem base, componentes e país, os CSS locais por último e `site.js` uma única vez, com `defer`, nas páginas que usam a base.
- Verifique descrições alternativas, dimensões e enquadramento das imagens, autoria, licença, fonte, URLs de atribuição e créditos visíveis exigidos. Abra os créditos em `<details>` com mouse e teclado, inclusive sem JavaScript.
- Preserve os destinos existentes de Portugal: principal e Galeria na raiz; Cultura, Gastronomia, Pontos Turísticos e Curiosidades em `paises/portugal/`. Confira também o botão de Pontos Turísticos para `../../portugal-fotos.html` e o retorno da Galeria para `portugal.html`.

## Critério para uma futura migração

Antes de alterar uma página existente, registre sua aparência e navegação e combine a mudança com seu responsável. Não remova classes antigas apenas por não aparecerem no modelo novo: pesquise os consumidores em HTML, CSS e scripts.

Quando a mudança autorizada abranger Portugal inteiro, inclua principal, Cultura, Gastronomia, Pontos Turísticos, Curiosidades e Galeria. A galeria precisa manter suas seis fotos, legendas, créditos e retorno ao país. Distinga problemas preexistentes de regressões introduzidas pela mudança e registre pendências sem alterar páginas fora do escopo.

Uma alteração nos componentes compartilhados exige combinar a conferência de todas as páginas que os utilizam. Uma alteração apenas no CSS local deve verificar as páginas que carregam esse arquivo e confirmar que os seletores permanecem limitados ao escopo previsto.

## Registrar resultados e pendências de uma nova conferência

Informe a data, o navegador, as páginas e versões de arquivos examinadas, as larguras, o funcionamento com e sem JavaScript, os testes efetivamente executados e seus resultados. Marque como **pendente** cada item não executado ou com problema ainda sem solução; explique limitações de ambiente e encaminhe questões fora do escopo ao responsável.

Zoom de 200%, janela baixa, aparelhos físicos, leitores de tela e outros navegadores não devem ser apresentados como aprovados sem verificação. Registre-os como pendentes ou fora do escopo da conferência, conforme o combinado. Não transforme a lista recomendada acima em um relatório de aprovação automática.

Nesta atualização foi feita somente a revisão documental e a conferência estática dos caminhos e componentes. **Nenhum teste de navegador foi reexecutado nesta etapa.** As seções datadas abaixo são registros históricos preservados; suas contagens, limitações e referências à organização da época não descrevem o estado atual.

## Histórico — Validação do rodapé de quatro colunas — 17/10/2026

Executada no Chrome **155.0.8059.84**, em modo headless no Windows. Os testes e capturas ficaram em pasta temporária fora do repositório; não foram adicionadas dependências nem páginas de teste ao projeto.

| Conferência executada | Resultado |
| --- | --- |
| Três consumidores em 390, 480, 481, 768, 769 e 1440 px, com JavaScript, sem JavaScript e com o script bloqueado | 54 cenários aprovados, sem rolagem horizontal ou falhas inesperadas de carregamento. |
| Rodapé gerado | Quatro blocos reais; Contato somente em Informações no rodapé e preservado no cabeçalho. |
| Grade nos limites solicitados | Uma coluna em 390/480 px, duas em 481/768 px e quatro em 769/1440 px; largura máxima de 1180 px. |
| Links e teclado | Destinos locais existentes; Tab e Shift+Tab percorrem o rodapé com foco visível; salto ao `main` funcionando também nas alternativas sem script. |
| Cabeçalho dos três consumidores | Código fora de `montarRodape`, HTML renderizado, estilos e medidas preservados; Enter, Espaço, Tab, Escape e foco ao atravessar 980/981 px aprovados. |
| Carregamento repetido do script | Sem duplicação do rodapé ou dos controles do cabeçalho. |
| Cópias virtuais em `paises/egito/`, sem criar arquivos | Caminhos e links aprovados com e sem JavaScript. Galeria ausente, configurada com arquivo existente e URL externa rejeitada conferidas. |
| Cultura e Gastronomia nas seis larguras | Cabeçalhos, conteúdo e rodapés próprios preservados em HTML, estilos e medidas. Capturas dos rodapés idênticas às anteriores em 390, 768 e 1440 px; teclado e expansão dos créditos aprovados. |
| Preservação do trabalho local | Somente os seis arquivos autorizados mudaram nesta revisão: script, CSS de componentes, dois guias e comentários dos dois modelos. Demais arquivos comparados por conteúdo, inclusive não rastreados, permaneceram intactos. |

As capturas do rodapé gerado em desktop, tablet e celular foram inspecionadas visualmente. Sem JavaScript, continua aparecendo o rodapé HTML mínimo; isso é o comportamento previsto, não uma versão de quatro colunas sem script. A pasta `template-modelo` não foi criada.

Limites desta revisão: não houve validação em aparelhos físicos, leitor de tela, Firefox ou Safari, nem zoom nativo de 200%. O registro abaixo é histórico e não amplia os testes desta revisão.

## Histórico — Resultados iniciais da base — 15/10/2026

Validação realizada em **15/10/2026**, no **Chrome 155 em modo headless no Windows**, com servidor HTTP local temporário e também por abertura direta `file://`.

| Conferência executada | Resultado |
| --- | --- |
| Dois modelos em 320, 360, 600, 768, 980, 981 e 1280 px, com e sem JavaScript | 28 combinações aprovadas, sem rolagem horizontal |
| Visibilidade do menu nos limites de 980 e 981 px | Aprovada |
| Tab, Shift+Tab, Enter, Espaço e Escape enviados ao navegador | Aprovados nos dois modelos |
| Foco visível e salto até o `main`, com e sem JavaScript | Aprovados |
| Foco após Escape e ao atravessar o limite entre celular e desktop | Aprovado |
| Clique externo, seleção de link e saída por Tab | Painéis fecham, sem aprisionar ou ocultar o foco |
| Script bloqueado na rede | Navegação HTML básica e rodapé mínimo preservados |
| Abertura direta por `file://` | Componentes e caminhos funcionando nos dois modelos |
| Carregamento repetido do script | Sem duplicação de controles ou eventos |
| Links, arquivos carregados e âncoras | Destinos locais existentes, sem âncoras ausentes |
| Estrutura renderizada | Um `main`, um `h1` e IDs sem duplicação |
| Exceções JavaScript e falhas inesperadas de carregamento | Nenhuma encontrada |

Os testes de teclado usaram eventos de entrada do navegador; os cliques usaram coordenadas dos controles. A seleção de link no teste de fechamento teve a navegação interceptada temporariamente no navegador para permitir a inspeção do painel fechado. A existência dos destinos foi conferida separadamente.

Capturas do modelo principal em desktop, da interna em celular e da alternativa sem script foram inspecionadas visualmente. O controlador de testes, o perfil temporário do navegador, o relatório e as capturas ficaram fora do repositório; não são dependências da base.

Limites: não houve validação com leitor de tela, Firefox, Safari ou aparelhos físicos. Zoom nativo de 200% e janela baixa permanecem na lista de conferência manual. A aprovação destes modelos não substitui a regressão das páginas existentes quando uma migração for autorizada.
