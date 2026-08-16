# Base de Dados: Instrumentos de Indução da Maturidade de Governo Digital e Agêntico na Educação

[![Mestrado Profissional](https://img.shields.io/badge/Mestrado_Profissional-ISC%2FTCU-003366?style=for-the-badge)](https://portal.tcu.gov.br/instituto-serzedello-correa/)
[![CAPES](https://img.shields.io/badge/Avaliação-CAPES-blue?style=for-the-badge)](https://www.gov.br/capes/pt-br)
[![Metodologia](https://img.shields.io/badge/Metodologia-LACA_(LLM--Assisted)-128C7E?style=for-the-badge)](#-metodologia-laca-llm-assisted-content-analysis)
[![Licença](https://img.shields.io/badge/Licença-CC%20BY%204.0-green?style=for-the-badge)](https://creativecommons.org/licenses/by/4.0/deed.pt_BR)

## 📌 Sobre o Produto Técnico Tecnológico (PTT)

Este repositório contém a Base de Dados estruturada referente ao **Produto Técnico Tecnológico (PTT)** desenvolvido no âmbito do Mestrado Profissional em Controle da Administração Pública do Instituto Serzedello Corrêa (ISC/TCU).

O acervo reúne **1.029 extrações de dados textuais consolidadas em 909 instrumentos únicos** de políticas públicas, tecnologias e normativos destinados à indução da maturidade em Governo Digital e Agêntico na Educação, com foco na participação cidadã e na coprodução de valor público.

* **Título da Dissertação:** Instrumentos de indução da maturidade de governo digital na educação à luz da participação cidadã: a transição para o governo agêntico na coprodução de valor público
* **Aluno/Autor:** Tiago Marafante Lins de Souza
* **Orientador:** Prof. Dr. Edans Flávius de Oliveira Sandes
* **Instituição:** Instituto Serzedello Corrêa (ISC) / Tribunal de Contas da União (TCU)
* **Programa:** Programa de Pós-Graduação Stricto Sensu em Controle da Administração Pública (Linha de Pesquisa 2: Tecnologias para a Inovação do Controle Governamental)
* **Ano:** 2026

---

## 🔬 Metodologia: LACA (LLM-Assisted Content Analysis)

A identificação e a categorização dos 909 instrumentos utilizaram a metodologia de fronteira **LACA (LLM-Assisted Content Analysis)**, que emprega Inteligência Artificial Generativa (LLM Gemini) para a codificação de dados qualitativos em larga escala.

**Passo a passo da operacionalização do LACA:**
1. **Formação do Corpus:** Triagem de 76 documentos refinados (Scopus, Web of Science, Google Scholar) e normativos do controle externo do TCU/OCDE.
2. **Extração via Prompt Blender:** Utilização de modelos de linguagem ajustados com restrições semânticas estritas (matriz 5W2H) para extração de atributos analíticos (descrição, território, grau de implementação, resultados reportados).
3. **Calibração Humana (Ground Truth):** Validação inicial mediante codificação manual pelo pesquisador para ajustar as instruções do modelo de IA e evitar "alucinações".
4. **Sintetização e Deduplicação:** Tratamento computacional de 1.025 ocorrências brutas para a consolidação de 909 instrumentos governamentais únicos[cite: 4].

---

## 📁 Estrutura do Repositório

```text
ptt-instrumentos-governo-digital-e-agentico/
├── README.md                                         # Documentação principal e guia da base
├── LICENSE                                           # Termos da licença CC BY 4.0 (Open Data)
├── Base_de_Dados_Instrumentos_Governo_Digital.xlsx  # Planilha completa com Dashboard analítico
├── Base_de_Dados_Instrumentos_Governo_Digital.csv   # Versão em formato aberto legível por máquina
└── Relatorio_Tecnico_PTT_Tiago_Souza.pdf            # Relatório Técnico Descritivo para avaliação CAPES
