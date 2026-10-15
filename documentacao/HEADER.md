# Cabeçalho atual do Turismo.com

## Origem e uso opcional

Referência: [portugal.html](../portugal.html), [portugal.css](../portugal.css) e [estilo.css](../estilo.css), na versão local examinada em 14/10/2026. Os arquivos de Portugal já tinham alterações locais antes desta organização; os exemplos refletem essa versão, ainda sem commit.

Este é um **modelo opcional para copiar e adaptar manualmente**. Não é um componente automático: editar este documento não atualiza nenhuma página. A página inicial e as demais páginas ainda usam outro cabeçalho, mais simples.

A documentação está em `documentacao/` porque já existe um arquivo chamado `Docs` na raiz. Ele foi preservado; no Windows, impede criar uma pasta `docs/` no mesmo local.

## Dependências da implementação atual

Na página de Portugal, a ordem é obrigatória: primeiro o CSS global e depois o CSS de Portugal, que sobrescreve regras globais de `header`, `nav` e `nav a`.

```html
<link rel="stylesheet" href="estilo.css">
<link rel="stylesheet" href="portugal.css">
```

O ancestral precisa ter a classe real `pagina-portugal`; atualmente ela está no `body`:

```html
<body class="pagina-portugal">
```

Somente `estilo.css` não reproduz este cabeçalho. Todas as regras específicas abaixo começam com `.pagina-portugal`. O arquivo `portugal.css` completo também contém estilos do conteúdo de Portugal, inclusive de `main`; não é uma folha compartilhada independente.

Não há bibliotecas, fontes externas nem imagens de logotipo para carregar neste bloco: o símbolo ✈ é texto. Para o menu móvel, é necessário o script apresentado ao final deste documento. Não foi encontrado arquivo JavaScript externo no repositório.

## HTML pronto para copiar

Este é o bloco real de `portugal.html`, com caminhos relativos à raiz. Copie uma única vez no início do `body`, antes de `main`.

```html
<header class="cabecalho-principal">
    <div class="barra-cabecalho">

        <!-- Identidade do site -->
        <a href="index.html" class="marca">
            <span class="marca-simbolo">✈</span>

            <span class="marca-texto">
                <strong>TURISMO<span>.COM</span></strong>
                <small>DESCUBRA O MUNDO</small>
            </span>
        </a>

        <!-- Menu de navegação -->
        <nav class="navegacao" aria-label="Menu principal">
            <a href="index.html">Início</a>

            <!-- Lista de países -->
            <div class="grupo-dropdown">
                <button class="botao-dropdown" type="button" aria-expanded="false">
                    Países <span>⌄</span>
                </button>

                <div class="menu-dropdown">
                    <a href="brasil.html">Brasil</a>
                    <a href="portugal.html">Portugal</a>
                    <a href="franca.html">França</a>
                    <a href="espanha.html">Espanha</a>
                    <a href="italia.html">Itália</a>
                    <a href="japao.html">Japão</a>
                    <a href="china.html">China</a>
                </div>
            </div>

            <a href="hospedagem.html">Hospedagem</a>
            <a href="alimentacao.html">Alimentação</a>
            <a href="compras.html">Compras</a>
            <a href="contato.html">Contato</a>
        </nav>

        <!-- Botão para o menu no celular -->
        <button class="botao-menu" type="button" aria-label="Abrir menu" aria-expanded="false">
            <span></span>
            <span></span>
            <span></span>
        </button>

    </div>
</header>
```

Mantenha os nomes das classes e os botões com `type="button"`: o CSS e o JavaScript dependem dessa estrutura. Os links do menu levam somente às sete páginas de países existentes; as novas pastas ainda não são páginas navegáveis.

## Estilos necessários

O bloco abaixo foi transcrito de `portugal.css`, incluindo todas as regras do cabeçalho e suas consultas de mídia. Ele complementa o reset, a fonte Arial e as regras básicas de `estilo.css`.

Se carregar `portugal.css` inteiro, **não precisa copiar novamente este CSS**.

