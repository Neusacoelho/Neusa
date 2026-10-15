# Orientações para a equipe — Turismo.com

## O que foi preparado

Foram criadas pastas para os 13 países, sem mover páginas, imagens, CSS ou outros arquivos existentes. Cada pasta de país contém somente um `.gitkeep`: é um marcador vazio para o Git registrar a pasta, sem efeito no navegador e sem função de página HTML.

A documentação está em `documentacao/`, alternativa escolhida para preservar o arquivo existente `Docs`. No Windows, esse arquivo conflita com uma pasta chamada `docs/`, mesmo com letras minúsculas.

Os exemplos de [HEADER.md](HEADER.md) e [FOOTER.md](FOOTER.md) são **modelos opcionais**, copiados da implementação atual de Portugal. Não são componentes automáticos e não são inseridos nas páginas por nenhum sistema.

## Estrutura atual após a preparação

```text
turismo-com-paginas/
├── index.html
├── estilo.css
├── README.md
├── TAREFAS.md
├── Docs                         (arquivo existente, preservado)
├── Dados                        (arquivo existente, preservado)
├── Galerias                     (arquivo existente, preservado)
├── paginas                      (arquivo existente, preservado)
├── alimentacao.html
├── alimentacao.json
├── compras.html
├── contato.html
├── hospedagem.html
├── hospedagem.json
├── brasil.html / brasil-fotos.html
├── china.html / china-fotos.html
├── espanha.html / espanha-fotos.html
├── franca.html / franca-fotos.html
├── italia.html / italia-fotos.html
├── japao.html / japao-fotos.html
├── portugal.html / portugal-fotos.html
├── portugal.css
├── imagens-portugal/            (imagens e CREDITOS.md preservados)
├── documentacao/
│   ├── HEADER.md
│   ├── FOOTER.md
│   └── ORIENTACOES.md
└── paises/
    ├── africa-do-sul/
    ├── alemanha/
    ├── brasil/
    ├── china/
    ├── egito/
    ├── espanha/
    ├── franca/
    ├── grecia/
    ├── italia/
    ├── japao/
    ├── portugal/
    ├── reino-unido/
    └── taiwan/

Cada pasta de país acima contém um .gitkeep.
```

As barras entre nomes de HTML indicam dois arquivos na mesma pasta. Nenhum arquivo HTML novo foi criado nesta preparação.

| País | Pasta preparada | Página que já existe na raiz |
| --- | --- | --- |
| Brasil | `paises/brasil/` | `brasil.html` |
| China | `paises/china/` | `china.html` |
| Espanha | `paises/espanha/` | `espanha.html` |
| França | `paises/franca/` | `franca.html` |
| Itália | `paises/italia/` | `italia.html` |
| Japão | `paises/japao/` | `japao.html` |
| Portugal | `paises/portugal/` | `portugal.html` |
| Taiwan | `paises/taiwan/` | Ainda não existe |
| Reino Unido | `paises/reino-unido/` | Ainda não existe |
| Grécia | `paises/grecia/` | Ainda não existe |
| Alemanha | `paises/alemanha/` | Ainda não existe |
| África do Sul | `paises/africa-do-sul/` | Ainda não existe |
| Egito | `paises/egito/` | Ainda não existe |

## Como começar

1. Consulte [TAREFAS.md](../TAREFAS.md) e combine com Neusa quem desenvolve cada país.
2. Confira `git status --short` antes de trabalhar, para reconhecer alterações de outros colegas.
3. Para um país que já tem HTML, use o arquivo atual como referência e combine a próxima mudança com a equipe. A pasta nova não substitui a página da raiz. Evite manter duas versões concorrentes sem combinar qual será integrada.
4. Para um país novo, crie uma página com conteúdo real dentro da pasta correspondente quando começar seu desenvolvimento. Não é necessário criar HTML vazio como reserva.
5. Use nomes em minúsculas, sem espaços ou acentos nos caminhos: `africa-do-sul`, `reino-unido`, `grecia`. No conteúdo visível, escreva normalmente: “África do Sul”, “Reino Unido”, “Grécia”.
6. Salve HTML, CSS, JavaScript e Markdown em UTF-8. No HTML, mantenha `lang="pt-BR"`, a declaração de codificação e a configuração da viewport.

## Organização sugerida para arquivos futuros

O exemplo abaixo é uma **sugestão para o desenvolvimento futuro**, não uma lista de arquivos criados nesta etapa:

