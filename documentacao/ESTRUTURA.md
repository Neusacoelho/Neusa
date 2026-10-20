# Base reutilizável do TURISMO.COM

Este é o guia principal para compreender e reutilizar os componentes e modelos do TURISMO.COM. As páginas usam HTML, CSS e JavaScript puros. Não é necessário instalar pacotes, compilar o projeto ou acrescentar bibliotecas e fontes externas para usar os modelos.

Comece pela escolha abaixo, siga o roteiro de cópia e confira a lista de testes ao final. Portugal serve como exemplo de implementação; suas páginas não são um padrão obrigatório para os outros países.

## Escolha como começar

| Opção | O que oferece | Quando escolher |
| --- | --- | --- |
| **1 — `modelos/`** | Estrutura básica reutilizável: uma página principal e uma interna genérica. | Quando você quer montar e personalizar seu próprio layout, acrescentando seções aos poucos. |
| **2 — `template-modelo/`** | Exemplo visual completo com página principal, Cultura e Gastronomia, CSS locais e ilustrações. | Quando você prefere partir de páginas prontas para adaptar, ou consultar um exemplo para copiar somente seções e componentes. |
| **3 — `teste-modelo/`** | Demonstração dos componentes, com um país e dados fictícios. | Quando você quer observar e conferir o cabeçalho, o menu, os botões e o rodapé compartilhados. Não publique essa demonstração como conteúdo de um país real. |

**Os modelos e exemplos são opcionais e permitem personalização.** As opções 1 e 2 são pontos de partida para criar páginas; a opção 3 serve para demonstração e conferência. Na sua cópia, você pode alterar a organização do conteúdo, os cartões, as imagens e os estilos locais. Não é necessário reproduzir todo o exemplo nem usar todas as seções. Preserve os componentes compartilhados combinados pela equipe.

Para a opção 1, siga o passo a passo com Egito neste guia. Para a opção 2, consulte o [LEIA-ME do template visual](../template-modelo/LEIA-ME.md), que explica a cópia completa e o reaproveitamento de partes.

## Organização atual e compatibilidade dos endereços

`portugal.html` e `portugal-fotos.html` permanecem na raiz do projeto para preservar os links publicados e as integrações existentes. Seus estilos locais são `portugal.css` e `portugal-fotos.css`. As páginas internas e seus CSS estão em `paises/portugal/`: Cultura, Gastronomia, Pontos Turísticos e Curiosidades. As fotografias de Portugal continuam em `imagens-portugal/`.

Novos países podem organizar suas páginas em `paises/<nome-do-pais>/`, após combinar o trabalho e os nomes com a equipe. Use nomes em minúsculas, sem espaços ou acentos, com hífens quando necessário. Não é necessário mover ou padronizar páginas existentes de outros colegas. A pasta de um país não altera automaticamente os endereços nem a lista do menu.

## Arquivos e responsabilidades

```text
portugal.html               # Principal: endereço existente preservado
portugal.css                # Estilos da principal e dependência de Cultura
portugal-fotos.html         # Galeria: endereço existente preservado
portugal-fotos.css          # Estilos exclusivos da galeria
paises/portugal/
├── cultura.html / cultura.css
├── gastronomia.html / gastronomia.css
├── pontos-turisticos.html / pontos-turisticos.css
└── curiosidades.html / curiosidades.css
imagens-portugal/           # Fotografias e CREDITOS.md de Portugal
assets/
├── css/
│   ├── base.css             # Fonte, cores, reset limitado, foco e container
│   ├── componentes.css      # Marca, header, footer, menu, botões e link de salto
│   └── pais.css             # Banner, seções, cartões, artigo e grade de galeria
└── js/
    └── site.js              # Montagem do header/footer e controle do menu
modelos/
├── pais-principal.html      # Introdução, dados rápidos e assuntos do país
└── pais-interna.html        # Artigo de cultura ou outro assunto
template-modelo/
├── index.html               # Exemplo visual de página principal
├── template.css             # CSS local usado pelas três páginas
├── cultura.html             # Exemplo completo de Cultura
├── cultura.css              # CSS local de Cultura
├── gastronomia.html         # Exemplo completo de Gastronomia
├── gastronomia.css          # CSS local de Gastronomia
├── imagens/                 # Ilustrações demonstrativas
└── LEIA-ME.md                # Como copiar e adaptar o exemplo visual
teste-modelo/
├── index.html               # Demonstração com conteúdo fictício
└── teste-modelo.css          # Ajustes locais da demonstração
documentacao/
├── ESTRUTURA.md             # Este guia
└── REGRESSAO.md             # Conferências e resultados dos testes
```

