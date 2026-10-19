# Base reutilizável do TURISMO.COM

Esta é uma base para páginas novas, em HTML, CSS e JavaScript puros. Os dois modelos de `modelos/`, as três páginas de `template-modelo/` e `teste-modelo/index.html` utilizam cabeçalho e rodapé gerados. Gastronomia de Portugal também utiliza os arquivos compartilhados, mas mantém um rodapé próprio. Não há instalação de pacotes, compilação, bibliotecas ou fontes externas.

## Escolha como começar

| Opção | O que oferece | Quando escolher |
| --- | --- | --- |
| **1 — `modelos/`** | Estrutura básica reutilizável: uma página principal e uma interna genérica. | Quando você quer montar e personalizar seu próprio layout, acrescentando seções aos poucos. |
| **2 — `template-modelo/`** | Exemplo visual completo com página principal, Cultura e Gastronomia, CSS locais e ilustrações. | Quando você prefere partir de páginas prontas para adaptar, ou consultar um exemplo para copiar somente seções e componentes. |

**As duas opções são opcionais e permitem personalização.** Você pode alterar a organização do conteúdo, os cartões, as imagens e os estilos locais na sua cópia. Não é necessário reproduzir todo o exemplo nem usar todas as seções. Preserve a identidade e os componentes compartilhados combinados pela equipe.

Para a opção 1, siga o passo a passo com Egito neste guia. Para a opção 2, consulte o [LEIA-ME do template visual](../template-modelo/LEIA-ME.md), que explica a cópia completa e o reaproveitamento de partes.

## Arquivos e responsabilidades

```text
assets/
├── css/
│   ├── base.css             # Fonte, cores, reset limitado, foco e container
│   ├── componentes.css      # Marca, header, footer, menu, botões e link de salto
│   └── pais.css             # Banner, seções, cartões, artigo e galeria futura
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
documentacao/
├── ESTRUTURA.md             # Este guia
└── REGRESSAO.md             # Conferências e resultados dos testes
```

Abra `modelos/pais-principal.html` ou `template-modelo/index.html` em um navegador, diretamente pelo arquivo ou pelo Live Server iniciado na raiz do repositório. Os dois modelos básicos são navegáveis entre si; o template visual conecta a principal, Cultura e Gastronomia. Os campos genéricos, textos fictícios e avisos devem ser substituídos antes de publicar uma página de país.

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

**Não personalize o miolo de um rodapé com `data-tc-rodape` esperando que ele permaneça após o carregamento:** o script o substitui. O HTML mínimo dentro dele é a alternativa sem JavaScript e deve continuar com links funcionais. As quatro colunas completas dependem do script.

### Consumidores e rodapés personalizados

| Página | Cabeçalho | Rodapé |
| --- | --- | --- |
| `modelos/pais-principal.html` | Gerado por `site.js`. | Gerado, com `data-tc-rodape`. |
| `modelos/pais-interna.html` | Gerado por `site.js`. | Gerado, com `data-tc-rodape`. |
| `template-modelo/index.html`, `cultura.html` e `gastronomia.html` | Gerado por `site.js`. | Gerado, com `data-tc-rodape`, nas três páginas. |
| `teste-modelo/index.html` | Gerado por `site.js`. | Gerado, com `data-tc-rodape`. |
| `paises/portugal/cultura.html` | HTML próprio e script inline. | HTML próprio; não usa o gerador. |
| `paises/portugal/gastronomia.html` | Gerado por `site.js`. | HTML próprio, sem `data-tc-rodape`. |
| Páginas HTML da raiz | Estruturas próprias. | Estruturas próprias; não usam o gerador. |

As novas regras de acabamento usam `.tc-rodape[data-tc-rodape]`. Assim, não mudam os rodapés próprios, mesmo quando eles utilizam classes `tc-`, como em Gastronomia. Os estilos básicos de `.tc-rodape` continuam disponíveis para essas páginas.

Não acrescente `data-tc-rodape` a um rodapé personalizado sem uma migração autorizada: isso fará o script substituir seu conteúdo. Preserve também as classes e o CSS local dessas páginas. Cultura é a referência visual; não é uma cópia funcional dos novos modelos e suas folhas antigas não devem ser carregadas para obter o rodapé novo.

Ao alterar o gerador, confira os dois modelos básicos, as três páginas do template visual, `teste-modelo/index.html` e o cabeçalho de Gastronomia de Portugal. Ao alterar o CSS compartilhado, compare também Cultura e Gastronomia de Portugal para confirmar a preservação dos rodapés locais. Atualize esta lista quando outra página passar a usar a base.

## Opção 1 — Copiar a estrutura básica: exemplo com Egito

Os caminhos abaixo são uma orientação para trabalho futuro. Esta etapa não cria páginas do Egito nem altera a lista de países publicados.

1. Combine com a equipe quem trabalha no país e confira `git status --short` para reconhecer alterações preexistentes.
2. Copie `modelos/pais-principal.html` para `paises/egito/egito.html`.
3. Copie `modelos/pais-interna.html` para `paises/egito/cultura.html`, se for desenvolver esse assunto.
4. Crie `paises/egito/egito.css` para personalizações. Crie `cultura.css` somente se a interna precisar de regras próprias.
5. No `head` de ambos os HTML, troque `../assets/` por `../../assets/` e carregue o CSS local por último.
6. Ajuste as classes e os atributos do `body`, conforme o exemplo abaixo.
7. Atualize também os links básicos, o caminho de navegação, os cartões e os links de retorno. Eles não são reescritos pelo script.
8. Substitua título, descrição, textos e dados; remova o aviso de modelo. Confira fontes, imagens e créditos.
9. Execute a lista de [regressão](REGRESSAO.md). Peça a inclusão no menu comum apenas quando a página estiver pronta e essa integração estiver autorizada.

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
| CSS local | `egito.css` |
| Fotografia local | `imagens/foto-do-destino.jpg` |
| `data-pais-url` | `paises/egito/egito.html` |

Um `href`, `src` ou link básico é relativo ao HTML. Já `url(...)` é relativo ao arquivo CSS que o declara. Os atributos `data-pais-url` e `data-galeria-url` são relativos à raiz indicada por `data-raiz`. Não use `<base>` para corrigir caminhos: mantenha-os explícitos.

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

Para uma galeria futura, `tc-galeria` oferece uma grade adaptável. Ela não substitui nem altera `.galeria` e `.foto-card` das páginas atuais.

## Menu e acessibilidade

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

## Limites desta etapa

Esta padronização do rodapé não migra as páginas da raiz, Cultura ou Gastronomia. Os rodapés personalizados, as imagens, os créditos e o cabeçalho permanecem como estavam. A lista compartilhada de países continua apontando apenas para os sete países já existentes na raiz; nenhuma página publicada recebeu links para os modelos.

O cabeçalho e o rodapé completos dependem de JavaScript. A alternativa sem script conserva os links básicos, não toda a navegação expandida. O ano do rodapé é atualizado pelo script; o HTML básico contém 2026 e exige atualização manual se for reutilizado em outro ano.

Novas migrações, inclusão de países no menu, limpeza de classes antigas e reconciliação de `HEADER.md`, `FOOTER.md` e `ORIENTACOES.md` ficam para uma etapa autorizada separadamente. Esses guias antigos descrevem estruturas próprias; para as duas opções reutilizáveis, siga este documento e o [LEIA-ME de `template-modelo/`](../template-modelo/LEIA-ME.md). Continue usando `documentacao/`: `Docs` já é um arquivo no repositório.
