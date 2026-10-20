# Orientações para a equipe — Turismo.com

## Comece pelo guia principal

O guia principal para criar páginas de países é [ESTRUTURA.md](ESTRUTURA.md). Ele explica como escolher e copiar um modelo, adaptar os caminhos e testar a página. O [README](../README.md) apresenta o projeto e os atalhos de entrada. Este documento complementa esses guias com orientações de colaboração e o histórico da organização inicial.

| Opção | Para que serve |
| --- | --- |
| [modelos/](../modelos/) | Estruturas básicas de página principal e interna para desenvolver um layout próprio. |
| [template-modelo/](../template-modelo/) | Exemplo visual completo com principal, Cultura e Gastronomia, reutilizável inteiro ou por seções e cartões. Consulte o [LEIA-ME](../template-modelo/LEIA-ME.md). |
| [teste-modelo/](../teste-modelo/) | Demonstração dos componentes com dados fictícios. Serve para consultar e conferir o comportamento, não para publicar como conteúdo real. |

Os modelos são opcionais e permitem personalização. Portugal é uma referência de implementação, não um layout obrigatório para os demais países.

## Organização atual

Na preparação inicial, foram criadas pastas para os 13 países, sem mover páginas, imagens, CSS ou outros arquivos existentes. Naquele momento, elas continham somente `.gitkeep`, um marcador vazio para o Git registrar a pasta, sem efeito no navegador. Hoje, `paises/portugal/` já contém páginas e estilos; as outras 12 pastas preparadas ainda contêm apenas o marcador. Antes de trabalhar, confira o conteúdo real da pasta para não sobrescrever o trabalho de um colega.

A documentação está em `documentacao/`, alternativa escolhida para preservar o arquivo existente `Docs`. No Windows, esse arquivo conflita com uma pasta chamada `docs/`, mesmo com letras minúsculas.

`portugal.html` e `portugal-fotos.html` permanecem na raiz para preservar os links publicados. Cultura, Gastronomia, Pontos Turísticos e Curiosidades estão em `paises/portugal/`, com seus CSS locais. Novos países podem usar `paises/<nome-do-pais>/`, mediante coordenação. Não é necessário mover ou padronizar páginas existentes dos colegas.

Os documentos [HEADER.md](HEADER.md) e [FOOTER.md](FOOTER.md) são materiais complementares sobre implementações próprias de Portugal. Não são a fonte obrigatória de código para novas páginas. Para começar, use os modelos atuais e as instruções de ESTRUTURA, em vez de copiar manualmente cabeçalho, rodapé e script desses documentos.

### Arquivos de referência existentes

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
├── portugal-fotos.css
├── imagens-portugal/            (imagens e CREDITOS.md preservados)
├── assets/
│   ├── css/
│   │   ├── base.css
│   │   ├── componentes.css
│   │   └── pais.css
│   └── js/
│       └── site.js
├── modelos/
│   ├── pais-principal.html
│   └── pais-interna.html
├── template-modelo/             (principal, Cultura, Gastronomia, CSS e imagens)
├── teste-modelo/                (index.html e teste-modelo.css)
├── documentacao/
│   ├── ESTRUTURA.md
│   ├── HEADER.md
│   ├── FOOTER.md
│   ├── ORIENTACOES.md
│   └── REGRESSAO.md
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
    │   ├── cultura.html / cultura.css
    │   ├── gastronomia.html / gastronomia.css
    │   ├── pontos-turisticos.html / pontos-turisticos.css
    │   └── curiosidades.html / curiosidades.css
    ├── reino-unido/
    └── taiwan/
