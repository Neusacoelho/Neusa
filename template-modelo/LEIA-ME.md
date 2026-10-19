# Template de páginas de país — TURISMO.COM

Este exemplo permite consultar, copiar e adaptar páginas completas, sem começar o layout do zero. Textos e ilustrações são fictícios: não descrevem um país real.

A organização visual acompanha as páginas de Portugal, usadas somente como referência. Os arquivos de Portugal não são dependências deste template.

## Qual opção escolher?

| Opção | Quando usar |
| --- | --- |
| **1 — `modelos/`: estrutura básica reutilizável** | Para montar seu próprio layout a partir de uma principal e uma interna genérica, acrescentando o conteúdo aos poucos. Veja o [passo a passo no guia de estrutura](../documentacao/ESTRUTURA.md). |
| **2 — `template-modelo/`: exemplo visual completo** | Para copiar a principal, Cultura e Gastronomia prontas para adaptar, ou usar os arquivos como referência e copiar somente uma seção ou um cartão. Este LEIA-ME explica essa opção. |

**Os exemplos são opcionais e permitem personalização.** Você pode reorganizar seções, retirar blocos, incluir cartões e mudar os estilos locais da sua cópia. Não precisa usar todas as páginas nem manter exatamente o visual demonstrado. Combine com a equipe as mudanças nos elementos compartilhados.

## Arquivos

| Arquivo | Conteúdo |
| --- | --- |
| `index.html` | Banner, resumo com quatro informações, introdução em colunas, quatro cartões e destaque de galeria. |
| `template.css` | Base local das três páginas e estilos específicos da principal. |
| `cultura.html` e `cultura.css` | Banner, introdução com destaque, quatro cartões, patrimônio em fundo escuro, experiências e navegação final. |
| `gastronomia.html` e `gastronomia.css` | Banner, introdução, quatro pratos, três doces, quatro regiões, experiências e navegação final. |
| `imagens/` | Quatro ilustrações SVG locais, reutilizadas sem alterar os arquivos originais. |

Os cartões da principal **não têm imagens**, assim como na principal de Portugal. O destaque de galeria ocupa duas colunas no computador e seu botão abre a ilustração local. Não há uma página separada de galeria. “Pontos turísticos” e “Curiosidades” levam a seções existentes da principal; Cultura e Gastronomia abrem as respectivas páginas completas.

As três páginas carregam `assets/css/base.css`, `componentes.css`, `pais.css` e `assets/js/site.js`. O cabeçalho e o rodapé de quatro colunas são compartilhados. Eles mantêm os links institucionais reais para Início, países, serviços e Contato. O conteúdo fictício está no `<main>` de cada HTML.

## Abrir o exemplo

Abra `template-modelo/index.html` no navegador ou use um servidor local, como o Live Server do editor. Mantenha a pasta dentro do projeto: abrir apenas um HTML isolado não carrega os estilos compartilhados.

Os cartões abrem Cultura e Gastronomia. Nas internas, as migalhas e “Voltar ao País” retornam à principal do template. “Ver galeria” e “Explorar o destino” levam ao destaque de galeria da principal.

## Copiar o exemplo completo ou uma página inteira

1. Combine com a equipe um destino novo, por exemplo `paises/meu-pais/`. Confira se ele contém trabalho de alguém antes de copiar.
2. Copie os HTML desejados e seus CSS locais. Todas as páginas precisam de `template.css`. Cultura também precisa de `cultura.css`; Gastronomia, de `gastronomia.css`.
3. Copie `imagens/`. Para começar com as três páginas conectadas, copie todo o conteúdo de `template-modelo/`, incluindo o `LEIA-ME.md`, diretamente para `paises/meu-pais/`. A principal deve ficar em `paises/meu-pais/index.html`, sem uma pasta `template-modelo/` intermediária. Não sobrescreva arquivos existentes.
4. Mantenha `assets/` na raiz do projeto e use os caminhos abaixo para acessá-lo. Para esta opção, não é necessário copiar `estilo.css`, `portugal.css`, os arquivos de Portugal ou os modelos da pasta `modelos/`.
5. Ajuste os caminhos pela tabela abaixo e substitua os textos genéricos.
6. Mantenha inicialmente as classes `tc-site`, `pais-modelo` e `pagina-inicio`, `pagina-cultura` ou `pagina-gastronomia` no `<body>`. Elas ativam os estilos corretos. `pais-modelo` delimita estas demonstrações; não é o nome do país. Você pode trocá-la, por exemplo, por `pais-egito`, desde que atualize também todos os seletores correspondentes nos CSS locais copiados. Preserve `tc-site` para os componentes comuns.