```text
paises/egito/
├── .gitkeep
├── egito.html
├── egito.css
├── egito-fotos.html       (somente quando houver galeria)
└── imagens/
    ├── piramides.jpg      (somente quando a imagem for adicionada)
    └── CREDITOS.md
```

Mantenha os estilos específicos no CSS do próprio país. Se precisar de JavaScript, crie um arquivo local com propósito claro; para reproduzir apenas o menu de Portugal, o script documentado em HEADER.md já é suficiente.

Não copie imagens de Portugal para outros países só para preencher espaços. Prefira imagens adequadas ao destino, com texto alternativo descritivo, arquivo otimizado e registro de autoria, origem e licença. Os créditos existentes em `imagens-portugal/CREDITOS.md` são preservados; confirme as informações antes de reutilizar esse material.

## Identidade visual e dependências reais

Use como referência o visual de Portugal: turquesa, azul-marinho e branco. A folha global ainda usa azul `#0047ab` em cabeçalhos, rodapés e títulos. Por isso, carregar apenas `estilo.css` não reproduz o visual específico de Portugal.

| Uso observado | Cor |
| --- | --- |
| Marca, botões e destaques | `#00a7b5` |
| Destaques e links no rodapé | `#00c2cf` |
| Títulos, texto da marca e fundo do rodapé | `#163b50` |
| Cabeçalho, cartões e títulos no rodapé | `#ffffff` |
| Texto secundário no rodapé | `#d4e2e8` |

A base usa Arial, sem dependência de fonte externa. Preserve espaçamento confortável, títulos bem organizados, contraste e navegação legível em celular.

Para copiar o visual em uma página nova, escolha um dos modos descritos em HEADER.md:

- **Referência completa:** carregue `estilo.css` e depois `portugal.css`, usando `<body class="pagina-portugal">`. Isso também aplica estilos de conteúdo de Portugal, inclusive de `main`.
- **Adaptação local opcional:** copie somente os blocos CSS do cabeçalho e do rodapé para o novo CSS do país, substitua `.pagina-portugal` por `body` nessa cópia e use `<body>`. Carregue `estilo.css` primeiro e o CSS local depois. Nenhum estilo original deve ser editado para isso.

Não misture os modos. Preserve as classes internas reais do cabeçalho e do rodapé e inclua o script do menu uma única vez, depois dos elementos ou em arquivo externo com `defer`.

## Exemplo de ponto de partida para uma página nova

Este exemplo serve para um futuro arquivo `paises/egito/egito.html`, no modo de adaptação local. Antes de usá-lo, prepare `egito.css` com os dois blocos CSS documentados, trocando o prefixo conforme explicado acima. Os comentários mostram onde colar os blocos completos de HEADER.md e FOOTER.md; **o exemplo sozinho ainda não contém a navegação**.

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Egito — Turismo.com</title>
    <link rel="stylesheet" href="../../estilo.css">
    <link rel="stylesheet" href="egito.css">
</head>
<body>
    <!-- Cole aqui o cabeçalho de HEADER.md com links ajustados para ../../. -->

    <main>
        <h1>Egito</h1>
        <section aria-labelledby="cultura">
            <h2 id="cultura">Cultura</h2>
            <p>A história e o patrimônio do Egito estão ligados ao rio Nilo.</p>
        </section>
        <section aria-labelledby="gastronomia">
            <h2 id="gastronomia">Gastronomia</h2>
            <p>O koshari reúne arroz, lentilhas e massas em uma receita popular.</p>
        </section>
        <section aria-labelledby="pontos-turisticos">
            <h2 id="pontos-turisticos">Pontos turísticos</h2>
            <p>As pirâmides de Gizé e os templos de Luxor são destaques do país.</p>
        </section>
    </main>

    <!-- Cole aqui o rodapé de FOOTER.md com os links ajustados. -->
    <!-- Cole aqui o script completo de HEADER.md, após inserir o cabeçalho. -->