```

As barras entre nomes indicam arquivos separados na mesma pasta. A árvore resume a organização atual; não representa uma migração de todas as páginas. Os marcadores `.gitkeep` foram omitidos da árvore, mas permanecem nas pastas preparadas.

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
2. Confira os arquivos existentes e reconheça as alterações locais antes de trabalhar. Preserve tudo o que não pertence à sua tarefa.
3. Para um país que já tem HTML, use o arquivo atual como referência e combine a próxima mudança com a equipe. A pasta nova não substitui a página da raiz. Evite manter duas versões concorrentes sem combinar qual será integrada.
4. Para um país novo, escolha uma das duas opções de criação apresentadas acima e siga o roteiro de cópia em [ESTRUTURA.md](ESTRUTURA.md). Use ou crie a pasta do próprio país sem sobrescrever arquivos. Não é necessário criar HTML vazio como reserva.
5. Use nomes em minúsculas, sem espaços ou acentos nos caminhos: `africa-do-sul`, `reino-unido`, `grecia`. No conteúdo visível, escreva normalmente: “África do Sul”, “Reino Unido”, “Grécia”.
6. Salve HTML, CSS, JavaScript e Markdown em UTF-8. No HTML, mantenha `lang="pt-BR"`, a declaração de codificação e a configuração da viewport.
7. Cada colega é responsável pelas páginas do seu país. Alterações em `index.html` da raiz, no menu compartilhado ou nos arquivos compartilhados exigem coordenação e autorização da equipe. Criar uma pasta ou configurar o país no modelo não o adiciona automaticamente ao menu.

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

Mantenha os estilos específicos no CSS do próprio país. Os modelos já usam `assets/js/site.js` para os componentes compartilhados e o menu: não copie um segundo script de cabeçalho nem duplique essa lógica. Um JavaScript local só deve ser acrescentado se houver uma necessidade própria do conteúdo, mantendo sua função separada da navegação compartilhada.

Não copie imagens de Portugal para outros países só para preencher espaços. Prefira imagens adequadas ao destino, com texto alternativo descritivo, arquivo otimizado e registro de autoria, origem e licença. Os créditos existentes em `imagens-portugal/CREDITOS.md` são preservados; confirme as informações antes de reutilizar esse material.

## Estilos e componentes compartilhados

Para páginas novas baseadas nos modelos, use os arquivos compartilhados abaixo. Carregue os três CSS nesta ordem e o CSS local por último. Inclua `site.js` uma única vez, com `defer`.

| Arquivo | Função |
| --- | --- |
| `assets/css/base.css` | Cores, fonte, estilos básicos, contêiner e foco visível nas páginas com `tc-site`. |
| `assets/css/componentes.css` | Cabeçalho, marca, menu, rodapé, botões e link de salto para o conteúdo. |
| `assets/css/pais.css` | Banner, seções, cartões, artigo, dados rápidos e galeria. |
| `assets/js/site.js` | Montagem dos componentes marcados e controle do menu acessível. |

Preserve `tc-site` no `body` e ajuste `data-raiz`, `data-pais-nome` e `data-pais-url` conforme ESTRUTURA. Acrescente `data-galeria-url` somente quando a galeria existir. Ao copiar o template, preserve inicialmente suas classes e os CSS locais; se renomear uma classe, atualize os seletores correspondentes na cópia.

`site.js` pode substituir o conteúdo de `header.tc-cabecalho[data-tc-cabecalho]` e `footer.tc-rodape[data-tc-rodape]`. Configure os dados variáveis pelo `body`, sem editar o HTML gerado no navegador. Preserve a navegação e o rodapé básicos escritos nos modelos: eles continuam disponíveis sem JavaScript, embora o menu interativo e as quatro colunas geradas não apareçam nessa alternativa mínima.

Nem todas as páginas de Portugal usam o mesmo mecanismo: a principal e Cultura mantêm cabeçalho, rodapé e script próprios; Gastronomia e Pontos Turísticos usam o cabeçalho compartilhado e rodapé próprio; Galeria e Curiosidades usam os dois componentes gerados e já têm rodapé completo no HTML para a alternativa sem JavaScript. Consulte a relação de consumidores em [ESTRUTURA.md](ESTRUTURA.md) antes de propor mudanças compartilhadas.

`estilo.css` e `portugal.css` continuam sendo dependências de páginas existentes, mas **não são o padrão de carregamento dos modelos novos**. Não adicione essas folhas nem copie blocos de cabeçalho e rodapé para fazer uma nova cópia funcionar.

### Referência visual opcional de Portugal

Portugal usa turquesa, azul-marinho e branco. Estes tons são uma referência, não uma obrigação para os outros países:

| Uso observado | Cor |
| --- | --- |
| Marca, botões e destaques | `#00a7b5` |
| Destaques e links no rodapé | `#00c2cf` |
| Títulos, texto da marca e fundo do rodapé | `#163b50` |
| Cabeçalho, cartões e títulos no rodapé | `#ffffff` |
| Texto secundário no rodapé | `#d4e2e8` |

A base compartilhada usa Arial, sem dependência de fonte externa; alguns títulos locais usam Georgia. Preserve espaçamento confortável, contraste e navegação legível em celular. Personalize o conteúdo no CSS local, sem alterar os componentes de todos os colegas.

## Exemplo de ponto de partida para uma página nova

Para um futuro arquivo `paises/egito/egito.html`, copie `modelos/pais-principal.html`; se precisar de uma interna, copie também `modelos/pais-interna.html`, por exemplo como `cultura.html`. Copie somente o necessário e ajuste os links entre as páginas. Se copiar apenas a principal, substitua os links para a interna por destinos existentes.