Você pode manter os nomes dos arquivos para começar. Se mudar `index.html` para o nome do país, por exemplo `egito.html`, atualize todos os links que apontam para ele, inclusive `index.html#galeria`, e o atributo `data-pais-url` nas três páginas.

Se copiar somente uma interna para um país que já tem página principal, ajuste os links `index.html` e `index.html#galeria` para os destinos existentes desse país. Se copiar somente a principal, copie também as internas vinculadas ou substitua seus links por destinos que já existam. Não deixe links apontando para arquivos que não foram copiados.

### Ajustar caminhos

`../` significa “subir uma pasta”; `../../`, “subir duas pastas”. `cultura.html` procura um arquivo na mesma pasta do HTML atual.

| Configuração | Nesta pasta | Em `paises/meu-pais/` |
| --- | --- | --- |
| `data-raiz` no `<body>` | `../` | `../../` |
| CSS compartilhados no `<head>` | `../assets/css/base.css` (e os outros dois) | `../../assets/css/base.css` (e os outros dois) |
| Script no `<head>` | `../assets/js/site.js` | `../../assets/js/site.js` |
| Links para o início do projeto | `../index.html` | `../../index.html` |
| `data-pais-url` no `<body>` | `template-modelo/index.html` | `paises/meu-pais/index.html` |
| `data-pais-nome` no `<body>` | `Nome do País` | Nome escolhido pela equipe |
| CSS local e imagens | `template.css`, `cultura.css`, `imagens/cidade-modelo.svg` | Iguais, mantendo essa organização |
| Links entre as três páginas | `index.html`, `cultura.html`, `gastronomia.html` | Iguais, mantendo os três HTML juntos |

**Atenção:** `data-pais-url` parte da raiz do projeto, sem `../` no início. `data-raiz` parte do HTML atual. Atualize os atributos nas três páginas copiadas. Os links básicos do cabeçalho e rodapé e o “Início” das migalhas também precisam da distância correta até a raiz.

Não configure `data-galeria-url` com `#galeria`: o gerador aceita um caminho para um HTML existente. Aqui o atributo foi omitido porque não há página separada de galeria. Quando ela existir, configure o caminho relativo à raiz.

## Substituir conteúdo

- Troque os títulos genéricos e os parágrafos Lorem ipsum. Remova `lang="la"` quando escrever em português. Textos de extensão semelhante ajudam a preservar proporções; confira as quebras de linha depois.
- Atualize `<title>`, a descrição em `<meta name="description">`, `data-pais-nome`, as migalhas e os textos alternativos das imagens.
- Mantenha um `<h1>` por página. Seções usam `<h2>`; cartões e itens usam `<h3>`.
- Salve suas novas imagens em `imagens/`. Ajuste `src`, `alt`, `width` e `height`. Os dois últimos indicam as dimensões reais do arquivo, não o tamanho do cartão.
- O fundo do banner de Cultura está em `cultura.css`, na regra `.cultura-banner-foto`. Caminhos `url(...)` partem da pasta do próprio CSS. Os outros banners usam `<img>` no HTML.
- `object-fit: cover` e `background-size: cover` preenchem as áreas sem esticar a imagem, podendo recortar as bordas. Ajuste o enquadramento com `object-position` ou `background-position` no CSS local.
- As ilustrações são exemplos, não fotografias. Ao usar fotos, confirme a licença e registre autor, fonte, licença e adaptações. Nas internas, “Sobre as ilustrações demonstrativas” mostra o local desses créditos.
- Não apague imagens de colegas. Na sua cópia, use nomes novos e descritivos para os seus arquivos.

## Copiar somente uma seção

1. Copie o bloco completo entre os comentários `INÍCIO` e `FIM`, incluindo título, cartões, imagens e fechamento das tags.
2. Preserve os contêineres. Em Cultura, várias seções ficam dentro de `<div class="cultura-container">`. Em Gastronomia, algumas usam `tc-container` na própria seção e outras dentro dela. Evite contêineres duplicados: eles aumentam as margens.
3. No destino, carregue os três CSS compartilhados, depois `template.css` e o CSS da interna correspondente. Não misture `estilo.css` com a base `tc-site` sem revisar a integração.
4. As regras de Cultura dependem de `pais-modelo pagina-cultura` no `<body>`; as de Gastronomia, de `pais-modelo pagina-gastronomia`. Para começar, copie seções entre páginas do mesmo tipo. Para combinar tipos, adapte os seletores no CSS local com a equipe.
5. Não repita um `id` na mesma página. Se renomear um identificador, atualize `aria-labelledby` e os links `href="#..."` relacionados.
6. Ajuste os caminhos das imagens e links. Não crie links para páginas que ainda não existem.

Para iniciantes, manter o CSS local completo é o caminho mais simples. Ao separar somente algumas regras, lembre-se das variáveis de cor, estilos gerais dos títulos e dos blocos `@media` para telas menores.