Esta árvore resume os arquivos existentes relevantes para os modelos e Portugal. As barras entre um HTML e um CSS indicam dois arquivos na mesma pasta. Os caminhos de países e fotografias usados nos exemplos de cópia adiante são destinos futuros, não arquivos já criados.

Abra `modelos/pais-principal.html`, `template-modelo/index.html` ou `teste-modelo/index.html` diretamente no navegador, mantendo a estrutura do projeto. Os dois modelos básicos são navegáveis entre si; o template visual conecta a principal, Cultura e Gastronomia. Os campos genéricos, textos fictícios e avisos devem ser substituídos antes de publicar uma página de país.

### Papel de cada arquivo compartilhado

| Arquivo | Responsabilidade |
| --- | --- |
| `assets/css/base.css` | Cores em variáveis CSS, fonte, estilos básicos, contêiner de conteúdo e foco visível. Atua em páginas com `tc-site`. |
| `assets/css/componentes.css` | Aparência da marca, cabeçalho, menu, rodapé, botões e link de salto. |
| `assets/css/pais.css` | Estruturas de conteúdo: banner, migalhas, seções, dados rápidos, cartões, artigo e galeria. |
| `assets/js/site.js` | Gera o conteúdo dos cabeçalhos e rodapés marcados, monta seus links e controla o menu acessível. |

Carregue os três CSS nessa ordem e o CSS local da página por último. Carregue `site.js` uma única vez, com `defer`. O CSS local personaliza o conteúdo do seu país; não substitui a base compartilhada.

## Roteiro para criar a página do seu país

1. Combine com a equipe quem trabalha no país e qual será a página principal. Confira se `paises/<nome-do-pais>/` já existe e se contém trabalho de um colega. Preserve também todas as alterações locais existentes.
2. Escolha a estrutura básica de `modelos/` ou o exemplo visual de `template-modelo/`. Use `teste-modelo/` para conferir componentes e comportamento.
3. Se a pasta do país não existir, crie-a dentro de `paises/`. Se já existir, utilize-a conforme o combinado, sem sobrescrever arquivos de outra pessoa.
4. Copie somente os HTML e CSS necessários. No template visual, copie também as ilustrações usadas em `imagens/`; para começar com as três páginas conectadas, siga a opção 2 abaixo. Mantenha `assets/` na raiz.
5. Adapte os nomes dos arquivos, títulos, textos, imagens e créditos. Ao renomear um HTML, atualize todos os links que apontam para ele.
6. Ajuste os caminhos de CSS, JavaScript, imagens e links conforme a profundidade da nova pasta. Confira também os caminhos `url(...)` dentro dos CSS.
7. Confira as classes do `body`, `data-raiz`, `data-pais-nome`, `data-pais-url` e, quando houver uma galeria existente, `data-galeria-url`. Ajuste os links básicos do HTML, as migalhas e os retornos à principal do país e ao início do projeto.
8. Abra as páginas no navegador, teste em larguras de computador e celular, com e sem JavaScript, e siga a lista de regressão deste guia. Só peça a integração no menu quando os destinos existirem.

**Adicionar países ao menu compartilhado ou alterar o `index.html` da raiz exige coordenação com a equipe e autorização para essa integração.** Criar a pasta ou configurar `data-pais-url` não adiciona o país ao menu. Não altere a página inicial, páginas de outros países, exemplos originais ou arquivos compartilhados para fazer sua cópia funcionar.

## Como os componentes funcionam