O trecho abaixo mostra apenas a configuração dos arquivos compartilhados e do `body` nessa futura pasta. **Não é uma página completa:** mantenha o cabeçalho, o conteúdo, o rodapé, o link de salto e os links básicos da cópia do modelo. O arquivo `egito.css` só deve ser carregado depois de criado.

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Egito — Turismo.com</title>
    <link rel="stylesheet" href="../../assets/css/base.css">
    <link rel="stylesheet" href="../../assets/css/componentes.css">
    <link rel="stylesheet" href="../../assets/css/pais.css">
    <link rel="stylesheet" href="egito.css">
    <script src="../../assets/js/site.js" defer></script>
</head>
<body class="tc-site pais-egito" data-raiz="../../"
      data-pais-nome="Egito" data-pais-url="paises/egito/egito.html">
    <!-- Preserve e adapte o restante do HTML copiado do modelo. -->
```

`data-raiz` mede a distância do HTML até a raiz; `data-pais-url` parte da raiz e não recebe `../../`. Os links HTML básicos não são reescritos pelo script: ajuste também as migalhas, os cartões e os retornos. Desenvolva os assuntos conforme a divisão de tarefas, verificando as fontes. Não adicione links para arquivos que ainda não existem.

Se escolher o exemplo visual, siga a cópia completa ou parcial descrita em [ESTRUTURA.md](ESTRUTURA.md) e no [LEIA-ME](../template-modelo/LEIA-ME.md). Um cartão pode depender da grade, dos contêineres, das classes do `body` e dos CSS da seção original; não basta copiar apenas seu texto.

## Caminhos relativos: o que muda nas páginas novas

Os caminhos são resolvidos a partir da localização do HTML, não da pasta em que o editor está aberto. A documentação não muda nenhum caminho atual.

| Recurso | Exemplo em `paises/egito/egito.html` |
| --- | --- |
| CSS básicos compartilhados | `../../assets/css/base.css`, `../../assets/css/componentes.css`, `../../assets/css/pais.css` |
| JavaScript compartilhado | `../../assets/js/site.js` |
| CSS local futuro | `egito.css` |
| Página inicial existente | `../../index.html` |
| Serviços existentes | `../../hospedagem.html`, `../../alimentacao.html`, `../../compras.html`, `../../contato.html` |
| Página de Portugal existente | `../../portugal.html` |
| Galeria de Portugal existente | `../../portugal-fotos.html` |
| Internas de Portugal existentes | `../portugal/cultura.html`, `../portugal/gastronomia.html`, `../portugal/pontos-turisticos.html`, `../portugal/curiosidades.html` |
| Foto nova dentro da própria pasta | `imagens/piramides.jpg` |

Nos modelos originais, os recursos compartilhados usam `../assets/`; numa cópia em `paises/egito/`, passam a usar `../../assets/`. O Início do projeto passa a ser `../../index.html`. Links entre arquivos da mesma pasta continuam locais se os nomes forem mantidos. Não substitua todo `../` automaticamente.

As folhas de estilo resolvem seus próprios `url(...)` a partir do arquivo CSS. Uma futura mudança de pasta precisa revisar tanto o HTML quanto o CSS. Se copiar o LEIA-ME para a pasta do país, ajuste também o link dessa cópia para o guia principal, conforme ESTRUTURA.

Somente **depois de adicionar a imagem** e seus créditos, um trecho como este pode ser usado na página nova:

```html
<figure>
    <img src="imagens/piramides.jpg"
         alt="Pirâmides de Gizé vistas do deserto"
         loading="lazy">
    <figcaption>Pirâmides de Gizé, no Egito.</figcaption>
</figure>
```

## Registro histórico da preparação inicial

As observações desta seção descrevem o estado inicial, anterior aos modelos e componentes atuais. **Não são instruções de implementação nem um retrato da branch atual.** Na análise inicial, a branch era `feature/header-turques`, e foram registradas estas alterações locais:

```text
 M portugal.css
 M portugal.html