```css
/* ===== CABEÇALHO E MENU ===== */
.pagina-portugal .cabecalho-principal {
    background: #fff;
    border-bottom: 1px solid #dce6e9;
    position: sticky;
    top: 0;
    z-index: 100;
    padding: 0;
    color: #163b50;
}

.pagina-portugal .barra-cabecalho {
    box-sizing: border-box;
    max-width: 1280px;
    min-height: 82px;
    margin: 0 auto;
    padding: 12px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
}

.pagina-portugal .marca {
    display: flex;
    align-items: center;
    gap: 12px;
    flex-shrink: 0;
    color: #163b50;
    text-decoration: none;
}

.pagina-portugal .marca-simbolo {
    display: grid;
    place-items: center;
    width: 42px;
    height: 42px;
    border-radius: 12px;
    background: #00a7b5;
    color: #fff;
    font-size: 24px;
}

.pagina-portugal .marca-texto {
    display: flex;
    flex-direction: column;
    gap: 3px;
}

.pagina-portugal .marca-texto strong { font-size: 17px; }
.pagina-portugal .marca-texto strong span { color: #00a7b5; }
.pagina-portugal .marca-texto small {
    font-size: 9px;
    letter-spacing: 2px;
    color: #667d89;
}

.pagina-portugal .cabecalho-principal .navegacao {
    display: flex;
    flex-wrap: nowrap;
    align-items: center;
    justify-content: flex-end;
    gap: 22px;
    width: auto;
    margin: 0;
    padding: 0;
    background: transparent;
}

.pagina-portugal .cabecalho-principal .navegacao a {
    margin: 0; /* Neutraliza a margem global de nav a */
}

.pagina-portugal .cabecalho-principal .navegacao a,
.pagina-portugal .cabecalho-principal .botao-dropdown {
    box-sizing: border-box;
    color: #163b50;
    font-size: 13px;
    font-weight: 600;
    text-decoration: none;
    line-height: 1.4;
}

.pagina-portugal .cabecalho-principal .navegacao a:hover,
.pagina-portugal .cabecalho-principal .botao-dropdown:hover { color: #00a7b5; }

.pagina-portugal .grupo-dropdown { position: relative; }
.pagina-portugal .botao-dropdown {
    background: transparent;
    border: 0;
    padding: 10px 0;
    cursor: pointer;
}

.pagina-portugal .menu-dropdown {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    min-width: 170px;
    padding: 8px;
    background: #fff;
    border: 1px solid #dce6e9;
    border-radius: 10px;
    box-shadow: 0 8px 24px #163b501a;
}

.pagina-portugal .cabecalho-principal .menu-dropdown a {
    display: block;
    margin: 0;
    padding: 9px 12px;
    min-height: 0;
    border-radius: 6px;
    text-align: left;
}

.pagina-portugal .cabecalho-principal .menu-dropdown a:hover { background: #e0f4f5; }
.pagina-portugal .grupo-dropdown:hover .menu-dropdown,
.pagina-portugal .grupo-dropdown.aberto .menu-dropdown { display: block; }

.pagina-portugal .botao-menu {
    display: none;
    background: transparent;
    border: 0;
    cursor: pointer;
    padding: 8px;
}

.pagina-portugal .botao-menu span {
    display: block;
    width: 25px;
    height: 2px;
    margin: 5px 0;
    background: #163b50;
}

/* Uma coluna compacta no celular e no tablet */
@media (max-width: 980px) {
    .pagina-portugal .botao-menu { display: block; }

    .pagina-portugal .cabecalho-principal .navegacao {
        box-sizing: border-box;
        display: none;
        position: absolute;
        top: 100%;
        left: 16px;
        right: 16px;
        width: auto;
        height: auto;
        max-height: calc(100dvh - 100px);
        overflow-y: auto;
        margin: 0;
        padding: 10px;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: flex-start;
        align-items: stretch;
        gap: 0;
        background: #fff;
        border-radius: 12px;
        box-shadow: 0 8px 24px #163b5020;
    }

    .pagina-portugal .cabecalho-principal .navegacao.aberta { display: flex; }

    .pagina-portugal .cabecalho-principal .navegacao > a,
    .pagina-portugal .cabecalho-principal .navegacao > .grupo-dropdown {
        box-sizing: border-box;
        display: block;
        flex: 0 0 auto;
        width: 100%;
        min-width: 0;
        min-height: 0;
        margin: 0;
    }

    .pagina-portugal .cabecalho-principal .navegacao > a,
    .pagina-portugal .cabecalho-principal .botao-dropdown {
        display: block;
        width: 100%;
        min-height: 0;
        margin: 0;
        padding: 11px 14px;
        text-align: left;
        font-size: 14px;
    }

    .pagina-portugal .menu-dropdown {
        position: static;
        min-width: 0;
        margin: 0 0 4px;
        padding: 4px;
        box-shadow: none;
    }

    .pagina-portugal .cabecalho-principal .menu-dropdown a {
        padding: 9px 14px;
    }
}

@media (max-width: 400px) {
    .pagina-portugal .barra-cabecalho { padding: 12px 16px; gap: 8px; }
    .pagina-portugal .marca { gap: 8px; }
    .pagina-portugal .marca-texto strong { font-size: 15px; }
    .pagina-portugal .marca-texto small { font-size: 8px; letter-spacing: 1.5px; }
}
```