Cada modelo contém conteúdo completo no `main`, uma navegação HTML básica e um rodapé mínimo. Um script clássico com `defer` executa depois que o HTML foi lido:

1. Confere a classe `tc-site` e o caminho `data-raiz` no `body`.
2. Monta o interior do `header[data-tc-cabecalho]` e do `footer[data-tc-rodape]`.
3. Inicializa os botões e marca o cabeçalho com `data-tc-menu-pronto`.
4. Somente então o CSS passa a recolher os painéis interativos.

O script não usa `fetch`, módulos, servidor de aplicação ou inclusões automáticas de outros HTML. Os componentes estão centralizados em `site.js`. Os dados variáveis entram por `textContent` e atributos do DOM; não são interpolados como HTML.

Se o JavaScript estiver desativado ou não carregar, o HTML básico permanece. O conteúdo, os links entre os modelos, o retorno ao início e o rodapé continuam disponíveis. Essa alternativa é intencionalmente menor que o menu completo; preserve seus links ao personalizar a página.

Use uma instância de cada componente por página e carregue `site.js` uma única vez. O script também verifica se o componente já foi inicializado para evitar repetição de eventos. Ele não atua em páginas sem `tc-site`.

## Rodapé reutilizável de quatro colunas

O rodapé gerado segue o acabamento de Cultura de Portugal: fundo azul-petróleo, conteúdo de até 1180 px e quatro blocos reais no HTML montado pelo script.

| Bloco | Conteúdo |
| --- | --- |
| TURISMO.COM | Marca e apresentação do projeto. |
| Explorar | Início, país configurado no `body` e galeria, quando configurada. |
| Serviços | Hospedagem, Alimentação e Compras. |
| Informações | Contato. |

No desktop, a marca ocupa uma coluna de proporção dupla e as demais têm a mesma largura. Até 768 px, os blocos formam duas colunas; até 480 px, uma. Esses limites são do rodapé: o menu do cabeçalho continua mudando em 980 px. O link Contato permanece também no cabeçalho.

Configure o país usando `data-pais-nome` e `data-pais-url`. Acrescente `data-galeria-url` somente quando a galeria existir. Os endereços e a resolução dos caminhos seguem a tabela deste guia; não adicione links de exemplo para arquivos futuros.

**Não personalize o miolo de um rodapé com `data-tc-rodape` esperando que ele permaneça após o carregamento:** `site.js` substitui o conteúdo desse elemento quando a página está configurada corretamente. Configure os links variáveis pelos atributos do `body`; mantenha os links HTML básicos corretos para a alternativa sem JavaScript.

O que aparece sem JavaScript depende do HTML existente:

- Nos dois modelos básicos, nas três páginas do template visual e em `teste-modelo/index.html`, o rodapé contém uma versão mínima com texto e links. O script a substitui pelas quatro colunas.
- Na Galeria e em Curiosidades de Portugal, o rodapé marcado já contém o HTML completo das quatro colunas. Sem JavaScript, esse conteúdo permanece; com JavaScript, ele também é substituído pelo gerador.
- Rodapés próprios, sem `data-tc-rodape`, não são substituídos. Eles dependem do HTML e dos estilos locais da página.

O cabeçalho marcado também tem seu conteúdo substituído. Nos modelos, preserve a navegação básica escrita no HTML: ela permite usar os links quando o script não carrega.

### Consumidores e rodapés personalizados

| Página | Cabeçalho | Rodapé |
| --- | --- | --- |
| `modelos/pais-principal.html` | Gerado por `site.js`. | Gerado, com `data-tc-rodape`. |
| `modelos/pais-interna.html` | Gerado por `site.js`. | Gerado, com `data-tc-rodape`. |
| `template-modelo/index.html`, `cultura.html` e `gastronomia.html` | Gerado por `site.js`. | Gerado, com `data-tc-rodape`, nas três páginas. |
| `teste-modelo/index.html` | Gerado por `site.js`. | Gerado, com `data-tc-rodape`. |
| `portugal.html` | HTML próprio e script inline. | HTML próprio; não usa o gerador. |
| `portugal-fotos.html` | Gerado por `site.js`. | Gerado, com HTML completo também sem JavaScript. |
| `paises/portugal/cultura.html` | HTML próprio e script inline. | HTML próprio; não usa o gerador. |
| `paises/portugal/gastronomia.html` | Gerado por `site.js`. | HTML próprio, sem `data-tc-rodape`. |
| `paises/portugal/pontos-turisticos.html` | Gerado por `site.js`. | HTML próprio, sem `data-tc-rodape`. |
| `paises/portugal/curiosidades.html` | Gerado por `site.js`. | Gerado, com HTML completo também sem JavaScript. |