?? imagens-portugal/lisboa-eletrico.jpg
```

Essas alterações preexistentes foram preservadas naquela preparação. O registro acima não foi atualizado por uma nova consulta ao Git.

- O README então descrevia uma pasta `imagens/` e uma paleta diferente. O README atual já apresenta a estrutura compartilhada e os modelos; as fotografias de Portugal continuam em `imagens-portugal/`.
- Os cartões de Portugal então apontavam para as âncoras provisórias `#conteudo-cultura`, `#conteudo-gastronomia`, `#conteudo-pontos-turisticos` e `#conteudo-curiosidades`, sem os IDs correspondentes. Hoje apontam para as páginas existentes em `paises/portugal/`. Não copie aqueles destinos históricos.
- Naquele momento não havia JavaScript compartilhado, e as páginas tinham implementações diferentes de cabeçalho e rodapé. Hoje existe `assets/js/site.js`, usado pelos modelos e por parte das páginas de Portugal. A principal e Cultura ainda mantêm seu script próprio.
- A extração de estilos e do menu para arquivos compartilhados era uma proposta futura. Esses arquivos agora existem em `assets/`; não é necessário repetir essa extração nem copiar os blocos antigos ao criar uma página pelo modelo.
- O levantamento inicial observou que `imagens-portugal/CREDITOS.md` ainda indicava downloads pendentes, embora os arquivos citados já estivessem presentes. Os problemas de download e essa divergência pertencem ao histórico do projeto: o estado atual de utilização das imagens já está atualizado em `imagens-portugal/CREDITOS.md`, e as imagens utilizadas estão disponíveis. As verificações de correspondência com os originais que ainda faltam permanecem identificadas como pendentes nesse documento; não presuma licença ou autoria somente porque o arquivo existe.

### Cuidados que continuam válidos

- `Docs`, `Dados`, `Galerias` e `paginas` são arquivos, não diretórios. Não os use como pastas nem os converta sem combinar com a equipe.
- Os diretórios de países não tornam suas páginas acessíveis pelo menu. A integração só deve ocorrer com destinos existentes e após coordenação.
- Preserve alterações locais, páginas dos colegas e os arquivos protegidos `documentacao/HEADER.md`, `curiosidades-layout.pdf` e `imagens-portugal/lisboa-eletrico.jpg`. Não presuma origem ou licença dessa fotografia e não a inclua automaticamente no trabalho.

## Como conferir o trabalho da sua página

Abra sua página no navegador, mantendo a estrutura do projeto. A lista completa está em **Testar sua cópia e conferir regressões**, em [ESTRUTURA.md](ESTRUTURA.md). Use [REGRESSAO.md](REGRESSAO.md) como complemento e registro de testes anteriores; resultados históricos não substituem a conferência da sua cópia.

1. Teste em 390, 768 e 1440 px: sem rolagem horizontal, textos legíveis, imagens carregadas e rodapé equilibrado. Confira também a mudança do menu em torno de 980 px.
2. Confira o carregamento dos CSS e de `site.js`, o console, os links, as âncoras e os retornos à principal do país e ao início do projeto.
3. Com JavaScript, teste o menu por clique e teclado: Tab, Shift+Tab, Enter e Escape. Confira foco visível e o estado `aria-expanded` dos controles. Não acrescente abertura por hover apenas com CSS, pois ela pode divergir do estado acessível; preserve o comportamento do modelo escolhido.
4. Desative o JavaScript e recarregue: o conteúdo e os links básicos do cabeçalho e do rodapé devem continuar utilizáveis. Não espere o menu interativo ou as quatro colunas geradas no HTML mínimo dos modelos.
5. Confira os botões `tc-botao`, inclusive a variante de contorno: sem sublinhado nos estados normal, hover, focus e visited, mantendo o indicador de foco visível de 3 px. Não remova o foco para ajustar a aparência.
6. Verifique os textos alternativos, as fontes do conteúdo e os créditos das imagens. Se usar `<details>` e `<summary>`, confira sua abertura pelo teclado também sem JavaScript.

Antes de compartilhar, revise somente os arquivos da sua tarefa, incluindo os arquivos novos, e preserve alterações dos colegas. Combine a revisão com Neusa e siga o fluxo de branches do grupo; não faça integrações em nome de outra pessoa sem combinar.

## Integrações e mudanças futuras

As recomendações abaixo dependem de coordenação e autorização; não são uma exigência para criar uma página com os modelos:

1. Combinar uma estrutura final, nomes dos arquivos, URLs e responsabilidade de cada país com Neusa.
2. Integrar novos países em `index.html` e no menu compartilhado somente quando as páginas estiverem prontas, sem alterar as páginas de outros integrantes.
3. Se houver necessidade aprovada de mudar componentes compartilhados, conferir seus consumidores e testar a mudança antes de integrar. Não usar a personalização de um país como motivo para alterar o componente de todos.
4. Se uma reorganização de páginas existentes for autorizada, fazê-la em etapas pequenas, revisando cada `href`, `src`, `url(...)` e âncora, além dos links de entrada. Preservar os endereços publicados, incluindo os dois HTML de Portugal na raiz. Não mover páginas apenas para uniformizar pastas.
5. Atualizar a documentação correspondente e os créditos após mudanças aprovadas, distinguindo orientações atuais de registros históricos.
