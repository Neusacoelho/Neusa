# Regressão da base reutilizável

Escopo atual: rodapé de quatro colunas gerado por `assets/js/site.js`, com acabamento em `assets/css/componentes.css`. Consumidores: `modelos/pais-principal.html`, `modelos/pais-interna.html` e `teste-modelo/index.html`. Esta etapa não migra nem corrige as páginas existentes com rodapé próprio.

## Como repetir a conferência

Abra os três consumidores diretamente no navegador ou com Live Server iniciado na raiz do projeto. Não há pacote de testes, dependência de desenvolvimento ou compilação para instalar.

Antes de trabalhar, confira `git status --short` e reconheça todas as alterações preexistentes, inclusive arquivos não rastreados. Preserve os arquivos dos colegas e não restaure nem inclua mudanças fora do escopo.

### Aparência e carregamento

- Para o rodapé, teste os três consumidores em 390, 480, 481, 768, 769 e 1440 px. Confira uma coluna até 480 px, duas até 768 px e quatro acima disso.
- Para a base completa, mantenha também a conferência em 320, 360, 600, 980, 981 e 1280 px.
- Confira que a página não exige rolagem horizontal e que textos, cartões e rodapé permanecem legíveis.
- Até 980 px, o botão Menu aparece e a navegação começa fechada. A partir de 981 px, a navegação aparece sem esse botão.
- Abra os países e confira que os links cabem na tela e podem ser rolados quando necessário.
- Confira turquesa, azul-marinho e branco, foco visível e leitura dos botões.
- Verifique também zoom de 200% no navegador e uma janela baixa, inclusive com o menu aberto.
- No console e na aba Network, confira que não há exceções ou falhas de carregamento dos três CSS e do script.
- Os modelos usam espaços de fotografia sem arquivos fictícios ou requisições externas de imagens.

### Agrupamentos e preservação dos rodapés

- Confira os quatro blocos: TURISMO.COM, Explorar, Serviços e Informações.
- Serviços deve conter somente Hospedagem, Alimentação e Compras. Contato deve estar em Informações e continuar também no cabeçalho.
- Explorar contém Início e o país configurado. Confira uma configuração com `data-galeria-url` válido e outra sem ele; a galeria não deve aparecer quando não estiver configurada.
- No desktop, confira o contêiner de até 1180 px e a proporção `2fr repeat(3, 1fr)`, comparando tipografia, alinhamentos e espaçamentos com Cultura.
- Compare o cabeçalho antes/depois: estrutura, links, foco e comportamento devem permanecer iguais.
- Compare Cultura e Gastronomia nas mesmas seis larguras. O HTML renderizado e o acabamento de seus rodapés próprios devem permanecer inalterados.
- Gastronomia carrega `site.js` para o cabeçalho, mas não tem `data-tc-rodape`. Cultura não utiliza o gerador. Não adicione o marcador durante o teste.
- Confira que os créditos fotográficos e o conteúdo dessas páginas continuam disponíveis. Não altere seus HTML, CSS ou fotografias para realizar esta conferência.

### Teclado

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

### Clique, foco e mudança de largura

- Os dois botões devem abrir e fechar os painéis com um único clique.
- Clique fora do cabeçalho para fechar os painéis.
- Selecione um link e confira seu destino e o fechamento do painel.
- Com foco na navegação desktop, reduza a largura para menos de 981 px: se a navegação for ocultada, o foco deve ir ao botão Menu.
- Com foco no botão Menu, aumente a largura: o foco deve passar para o primeiro link da navegação visível.
- Uma lista de países aberta não deve permanecer aberta após atravessar esse limite.

### Sem JavaScript e com falha do script

Desative JavaScript no navegador e recarregue os três consumidores. Faça isso também em tela pequena.

- A navegação HTML básica, o conteúdo e o rodapé mínimo devem aparecer.
- Os links básicos presentes em cada HTML devem funcionar, incluindo Início, país, interna ou âncoras locais, conforme a página.
- O rodapé mínimo é intencional: as quatro colunas completas só aparecem com o script. Não confunda essa alternativa com uma falha do novo layout.
- O link de salto e o foco visível devem continuar disponíveis.
- Não deve existir botão de expansão sem funcionamento.
- Repita bloqueando apenas `assets/js/site.js` na aba Network: a alternativa básica também deve permanecer.
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

## Critério para uma futura migração

Antes de alterar uma página existente, registre sua aparência e navegação e combine a mudança com seu responsável. Não remova classes antigas apenas por não aparecerem no modelo novo: pesquise os consumidores em HTML, CSS e scripts.

Para Portugal, uma futura conferência deve incluir página principal, cultura, gastronomia e galeria. A galeria precisa manter suas seis fotos, legendas, créditos e retorno ao país. Os problemas preexistentes devem ser distinguidos de regressões introduzidas pela migração.

Uma alteração nos componentes compartilhados exige repetir a conferência em todas as páginas que já os utilizarem. Uma alteração apenas no CSS local deve verificar seu país e confirmar que os seletores permanecem limitados a ele.

## Validação do rodapé de quatro colunas — 17/10/2026

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

## Resultados iniciais da base — 15/10/2026

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