São dez páginas com cabeçalho gerado e oito com rodapé gerado: a linha do template visual representa três páginas. Portugal principal e Cultura mantêm componentes próprios e carregam `estilo.css` e `portugal.css`; Cultura também carrega `cultura.css`. As outras páginas de Portugal listadas usam os três CSS compartilhados e seu CSS local. Não deduza a implementação pela pasta: a galeria está na raiz e usa o gerador.

As novas regras de acabamento usam `.tc-rodape[data-tc-rodape]`. Assim, não mudam os rodapés próprios, mesmo quando eles utilizam classes `tc-`, como em Gastronomia. Os estilos básicos de `.tc-rodape` continuam disponíveis para essas páginas.

Não acrescente `data-tc-rodape` a um rodapé personalizado sem uma migração autorizada: isso fará o script substituir seu conteúdo. Preserve também as classes e o CSS local dessas páginas. Cultura é a referência visual; não é uma cópia funcional dos novos modelos e suas folhas antigas não devem ser carregadas para obter o rodapé novo.

Uma alteração autorizada no gerador ou nos CSS compartilhados precisa conferir todos os consumidores indicados na tabela. Gastronomia e Pontos Turísticos usam o cabeçalho gerado, mas preservam rodapés próprios. Portugal principal e Cultura podem ser usados como comparação visual; isso não autoriza migrar seus componentes. Atualize a tabela quando outra página passar a usar a base.

## Opção 1 — Copiar a estrutura básica: exemplo com Egito

Os caminhos abaixo são uma orientação para trabalho futuro. Esta etapa não cria páginas do Egito nem altera a lista de países publicados.

1. Combine com a equipe quem trabalha no país. Verifique o conteúdo de `paises/egito/`; se a pasta não existir, crie-a sem alterar arquivos de outros colegas.
2. Copie `modelos/pais-principal.html` para `paises/egito/egito.html`, somente se isso não sobrescrever trabalho existente.
3. Copie `modelos/pais-interna.html` para `paises/egito/cultura.html`, se for desenvolver esse assunto.
4. Crie `paises/egito/egito.css` para personalizações. Crie `cultura.css` somente se a interna precisar de regras próprias.
5. No `head` de ambos os HTML, troque `../assets/` por `../../assets/` e carregue o CSS local por último.
6. Ajuste as classes e os atributos do `body`, conforme o exemplo abaixo.
7. Atualize também os links básicos, o caminho de navegação, os cartões e os links de retorno. Eles não são reescritos pelo script.
8. Substitua título, descrição, textos e dados; remova o aviso de modelo. Confira fontes, imagens e créditos.
9. Execute a lista **Testar sua cópia e conferir regressões** deste guia. Consulte [REGRESSAO.md](REGRESSAO.md) como complemento e histórico. Peça a inclusão no menu comum apenas quando a página estiver pronta e essa integração estiver autorizada.

Na cópia, troque os links `pais-principal.html` por `egito.html` e `pais-interna.html` por `cultura.html`. Troque os links de Início `../index.html` por `../../index.html`, inclusive na navegação básica, nas migalhas e no rodapé HTML. Não faça uma troca geral de todo `../`: os caminhos têm funções diferentes.

Se copiar somente a principal, substitua os links para a interna por destinos existentes, como uma seção da própria página, ou copie também a interna necessária. Não deixe links para arquivos que você não criou.

Exemplo do `head` em `paises/egito/cultura.html`:

```html
<link rel="stylesheet" href="../../assets/css/base.css">
<link rel="stylesheet" href="../../assets/css/componentes.css">
<link rel="stylesheet" href="../../assets/css/pais.css">
<link rel="stylesheet" href="egito.css">
<!-- Opcional: carregar depois cultura.css, se houver estilos exclusivos. -->
<script src="../../assets/js/site.js" defer></script>
```

Exemplo do `body` da página principal:

```html
<body class="tc-site pais-egito" data-raiz="../../"
      data-pais-nome="Egito" data-pais-url="paises/egito/egito.html">
```

Na página interna, acrescente a classe `pagina-cultura` ao mesmo `body`. Não use a classe `pagina-portugal` para obter o visual compartilhado.

| Configuração | Significado |
| --- | --- |
| `tc-site` | Habilita os novos estilos e componentes. Obrigatória nos modelos. |
| `pais-egito` | Limita as personalizações ao país. O nome é escolhido pelo integrante. |
| `pagina-cultura` | Permite limitar regras a um assunto dentro do país. |
| `data-raiz` | Caminho do HTML até a raiz: `../` nos modelos, `../../` em `paises/egito/`, `./` na raiz. |
| `data-pais-nome` | Texto do link do país no rodapé compartilhado. |
| `data-pais-url` | Caminho da página principal a partir da raiz, sem `/` inicial ou `../`. |
| `data-galeria-url` | Opcional: caminho da galeria a partir da raiz. Só acrescente quando o arquivo existir. |

Os dois atributos de URL aceitam arquivos `.html` com nomes minúsculos, números, hífens e sublinhados, em subpastas opcionais. Não aceitam endereços externos. O script não verifica se o arquivo existe: essa conferência faz parte dos testes.

## Opção 2 — Copiar o template visual

Para começar com as três páginas prontas, copie **o conteúdo** de `template-modelo/` para a pasta do país, por exemplo `paises/egito/`, sem sobrescrever arquivos existentes. Assim, a principal fica em `paises/egito/index.html`, junto de `cultura.html`, `gastronomia.html`, dos três CSS locais, de `imagens/` e do `LEIA-ME.md`. Não crie outra pasta `template-modelo/` dentro da pasta do país.

Nas três páginas copiadas, troque `../assets/` por `../../assets/`, use `data-raiz="../../"`, `data-pais-nome="Egito"` e `data-pais-url="paises/egito/index.html"`. Troque também os links de Início do projeto para `../../index.html`. Os links locais `index.html`, `cultura.html`, `gastronomia.html` e `imagens/...` continuam válidos se os nomes e a organização forem mantidos.

Mantenha inicialmente `tc-site`, `pais-modelo` e a classe `pagina-inicio`, `pagina-cultura` ou `pagina-gastronomia`: os CSS do template dependem delas. Se quiser trocar `pais-modelo` por `pais-egito`, atualize também todos os seletores correspondentes nos CSS da sua cópia. Substitua textos fictícios, títulos, descrições, imagens e créditos conforme o [LEIA-ME](../template-modelo/LEIA-ME.md). Se renomear `index.html` para `egito.html`, ajuste todos os links de retorno e `data-pais-url`.

O LEIA-ME também contém um caminho relativo: depois de copiá-lo para `paises/egito/LEIA-ME.md`, ajuste **nessa cópia** o link `../documentacao/ESTRUTURA.md` para `../../documentacao/ESTRUTURA.md`. O caminho original continua correto em `template-modelo/LEIA-ME.md`.

Se copiar somente uma página ou seção, leve também os CSS locais e as imagens de que ela depende. Todas as páginas do template precisam de `template.css`; Cultura e Gastronomia precisam ainda de seus respectivos CSS. Troque links para páginas não copiadas por destinos existentes. Alterar `data-pais-nome` não altera automaticamente os textos do conteúdo nem os seletores CSS.

## Opção 3 — Conferir a demonstração de componentes

Abra `teste-modelo/index.html` para observar os componentes compartilhados em uma página com dados fictícios. `teste-modelo/teste-modelo.css` contém ajustes exclusivos dessa demonstração, como a faixa de informações. Não é preciso copiar esses arquivos para criar seu país.

