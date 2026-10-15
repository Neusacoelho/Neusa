# Rodapé atual do Turismo.com

## Origem e uso opcional

Referência: o rodapé de [portugal.html](../portugal.html), seus estilos em [portugal.css](../portugal.css) e a base em [estilo.css](../estilo.css), examinados em 14/10/2026. O exemplo reflete a versão local de Portugal, que já tinha alterações antes desta organização.

Este é um **modelo opcional para copiar e adaptar manualmente**, não um componente automático. O rodapé simples das outras páginas continua como está. A documentação foi colocada em `documentacao/` para preservar o arquivo existente `Docs`, que impede criar `docs/` no Windows.

## Dependências

Para reproduzir o rodapé atual em uma página na raiz, mantenha esta ordem no `head`:

```html
<link rel="stylesheet" href="estilo.css">
<link rel="stylesheet" href="portugal.css">
```

As regras específicas dependem de `<body class="pagina-portugal">`. A folha global define reset, fonte, `h2`, `nav a` e `footer`; a folha de Portugal sobrescreve esses estilos no rodapé. Somente `estilo.css` não reproduz o modelo abaixo.

O rodapé não precisa de JavaScript, bibliotecas ou imagens. O ano 2026 é texto fixo no HTML; ele não é atualizado automaticamente.

## HTML pronto para copiar

Copie uma única vez depois de `</main>`. Os caminhos abaixo são os atuais, para uma página na raiz.

```html
<footer class="rodape-principal">
    <div class="rodape-conteudo">

        <!-- Apresentação do projeto -->
        <div class="rodape-sobre">
            <h2>✈ TURISMO<span>.COM</span></h2>
            <p>
                Descubra destinos, culturas e experiências
                incríveis ao redor do mundo.
            </p>
        </div>

        <!-- Links de navegação -->
        <nav class="rodape-coluna" aria-label="Navegação do rodapé">
            <h3>Explorar</h3>
            <a href="index.html">Início</a>
            <a href="portugal.html">Portugal</a>
            <a href="portugal-fotos.html">Galeria de Portugal</a>
        </nav>

        <!-- Serviços -->
        <nav class="rodape-coluna" aria-label="Serviços">
            <h3>Serviços</h3>
            <a href="hospedagem.html">Hospedagem</a>
            <a href="alimentacao.html">Alimentação</a>
            <a href="compras.html">Compras</a>
        </nav>

        <!-- Informações -->
        <nav class="rodape-coluna" aria-label="Informações">
            <h3>Informações</h3>
            <a href="contato.html">Contato</a>
        </nav>

    </div>

    <div class="rodape-inferior">
        <p>© 2026 Turismo.com — Todos os direitos reservados.</p>
        <p>Projeto acadêmico desenvolvido em equipe.</p>
    </div>
</footer>
```

Preserve a marca Turismo.com, as classes e os rótulos de navegação. O texto institucional pode ser revisto em conjunto pela equipe.

## Estilos necessários

Bloco real do rodapé em `portugal.css`, com suas regras responsivas. Se carregar a folha inteira, não duplique este CSS.

