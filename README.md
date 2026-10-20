<div align="center">

# ✈️ TURISMO.COM

**Descubra o mundo — um destino, uma cultura, uma história de cada vez.**

Projeto acadêmico e colaborativo de turismo, desenvolvido com HTML, CSS e JavaScript.

[🌐 Acessar o site](https://turismo-com.vercel.app/) · [📖 Orientações da equipe](documentacao/ORIENTACOES.md) · [🧭 Explorar Portugal](https://turismo-com.vercel.app/portugal.html)

![Prévia animada das telas do protótipo Figma](/turismo-preview.gif)

<sub>Prévia das telas de referência do Figma. O site publicado e as páginas em desenvolvimento podem apresentar diferenças.</sub>

</div>

## 🌍 Sobre o projeto

O **Turismo.com** é um guia educativo de viagens, criado em equipe para apresentar países, culturas, gastronomia, pontos turísticos e informações práticas. O projeto também conta com páginas de hospedagem, alimentação, compras, contato e galerias fotográficas.

A proposta é construir as páginas progressivamente, com uma identidade visual compartilhada e espaço para as contribuições de cada integrante.

## Comece por aqui

Se você vai criar ou adaptar a página de um país, comece pelo [guia principal — ESTRUTURA.md](documentacao/ESTRUTURA.md). Ele explica como escolher os arquivos, preparar a pasta do país, adaptar os caminhos e testar a página.

| Opção | Como usar |
| --- | --- |
| [Modelos básicos — modelos/](modelos/) | Uma principal e uma interna genérica para desenvolver seu próprio layout, acrescentando conteúdo aos poucos. |
| [Exemplo visual completo — template-modelo/](template-modelo/) | Principal, Cultura e Gastronomia para copiar integralmente ou reaproveitar por seções e cartões. Siga as [instruções do exemplo visual — LEIA-ME.md](template-modelo/LEIA-ME.md). |
| [Demonstração — teste-modelo/](teste-modelo/) | Página para observar os componentes compartilhados funcionando. O país e os dados são fictícios e não devem ser publicados como conteúdo real. |

Os modelos são opcionais e permitem personalização. Portugal é uma referência de implementação; seu layout não é obrigatório para os demais países.

## ✨ O que você encontra

- **Destinos:** páginas dedicadas a países e suas características culturais.
- **Portugal:** informações gerais, cartões temáticos e acesso à galeria de imagens.
- **Galerias:** fotografias de destinos com identificação e créditos.
- **Guias práticos:** hospedagem, alimentação e compras.
- **Contato:** espaço de comunicação com a equipe.

> 🚧 **Em desenvolvimento:** o conteúdo e as páginas estão sendo revisados e ampliados. Alguns links e recursos ainda podem estar em construção.

## 🗺️ Destinos

As páginas existentes no projeto incluem **Brasil, Portugal, França, Espanha, Itália, Japão e China**.

Também foram preparadas pastas para o trabalho futuro com **África do Sul, Alemanha, Egito, Grécia, Reino Unido e Taiwan**. A criação dessas pastas não significa que suas páginas estejam prontas.

## 🧰 Tecnologias

![HTML5](https://img.shields.io/badge/HTML5-estrutura-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-estilos-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-interatividade-F7DF1E?logo=javascript&logoColor=black)
![Git](https://img.shields.io/badge/Git-versionamento-F05032?logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-colabora%C3%A7%C3%A3o-181717?logo=github&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-publica%C3%A7%C3%A3o-000000?logo=vercel&logoColor=white)

O projeto utiliza também arquivos JSON para organização de alguns dados.

## 📁 Organização do repositório

```text
turismo-com/
├── index.html                     # Página inicial
├── estilo.css                     # Estilos das páginas antigas
├── portugal.html                  # Página de Portugal
├── portugal.css                   # Estilos específicos de Portugal
├── portugal-fotos.html            # Galeria de Portugal
├── portugal-fotos.css             # Estilos exclusivos da galeria
├── hospedagem.html                # Guia de hospedagem
├── alimentacao.html               # Guia de alimentação
├── compras.html                   # Guia de compras
├── contato.html                   # Contato
├── imagens-portugal/              # Fotografias e créditos de Portugal
├── assets/                       # Componentes compartilhados dos modelos
│   ├── css/
│   │   ├── base.css
│   │   ├── componentes.css
│   │   └── pais.css
│   └── js/
│       └── site.js
├── paises/                       # Páginas internas e pastas preparadas por país
│   └── portugal/
│       ├── cultura.html / cultura.css
│       ├── gastronomia.html / gastronomia.css
│       ├── pontos-turisticos.html / pontos-turisticos.css
│       └── curiosidades.html / curiosidades.css
├── modelos/                      # Estruturas básicas reutilizáveis
│   ├── pais-principal.html
│   └── pais-interna.html
├── template-modelo/              # Exemplo visual completo
│   ├── index.html / template.css
│   ├── cultura.html / cultura.css
│   ├── gastronomia.html / gastronomia.css
│   ├── imagens/
│   └── LEIA-ME.md
├── teste-modelo/                 # Demonstração com dados fictícios
│   ├── index.html
│   └── teste-modelo.css
├── documentacao/                 # Guias da equipe e registros de conferência
│   ├── ESTRUTURA.md              # Guia principal dos componentes e modelos
│   ├── REGRESSAO.md
│   ├── ORIENTACOES.md
│   ├── HEADER.md
│   └── FOOTER.md
└── README.md
```

Esta árvore é um resumo. As barras entre um HTML e um CSS indicam dois arquivos na mesma pasta; outras páginas de países e galerias também permanecem na raiz.

**Compatibilidade:** `portugal.html` e `portugal-fotos.html` permanecem na raiz para preservar os links publicados e as integrações existentes. As páginas internas de Portugal estão em `paises/portugal/`, com seus CSS locais. Novos países podem organizar suas páginas em `paises/<nome-do-pais>/`, mediante coordenação com a equipe. Não é necessário mover as páginas existentes dos colegas.

## 💻 Como executar localmente

1. Clone o repositório:
   ```bash
   git clone https://github.com/Neusacoelho/turismo-com.git
   ```
2. Abra a pasta do projeto no VS Code.
3. Abra `index.html` com a extensão **Live Server** ou diretamente no navegador.

Não é necessário instalar React ou executar um processo de compilação.

## 🤝 Padrão visual e colaboração

Cada colega é responsável pelas páginas do seu país, conforme a divisão de trabalho combinada com a equipe. Antes de copiar arquivos, confira se a pasta já existe e preserve o conteúdo e as alterações de outros integrantes.

O projeto reúne páginas com implementações diferentes. Os modelos utilizam os componentes compartilhados de `assets/`; páginas existentes podem manter cabeçalhos, menus e rodapés próprios. Personalize sua cópia sem transformar a referência de Portugal em uma obrigação para todo o site.

**Adicionar países ao menu compartilhado, alterar o `index.html` da raiz ou modificar os CSS e o JavaScript compartilhados exige coordenação com a equipe.** Não altere páginas de outros países ou os exemplos originais para fazer sua página funcionar. Criar a pasta de um país não o inclui automaticamente no menu.

Para implementar páginas com os modelos, siga o guia principal e o LEIA-ME da seção **Comece por aqui**. Também permanecem disponíveis materiais de etapas anteriores: [HEADER.md](documentacao/HEADER.md), [FOOTER.md](documentacao/FOOTER.md) e [ORIENTACOES.md](documentacao/ORIENTACOES.md). Eles não são arquivos incluídos automaticamente no site nem substituem o fluxo atual do guia principal.

## 👥 Equipe e créditos

Projeto acadêmico desenvolvido no curso de **Desenvolvimento Full Stack — +Pra Ti / Codifica**.

### Organização da equipe

| Função | Nome |
| :--- | :--- |
| Liderança do grupo | **Neusa Oliveira** |
| Vice-liderança | **David Pamplona** |
| Coordenação docente | **Prof. Jaques Antunes** |

### Integrantes

| Integrante | Integrante |
| :--- | :--- |
| Silvia Reis | Julia Alves |
| Emylli da Rosa | Regina Lucia Matos Lima |
| Wesley David | Stanley |
| Leo Matias | Matheus Alan |
| Lucas Morales | — |

**Contato:** [contato.neusa.turismo@gmail.com](mailto:contato.neusa.turismo@gmail.com)
**Localidade informada no projeto:** Sapucaia do Sul — RS

---

<div align="center">
  <strong>Turismo.com</strong> · Um projeto para aprender, colaborar e descobrir o mundo. 💙
</div>