## Copiar somente um cartão

Por exemplo, para reutilizar o cartão Cultura da principal:

1. Em `index.html` deste template, localize `<article class="explorar-cartao">` com o título Cultura e copie até o `</article>` correspondente.
2. Cole o cartão dentro de `<div class="explorar-cartoes">`, na seção `.explorar-modelo` do `main` da principal do seu país. Se essa seção ainda não existe, use a estrutura abaixo.
3. O destino precisa dos três CSS compartilhados, de `template.css` e das classes `tc-site pais-modelo pagina-inicio` no `body`, como a principal do template. Se você já adaptou o nome `pais-modelo`, use o mesmo nome nos seletores do CSS local. Confira os caminhos para a pasta do país pela tabela acima.
4. Troque o título, o texto, o número e o link pelo conteúdo desejado. O destino `cultura.html` só deve ser usado se essa página existir na pasta do país.

Exemplo para colar **dentro do `main`**, com um único cartão e seu contêiner:

```html
<section class="explorar-modelo" aria-label="Explore o país">
    <div class="explorar-cartoes">
        <article class="explorar-cartao">
            <span class="cartao-numero">01</span>
            <h3>Cultura</h3>
            <p>Conheça as tradições e os costumes do país.</p>
            <a href="cultura.html" class="cartao-link">Conhecer a cultura →</a>
        </article>
    </div>
</section>
```

Para um cartão de Cultura, copie um `<article class="cultura-tradicao">` completo e mantenha a grade `.cultura-tradicoes-grade`, o contêiner `.cultura-container`, `template.css`, `cultura.css` e as classes `tc-site pais-modelo pagina-cultura` no destino. Em Gastronomia, um prato usa `<article class="tc-cartao gastronomia-prato">`, a grade `.gastronomia-pratos-grade`, `template.css`, `gastronomia.css` e `tc-site pais-modelo pagina-gastronomia`. Preserve também os contêineres da seção original. Adapte imagens e IDs, incluindo o `aria-labelledby` que aponta para o título do cartão.

Se a página de destino tem outra estrutura, adapte os seletores no CSS local para aplicar o estilo ao bloco copiado. A troca de classes do `body` pode afetar outros blocos da página; combine a integração com a equipe. Não copie outro `<head>`, `<body>`, cabeçalho ou rodapé para dentro do conteúdo.

## Personalizar sem afetar colegas

Faça ajustes de cor, espaço, imagem e tipografia nos CSS da sua cópia. Os seletores `.pais-modelo.pagina-inicio`, `.pais-modelo.pagina-cultura` e `.pais-modelo.pagina-gastronomia` restringem essas regras ao exemplo.

Não altere sem combinar com a equipe os arquivos compartilhados `assets/css/base.css`, `assets/css/componentes.css`, `assets/css/pais.css` e `assets/js/site.js`, nem o `estilo.css` das páginas antigas. Isso inclui a marca, o cabeçalho, o menu, o rodapé e a lista comum de países e links. Para uma necessidade do seu país, use os HTML e CSS locais copiados; preserve os exemplos originais e os arquivos dos colegas.

Mantenha `data-tc-cabecalho` e `data-tc-rodape`. O `site.js` substitui esses componentes e ativa o menu; não substitui o conteúdo principal. Sem JavaScript, permanecem os links básicos escritos no HTML, mas o menu interativo e as quatro colunas geradas não aparecem.

Cultura e Gastronomia têm estruturas diferentes de propósito: Cultura tem patrimônio com imagem principal, imagem lateral e citação; Gastronomia tem uma sobremesa principal e duas laterais, além de regiões. Os estilos ficam separados para facilitar a manutenção.

## Testar antes de entregar

Abra as três páginas em 390, 768 e 1440 px no modo de dispositivos do navegador e confira:

- Ausência de rolagem horizontal, textos cortados e cartões sobrepostos.
- Imagens carregadas, proporcionais e com textos alternativos coerentes.
- Links da principal para Cultura e Gastronomia e retorno por “Voltar ao País”.
- Botões da galeria, migalhas e âncoras das seções com destinos corretos.
- Menu no celular, lista “Países” e fechamento com Escape.
- Tab, Shift+Tab e Enter com foco visível; o primeiro Tab oferece “Pular para o conteúdo”.
- Rodapé com TURISMO.COM, Explorar, Serviços e Informações: quatro colunas no computador, duas até 768 px e uma até 480 px.
- Abertura das informações das ilustrações com mouse e teclado.
- Conteúdo e links básicos acessíveis com JavaScript desativado.

Confira Console e Rede do navegador. Repita a validação visual após trocar textos ou imagens: o conteúdo pode mudar as alturas dos cartões e banners.
