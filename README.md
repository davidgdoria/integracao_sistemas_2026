# Integração de Sistemas · 2026

Este é o repositório de trabalho da unidade curricular **Integração de Sistemas** (2026). Guarda em Git os entregáveis das atividades práticas, as fontes que os geram e a respetiva documentação, com o histórico de versões.

> **Objetivo:** assegurar que todos os estudantes dispõem de um ambiente mínimo de controlo de versões que permita desenvolver e documentar as atividades práticas subsequentes.

## Atividades

| Sprint | Tema | Entregáveis | Estado |
|---|---|---|---|
| 1 | Diagnóstico do ecossistema TechStore | [Relatório (Markdown)](IS_Sprint1_Diagnostico.md) · [PDF de entrega](IS_Sprint1_Diagnostico_NomeApelido.pdf) | Em revisão |

As atividades seguintes serão acrescentadas a esta tabela.

### Sprint 1 — Diagnóstico do ecossistema TechStore

O trabalho faz um diagnóstico estruturado de um ecossistema de comércio eletrónico. Esse ecossistema inclui uma plataforma Web, uma aplicação móvel, um ERP, um CRM, gestão de armazém, faturação, um gateway de pagamentos e uma transportadora. O diagnóstico assenta nos conceitos de integração, heterogeneidade, interoperabilidade e dependência entre sistemas. Como o enunciado exige, o trabalho caracteriza o problema e **não propõe soluções tecnológicas**.

| Parte | Conteúdo |
|---|---|
| **A — Modelação do ecossistema** | Três diagramas: o mapa do ecossistema (Figura 1), os dados replicados entre sistemas (Figura 2) e o processo encomenda-a-entrega (Figura 3). Quadros com o inventário de sistemas, as entidades de dados, os fluxos F1–F13, as dependências e os pontos críticos PC1–PC8 |
| **B — Matriz de diagnóstico** | Dimensões de heterogeneidade; matriz com 14 entradas classificadas por natureza; lacunas de informação |
| **C — Análise crítica** | Os três problemas mais críticos: stock inconsistente, identidade do cliente fragmentada e faturação antes da confirmação do armazém. Inclui a priorização dos pontos críticos (Figura 4); ~890 palavras, dentro do limite de 700–1000 |
| **Referências** | 12 referências em APA 7, das quais 9 científicas |

**Pendente antes da entrega**

- [ ] Preencher a identificação (nome, n.º de estudante, curso/turma, docente) no Markdown e em `fonte/relatorio.html`
- [ ] Acrescentar ao PDF as Figuras 2–4, que já estão no Markdown
- [ ] Gerar o PDF final, que deve chamar-se `IS_Sprint1_Diagnostico_NomeApelido.pdf`
- [ ] Confirmar se a leitura proposta pela cadeira deve constar das referências

## Estrutura do repositório

```text
.
├── README.md
├── IS_Sprint1_Diagnostico.md               # Sprint 1: relatório em Markdown, com diagramas Mermaid
├── IS_Sprint1_Diagnostico_NomeApelido.pdf  # Sprint 1: versão PDF para entrega
└── fonte/                                  # Fontes do PDF do Sprint 1
    ├── relatorio.html                      # Texto, quadros e paginação (HTML + CSS)
    ├── mapa.py                             # Gera a Figura 1 (mapa.svg)
    ├── mapa.svg                            # Figura 1, gerada por mapa.py
    └── build.py                            # Gera o PDF e conta as palavras da Parte C
```

## Ver e exportar os diagramas

Os diagramas do relatório em Markdown estão escritos em [Mermaid](https://mermaid.js.org/). O GitHub mostra-os diretamente, tal como o VS Code (com uma extensão de pré-visualização Mermaid) e o Obsidian.

Para editar um diagrama ou exportá-lo em PNG ou SVG, copie o respetivo bloco `mermaid` para o [Mermaid Live Editor](https://mermaid.live). Os diagramas não têm cor de fundo, por isso leem-se bem tanto em tema claro como em tema escuro.

## Gerar o PDF

O PDF é gerado a partir de `fonte/relatorio.html` com o [WeasyPrint](https://weasyprint.org/). O script `build.py` faz três coisas: volta a desenhar o mapa (Figura 1), mostra quantas palavras tem a Parte C e escreve o PDF na raiz do repositório.

**Requisitos**
- Python 3.9 ou superior.
- Pango: já vem com a maioria das distribuições Linux. Para outros sistemas, veja a [documentação de instalação do WeasyPrint](https://doc.courtbouillon.org/weasyprint/stable/first_steps.html).
- Fontes Liberation Serif e Liberation Sans. Se não estiverem instaladas, são usadas as fontes equivalentes do sistema.

Criar um ambiente virtual (a pasta `.venv/` não deve ser versionada):

```bash
python3 -m venv .venv
```

Instalar o WeasyPrint:

```bash
.venv/bin/pip install weasyprint
```

Gerar o PDF, substituindo `NomeApelido` pelo seu nome, sem espaços:

```bash
.venv/bin/python fonte/build.py NomeApelido
```

## Convenções

- **Nome dos ficheiros de entrega:** `IS_Sprint<N>_<Tema>_NomeApelido.pdf`, como pede o enunciado.
- **Língua:** português europeu, segundo o Acordo Ortográfico de 1990.
- **Referências:** norma APA, 7.ª edição, com DOI sempre que exista.
- **Evidência:** cada afirmação do diagnóstico indica se vem explicitamente do enunciado ou se é inferida.
- **Texto em dois sítios:** o relatório em Markdown e `fonte/relatorio.html` têm o mesmo texto. Uma alteração num tem de ser replicada no outro, e o PDF é sempre gerado de novo a partir das fontes, nunca editado à mão.

## Autor

**[Nome Apelido]** · n.º [n.º] · [curso / turma]
Docente: [nome do docente]