## JavaScript necessário

O código atual está dentro de `portugal.html`, imediatamente antes de `</body>`. Copie o bloco uma única vez, depois do HTML do cabeçalho; ele pressupõe que os quatro elementos selecionados existam.

```html
<script>
    // Controla o menu em celulares e tablets
    const botaoMenu = document.querySelector(".botao-menu");
    const navegacao = document.querySelector(".navegacao");
    const botaoPaises = document.querySelector(".botao-dropdown");
    const grupoPaises = document.querySelector(".grupo-dropdown");

    botaoMenu.addEventListener("click", () => {
        const aberto = navegacao.classList.toggle("aberta");

        botaoMenu.setAttribute("aria-expanded", aberto);
        botaoMenu.setAttribute(
            "aria-label",
            aberto ? "Fechar menu" : "Abrir menu"
        );
    });

    // Abre e fecha a lista de países ao clicar
    botaoPaises.addEventListener("click", () => {
        const aberto = grupoPaises.classList.toggle("aberto");
        botaoPaises.setAttribute("aria-expanded", aberto);
    });
</script>
```

Não inclua esse script em páginas sem o cabeçalho completo: os seletores retornariam `null`. Ele controla uma única instância do cabeçalho por página.

Opcionalmente, em uma página nova, o conteúdo **entre** as tags `<script>` pode ser salvo em um arquivo JavaScript local. Nesse caso, carregue-o com `defer` no `head` ou depois do cabeçalho, e não mantenha também a cópia inline. Nenhum arquivo JavaScript foi criado nesta organização.

## Como o menu se comporta hoje

- Acima de 980 px, a navegação fica visível em linha e o botão de menu fica oculto.
- Até 980 px, a navegação começa oculta. O botão alterna `aberta` em `.navegacao`, atualiza `aria-expanded` e troca o rótulo entre “Abrir menu” e “Fechar menu”.
- O botão “Países” alterna `aberto` em `.grupo-dropdown` e atualiza seu próprio `aria-expanded`.
- O CSS também abre a lista de países ao passar o mouse sobre o grupo. Essa abertura por hover não atualiza `aria-expanded`; o script só o atualiza no clique.
- Até 400 px, há ajustes adicionais no tamanho da marca e nos espaçamentos.

O código atual não implementa fechamento por Escape, clique fora ou seleção de link, nem gerenciamento de foco. Essas melhorias podem ser avaliadas pela equipe em outra etapa.

## Reutilização em uma página nova dentro de paises/

Para uma página futura em `paises/egito/egito.html`, os arquivos da raiz ficam dois níveis acima:

```html
<link rel="stylesheet" href="../../estilo.css">
<link rel="stylesheet" href="../../portugal.css">
```

Esse modo mantém a dependência de `<body class="pagina-portugal">` e carrega também os estilos do conteúdo de Portugal. É útil para reproduzir a referência, mas a equipe deve avaliar os efeitos sobre o conteúdo da nova página.

Para usar somente o cabeçalho e o rodapé, sem depender da folha inteira de Portugal, há outra opção manual para **arquivos novos**:

1. Crie um CSS local do país, por exemplo `paises/egito/egito.css`.
2. Copie o bloco CSS acima e o bloco de [FOOTER.md](FOOTER.md) para esse arquivo.
3. Nessa cópia, substitua o prefixo `.pagina-portugal` por `body`. Assim, por exemplo, `.pagina-portugal .cabecalho-principal` passa a ser `body .cabecalho-principal`. O HTML pode usar `<body>` sem a classe de Portugal.
4. Carregue `../../estilo.css` primeiro e `egito.css` depois. Não carregue também `portugal.css` nesse modo.
5. Copie o HTML e o script reais, ajustando os caminhos somente na página nova.

Esse ajuste é uma sugestão de adaptação, não uma implementação existente nem uma componentização.

Para os links do HTML copiado, todos os destinos da raiz precisam do prefixo `../../`. Exemplos:

```html
<a href="../../index.html" class="marca">
    <span class="marca-simbolo">✈</span>
    <span class="marca-texto">
        <strong>TURISMO<span>.COM</span></strong>
        <small>DESCUBRA O MUNDO</small>
    </span>
</a>
<!-- Dentro da navegação copiada: -->
<a href="../../brasil.html">Brasil</a>
<a href="../../portugal.html">Portugal</a>
<a href="../../contato.html">Contato</a>
```

Aplique o mesmo cuidado aos outros links. Não troque por `../brasil/` nem por `../portugal/`: essas pastas ainda não contêm HTML. Veja o fluxo de trabalho em [ORIENTACOES.md](ORIENTACOES.md).