```css
/* ===== RODAPÉ TURISMO.COM ===== */

.pagina-portugal .rodape-principal {
    background-color: #163b50;
    color: #ffffff;
    padding: 48px 24px 20px;
    margin-top: 40px;
    text-align: left;
}

.pagina-portugal .rodape-conteudo {
    max-width: 1180px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 2fr repeat(3, 1fr);
    gap: 36px;
}

/* Apresentação do site */
.pagina-portugal .rodape-sobre h2 {
    color: #ffffff;
    font-size: 22px;
    margin-bottom: 14px;
}

.pagina-portugal .rodape-sobre h2 span {
    color: #00c2cf;
}

.pagina-portugal .rodape-sobre p {
    max-width: 280px;
    color: #d4e2e8;
    font-size: 14px;
    line-height: 1.7;
}

/* Colunas de links */
.pagina-portugal .rodape-coluna {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 12px;
    margin: 0;
}

.pagina-portugal .rodape-coluna h3 {
    color: #ffffff;
    font-size: 15px;
    margin-bottom: 6px;
}

.pagina-portugal .rodape-coluna a {
    color: #d4e2e8;
    font-size: 14px;
    font-weight: normal;
    text-decoration: none;
    margin: 0;
}

.pagina-portugal .rodape-coluna a:hover {
    color: #00c2cf;
    text-decoration: underline;
}

/* Direitos autorais */
.pagina-portugal .rodape-inferior {
    max-width: 1180px;
    margin: 36px auto 0;
    padding-top: 20px;
    border-top: 1px solid #456678;
    display: flex;
    justify-content: space-between;
    gap: 12px;
}

.pagina-portugal .rodape-inferior p {
    color: #d4e2e8;
    font-size: 12px;
}

/* Rodapé responsivo */
@media (max-width: 768px) {
    .pagina-portugal .rodape-conteudo {
        grid-template-columns: repeat(2, minmax(0, 1fr));
        gap: 30px;
    }

    .pagina-portugal .rodape-inferior {
        flex-direction: column;
        text-align: center;
    }
}

@media (max-width: 480px) {
    .pagina-portugal .rodape-conteudo {
        grid-template-columns: 1fr;
        gap: 28px;
    }

    .pagina-portugal .rodape-principal {
        padding: 36px 24px 20px;
    }
}
```

O fundo usa azul-marinho `#163b50`, os destaques usam turquesa `#00c2cf` e os títulos usam branco `#ffffff`. Os links e textos secundários usam `#d4e2e8`.

Em telas maiores, a grade tem a apresentação e três colunas de links. Até 768 px, passa a duas colunas e empilha a faixa inferior; até 480 px, passa a uma coluna.

## Como adaptar os links em páginas novas

Os exemplos só devem ser ajustados nas novas páginas em desenvolvimento. Nenhum caminho das páginas atuais foi alterado.

| Destino existente | Página nova na raiz | Página nova em `paises/egito/egito.html` |
| --- | --- | --- |
| Início | `index.html` | `../../index.html` |
| Portugal | `portugal.html` | `../../portugal.html` |
| Galeria de Portugal | `portugal-fotos.html` | `../../portugal-fotos.html` |
| Hospedagem | `hospedagem.html` | `../../hospedagem.html` |
| Alimentação | `alimentacao.html` | `../../alimentacao.html` |
| Compras | `compras.html` | `../../compras.html` |
| Contato | `contato.html` | `../../contato.html` |

Para a seção “Explorar” de uma página futura do Egito, mantenha links para destinos que já existam. Este exemplo pode ser copiado para essa nova página usando a galeria já disponível de Portugal:

```html
<nav class="rodape-coluna" aria-label="Navegação do rodapé">
    <h3>Explorar</h3>
    <a href="../../index.html">Início</a>
    <a href="../../portugal.html">Portugal</a>
    <a href="../../portugal-fotos.html">Galeria de Portugal</a>
</nav>
```

Quando a página do país estiver pronta, a equipe poderá trocar o link de Portugal pelo arquivo local do país, com o nome e o texto correspondentes. Só adicione uma galeria do novo país depois que ela existir. Uma pasta com `.gitkeep` não é uma página e não deve virar destino de navegação.

Para evitar carregar todos os estilos de Portugal em um país novo, copie somente os blocos CSS de cabeçalho e rodapé para o CSS local do país, trocando `.pagina-portugal` por `body` nessa cópia. Carregue a base global antes desse CSS local, com `<body>` simples. O procedimento completo está em [HEADER.md](HEADER.md). Não altere `portugal.css` para fazer essa adaptação.

## Conferência antes de compartilhar

Abra a nova página no navegador, confira todos os links e veja o rodapé em larguras de 768 px e 480 px. Confira também se os textos dos links correspondem aos destinos e se os rótulos `aria-label` continuam descrevendo cada grupo.