A demonstração não publica um novo destino, não adiciona países ao menu e não substitui os testes da sua própria página. Mantenha seu conteúdo fictício identificado; use as opções 1 ou 2 como ponto de partida para o conteúdo real.

## Reutilizar somente um cartão ou uma seção

Na opção 1, copie o `<article class="tc-cartao tc-fluxo">...</article>` completo para uma grade `<div class="tc-cartoes">` dentro do `main` da sua página. Para uma seção, copie de `<section ...>` até o `</section>` correspondente, com seus contêineres necessários. O destino precisa de `tc-site` no `body` e dos três CSS compartilhados apresentados neste guia.

Na opção 2, as seções têm comentários `INÍCIO` e `FIM`. Copie o bloco desejado e mantenha os contêineres, as classes do `body` e os CSS locais de que ele depende. Para copiar apenas um cartão, veja o [exemplo no LEIA-ME](../template-modelo/LEIA-ME.md#copiar-somente-um-cartão). Copiar somente o HTML pode deixar o cartão sem o estilo esperado.

Em qualquer opção, adapte os textos, imagens e links, evite IDs repetidos e confira os destinos de `href="#..."` e `aria-labelledby`. Reaproveitar um bloco não exige copiar outro cabeçalho ou rodapé. Para juntar blocos dos dois tipos de exemplo, adapte as regras no CSS local e confira o resultado em telas pequenas.

## Caminhos sem confusão

| Recurso | Dentro de `paises/egito/cultura.html` |
| --- | --- |
| Página inicial | `../../index.html` |
| Página principal do país | `egito.html` |
| Outra interna do mesmo país | `gastronomia.html`, somente após criá-la |
| CSS compartilhado | `../../assets/css/base.css` |
| Outros CSS compartilhados | `../../assets/css/componentes.css` e `../../assets/css/pais.css` |
| JavaScript compartilhado | `../../assets/js/site.js` |
| CSS local | `egito.css` |
| Fotografia local | `imagens/foto-do-destino.jpg` |
| `data-pais-url` | `paises/egito/egito.html` |

Um `href`, `src` ou link básico é relativo ao HTML. Já `url(...)` é relativo ao arquivo CSS que o declara. Os atributos `data-pais-url` e `data-galeria-url` são relativos à raiz indicada por `data-raiz`. Não use `<base>` para corrigir caminhos: mantenha-os explícitos.

Nesta tabela, `egito.html`, `egito.css`, `gastronomia.html` e a fotografia são exemplos a criar conforme a necessidade. Os quatro arquivos em `assets/` e `index.html` da raiz já existem. Para a opção 2, a principal pode continuar como `index.html` dentro da pasta do país; nesse caso, use `data-pais-url="paises/egito/index.html"` e retornos locais para `index.html`.

## Personalizar estilos sem afetar colegas

Não copie `portugal.css` nem carregue `estilo.css` nos modelos. Carregue apenas as três folhas novas e seus estilos locais, na ordem documentada.

As regras compartilhadas começam por `.tc-site`; as classes dos componentes usam `tc-`. Mantenha esse prefixo reservado para os elementos comuns. No CSS do país, use seu próprio escopo:

```css
/* Somente o conteúdo do Egito; não modifica a marca nem outros países. */
.tc-site.pais-egito .egito-destaque {
    padding: 1.5rem;
    border-left: 4px solid var(--tc-turquesa);
}

/* Apenas a página de cultura do Egito. */
.tc-site.pais-egito.pagina-cultura .egito-destaque {
    background: var(--tc-suave);
}
```

Use `class="egito-destaque"` no elemento correspondente do conteúdo. Evite regras soltas como `header`, `nav a`, `img`, `h2` ou `.pagina-cultura` sem o escopo do país. Mantenha a personalização em `main`; não sobrescreva as cores institucionais no `body` para mudar um único bloco.

As cores principais são turquesa `#00a7b5`, azul-marinho `#163b50` e branco. Links em fundo claro usam turquesa mais escuro para legibilidade; botões turquesa usam texto escuro. As variáveis estão em `base.css`.

Para um link com aparência de botão, use `tc-botao` e, quando quiser a variante contornada, acrescente `tc-botao-contorno`. O componente mantém o texto sem sublinhado nos estados normal, hover, foco e visitado, com indicação de foco visível de 3 px. Preserve as regras de foco ao personalizar. Links comuns, créditos e migalhas mantêm seus próprios estilos; não remova o sublinhado de todos os links da página.

Não altere `assets/css/base.css`, `assets/css/componentes.css`, `assets/css/pais.css` ou `assets/js/site.js` sem combinar com a equipe: eles atendem várias páginas, incluindo o cabeçalho, o menu e o rodapé. O mesmo cuidado vale para `estilo.css`, usado por páginas antigas, e para a lista de países e links institucionais em `site.js`. Faça as personalizações nos HTML e CSS locais da sua cópia, sem editar os exemplos originais nem os arquivos de outros países.

## Conteúdo, imagens e páginas internas

- Mantenha um `h1` por página e uma sequência de títulos coerente.
- Preserve o link “Pular para o conteúdo”, o `id="conteudo"` e o `tabindex="-1"` do `main`.
- Cada `href="#alguma-secao"` precisa de um elemento com esse ID na mesma página.
- Para uma interna de gastronomia, adapte o segundo modelo, incluindo título, descrição, classes e caminho de navegação.
- Não deixe links para páginas futuras. Um `.gitkeep` não é uma página navegável.
- Use imagens do próprio país, otimizadas, em `paises/<pais>/imagens/`.
- Registre autoria, origem, licença e eventuais recortes em `imagens/CREDITOS.md`; apresente os créditos exigidos também na página.

Somente depois de adicionar a fotografia, substitua o espaço de exemplo por uma figura como esta:

```html
<figure>
    <img src="imagens/foto-do-destino.jpg"
         alt="Descrição do lugar mostrado na fotografia"
         width="1200" height="800" loading="lazy">
    <figcaption class="tc-legenda">Local — autoria, origem e licença.</figcaption>
</figure>
```

Para foto de banner, adicione uma imagem `tc-banner-imagem` dentro de `tc-banner`, informe dimensões reais e não use `loading="lazy"` na imagem principal. Uma imagem puramente decorativa pode ter `alt=""`; uma fotografia informativa precisa de descrição e contexto. Verifique a leitura do texto sobre a imagem.

Para uma galeria, `tc-galeria` oferece uma grade adaptável, usada também em `portugal-fotos.html` com ajustes locais para duas colunas. Essa classe não substitui nem altera `.galeria` e `.foto-card` das páginas antigas.

## Menu e acessibilidade

As orientações abaixo descrevem o menu compartilhado de `site.js`, usado pelos modelos. Portugal principal e Cultura têm scripts próprios: servem como referências, mas não precisam ser copiados para usar a base. O menu próprio da principal de Portugal também aceita hover com estado ARIA sincronizado; o menu compartilhado usa seus botões de expansão.

- Acima de 980 px, a navegação aparece em linha. Até 980 px, o botão “Menu” controla sua expansão.
- O botão precede a navegação no HTML. Depois de abri-lo, Tab segue para o primeiro link.
- Enter e Espaço acionam os botões. Tab e Shift+Tab percorrem os links normalmente.
- “Países” abre por botão, sem abertura independente por hover. O estado visual acompanha `aria-expanded`.
- Escape fecha primeiro os países e devolve o foco ao seu botão; outro Escape fecha o menu móvel.
- Clique fora, escolha de link e saída do foco fecham os painéis. Tab pode sair sem aprisionamento de foco.
- Ao atravessar 980 px, o estado é reiniciado e o foco é reposicionado se o controle anterior ficar oculto.
- `aria-controls` aponta para IDs únicos. O destino atual recebe `aria-current="page"` quando a URL corresponde exatamente.
- Foco visível e link de salto também funcionam sem JavaScript.

São controles de expansão de navegação, sem `role="menu"`, navegação obrigatória por setas ou comportamento de janela modal. O limite de 980 px aparece no CSS e no `matchMedia` do script; mantenha ambos sincronizados se a equipe o alterar.

## Testar sua cópia e conferir regressões

Antes de entregar sua página ou propor uma alteração compartilhada:

1. Abra a principal e cada interna em 390, 768 e 1440 px. Confira textos, imagens, cartões, botões e ausência de rolagem horizontal. Após substituir textos ou imagens, repita a conferência.
2. Confira todos os destinos: Início do projeto, principal do país, internas, imagens e âncoras. Teste ida e volta; não basta conferir somente os links gerados por JavaScript.
3. Com JavaScript, teste Menu e Países por clique, Enter e Espaço. Use Tab, Shift+Tab e Escape, confirme o foco visível e compare `aria-expanded` com a visibilidade real dos painéis.
4. Confira o limite do menu em 980 e 981 px e a devolução do foco ao mudar de largura. Confira o rodapé em 480/481 e 768/769 px: são limites diferentes dos do menu.
5. Nos links `tc-botao`, confira normal, hover, foco e a aparência após visitar o destino e retornar. Teste as variantes preenchida e contornada. Preserve cores, tamanhos, espaçamentos, alinhamento e contorno de foco de 3 px; links comuns e créditos devem manter seus estilos.
6. Desative JavaScript no navegador e recarregue. Confira o conteúdo, o link de salto, os links básicos e o rodapé HTML existente. Nos modelos, o rodapé mínimo é esperado; na Galeria e em Curiosidades de Portugal, existe HTML completo. Reative JavaScript ao terminar. Nas páginas com `site.js`, confira também o comportamento quando apenas esse arquivo não carrega.
7. Confira as mensagens do console e os recursos carregados no navegador. Verifique um `h1`, um `main`, IDs únicos, descrições de imagens e destinos dos atributos ARIA. Teste também janela baixa, zoom de 200% e informações expansíveis por teclado, quando existirem.
8. Se a mudança for local, confira sua página e o escopo dos seletores. Se a mudança compartilhada estiver autorizada, confira os dez consumidores de cabeçalho da tabela, incluindo os oito rodapés gerados e os rodapés próprios de Gastronomia e Pontos Turísticos. Preserve as demais páginas.

O arquivo [REGRESSAO.md](REGRESSAO.md) contém uma lista complementar e registros históricos de testes. Os registros datados descrevem o escopo e os resultados da época; não comprovam o resultado de uma cópia nova nem substituem a relação atual de consumidores deste guia. Ao registrar uma nova conferência autorizada, informe páginas, larguras, funcionamento com e sem JavaScript, resultados reais e limitações, sem apagar os registros anteriores.

## Limites, referências e histórico

A base começou como uma estrutura para páginas novas, sem exigir a migração das páginas existentes. Isso explica a convivência de componentes próprios e gerados. A lista compartilhada de países continua apontando para os sete países existentes na raiz; criar modelos e exemplos não publica novos destinos.

O ano do rodapé gerado é atualizado por `site.js`. O HTML básico dos modelos contém 2026 e exige atualização manual se for reutilizado em outro ano sem o script.

Este guia apresenta o fluxo atual de uso dos modelos. O [LEIA-ME de `template-modelo/`](../template-modelo/LEIA-ME.md) detalha o exemplo visual; ao copiá-lo, aplique também o ajuste de caminho indicado na opção 2. Outros documentos podem conter orientações e observações de etapas anteriores. `HEADER.md` e `FOOTER.md` não são arquivos incluídos automaticamente no site nem dependências para executar os modelos; não é necessário copiar código deles para usar `site.js`. Preserve `documentacao/HEADER.md` e combine qualquer revisão documental separadamente.

Mudanças nos componentes, na página inicial, na lista do menu, em endereços publicados ou em páginas de colegas exigem coordenação e autorização próprias. Continue usando `documentacao/`: `Docs` já é um arquivo no repositório. Nenhuma dessas orientações exige mover as páginas atuais, adotar o visual de Portugal em todo o site ou acrescentar ferramentas ao projeto.