</body>
</html>
```

Desenvolva também curiosidades, moeda e câmbio conforme a divisão de tarefas, verificando as fontes do conteúdo. Não adicione no menu links para arquivos que ainda não existem.

## Caminhos relativos: o que muda nas páginas novas

Os caminhos são resolvidos a partir da localização do HTML, não da pasta em que o editor está aberto. A documentação não muda nenhum caminho atual.

| Recurso | Exemplo em `paises/egito/egito.html` |
| --- | --- |
| CSS global existente | `../../estilo.css` |
| CSS local futuro | `egito.css` |
| Página inicial existente | `../../index.html` |
| Serviços existentes | `../../hospedagem.html`, `../../alimentacao.html`, `../../compras.html`, `../../contato.html` |
| Página de Portugal existente | `../../portugal.html` |
| Galeria de Portugal existente | `../../portugal-fotos.html` |
| Foto nova dentro da própria pasta | `imagens/piramides.jpg` |

As folhas de estilo resolvem seus próprios `url(...)` a partir do arquivo CSS. Uma futura mudança de pasta precisa revisar tanto o HTML quanto o CSS.

Somente **depois de adicionar a imagem** e seus créditos, um trecho como este pode ser usado na página nova:

```html
<figure>
    <img src="imagens/piramides.jpg"
         alt="Pirâmides de Gizé vistas do deserto"
         loading="lazy">
    <figcaption>Pirâmides de Gizé, no Egito.</figcaption>
</figure>
```

## Estado observado e pontos de atenção

Na análise inicial, o branch era `feature/header-turques`, com:

```text
 M portugal.css
 M portugal.html
?? imagens-portugal/lisboa-eletrico.jpg
```

Essas alterações preexistentes foram preservadas. Esta organização não faz commit, push ou merge.

- `Docs`, `Dados`, `Galerias` e `paginas` são arquivos, não diretórios. Não os use como pastas nem os converta sem combinar com a equipe.
- O README descreve uma pasta `imagens/` e uma paleta diferente; a estrutura real tem `imagens-portugal/`, e Portugal usa os tons listados acima. O README foi preservado.
- Há links nos cartões de `portugal.html` para `#conteudo-cultura`, `#conteudo-gastronomia`, `#conteudo-pontos-turisticos` e `#conteudo-curiosidades`, mas esses IDs não estão presentes na página examinada. Eles não foram corrigidos nem devem ser copiados sem criar as seções correspondentes na nova página.
- O cabeçalho de Portugal usa JavaScript inline; não existe um componente ou arquivo JavaScript compartilhado. A galeria de Portugal e as outras páginas ainda têm cabeçalhos e rodapés diferentes.
- `imagens-portugal/CREDITOS.md` informa downloads pendentes e imagens ausentes, embora os arquivos citados já estejam no diretório. A equipe deve conferir essa documentação em uma etapa própria; ela não foi sobrescrita.
- Os novos diretórios não tornam os países acessíveis pelo menu atual. A integração dos novos links deve acontecer quando as páginas estiverem prontas.

## Como conferir o trabalho da sua página

Abra sua página no navegador e confira o console, carregamento de CSS e imagens, todos os links e os destinos das âncoras. Se usar o cabeçalho de Portugal, teste em tela maior que 980 px e em tela menor, acionando os dois botões por clique e por teclado. Confira o rodapé em 768 px e 480 px e a marca em 400 px.

Antes de compartilhar as alterações, use:

```powershell
git status --short
git diff --stat
git diff -- caminho/do/seu-arquivo.html
```

Arquivos novos não aparecem no `git diff` comum; confira-os diretamente e observe os itens `??` no status. Não inclua alterações de colegas por engano. Combine a revisão com Neusa e siga o fluxo de branches do grupo.

## Recomendações para uma migração futura

Estas ações são propostas para outra etapa; **não foram executadas**:

1. Combinar uma estrutura final, nomes dos arquivos, URLs e responsabilidade de cada país com Neusa.
2. Revisar as diferenças entre as páginas e escolher uma referência visual comum para o grupo.
3. Extrair os estilos comuns de cabeçalho e rodapé para uma folha compartilhada, com escopo apropriado, removendo a dependência do nome de Portugal. Manter os estilos de conteúdo em cada país.
4. Avaliar a extração do script do menu para um arquivo compartilhado e melhorias de teclado, foco, fechamento e estado acessível.
5. Decidir como reutilizar o HTML. Copiar blocos manualmente continua sendo possível; uma inclusão automática exigiria um mecanismo escolhido pela equipe. Não há necessidade de adotar React ou outra biblioteca para planejar essa separação.
6. Migrar um país por vez, incluindo sua página, galeria e imagens, revisando cada `href`, `src`, `url(...)` e âncora. Testar também os links que chegam da página inicial e dos serviços.
7. Planejar a continuidade dos endereços antigos conforme a hospedagem e conferir a navegação antes de integrar a mudança.
8. Atualizar README, tarefas, créditos e estes modelos depois de aprovada a nova organização, evitando instruções divergentes.
