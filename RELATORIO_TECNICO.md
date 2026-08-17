# 📄 Relatório Técnico e Metodológico do PTT: Base de Dados LACA

---

- **Produto Técnico Tecnológico (PTT):** Mapeamento e Base de Dados de Instrumentos de Indução da Maturidade de Governo Digital e Agêntico na Educação
- **Dissertação Associada:** Instrumentos de indução da maturidade de governo digital na educação à luz da participação cidadã: a transição para o governo agêntico na coprodução de valor público
- **Autor:** Tiago Marafante Lins de Souza
- **Orientador:** Prof. Dr. Edans Flávius de Oliveira Sandes
- **Programa:** Mestrado Profissional em Controle da Administração Pública (MP-CAP)
- **Instituição:** Instituto Serzedello Corrêa / Tribunal de Contas da União (ISC/TCU)
- **Ano:** 2026
- **Repositório Oficial:** [ptt-instrumentos-governo-digital-e-agentico](https://github.com/tl81/ptt-instrumentos-governo-digital-e-agentico)[cite: 9]
- **Licença:** Creative Commons Attribution 4.0 International (CC-BY 4.0)

---

## 1. Apresentação e Escopo do PTT

Este Relatório Técnico documenta a concepção, o pipeline computacional e os resultados da base de dados produzida como **Produto Técnico Tecnológico (PTT)** da dissertação de mestrado do programa MP-CAP/TCU[cite: 9]. 

O objetivo do PTT é fornecer à Administração Pública e aos órgãos de controle externo uma base de dados estruturada, auditável e categorizada contendo instrumentos governamentais e de Inteligência Artificial para indução da maturidade em Governo Digital e Agêntico no setor público educacional[cite: 9].

### Produtos Gerados no Repositório

| Arquivo / Produto | Registros | Descrição |
| :--- | :---: | :--- |
| **Matriz Bruta Consolidada** | 1.025 | Corpus unificado da revisão de escopo em PDF (69 artigos), normas externas (TCU/OCDE) e base de calibração (*Ground Truth*)[cite: 9]. |
| **Base Deduplicada LACA** | 909 | Base sintetizada via *TF-IDF* + *Agglomerative Clustering* (`distance_threshold=0.2`), representando os instrumentos únicos[cite: 9]. |
| **Recorte Governo Agêntico** | 176 | Subamostra temática contendo evidências diretas de uso de IA generativa, orquestração multiagente e automação inteligente[cite: 9]. |

---

## 2. Declaração de Transparência no Uso de IA (Diretrizes CAPES/CNPq)

> **Declaração de Integridade Acadêmica:** Em observância às diretrizes da CAPES e do CNPq sobre transparência no uso de inteligência artificial generativa na pós-graduação:
>
> As rotinas de pré-processamento, vetorização e agrupamento semântico foram desenvolvidas com o auxílio do modelo de linguagem **Google Gemini** em ambiente **Google Colab**[cite: 9]. 
>
> A parametrização estatística, a validação de agrupamentos semânticos, a curadoria do dicionário de dados e a reclassificação das 10 macrocategorias de IA foram executadas integralmente pelo autor, que assume total responsabilidade científica e autoral pelos produtos publicados[cite: 9].

---

## 3. Metodologia LACA (LLM-Assisted Content Analysis)

O método **LACA** combina o poder de extração contextual de Large Language Models (LLMs) com algoritmos de aprendizado de máquina não supervisionado (*Machine Learning*) para tratamento estatístico de grandes corpora qualitativos[cite: 9].

```text
[Corpus em PDF (69) + Normas (7) + Ground Truth]
                      │
                      ▼
        [1. Extração Estruturada via LLM] ──► (1.025 ocorrências brutas)
                      │
                      ▼
     [2. Limpeza Textual NLTK & Vetorização TF-IDF]
                      │
                      ▼
  [3. Agrupamento Hierárquico Aglomerativo (d=0.2)] ──► (Atribuição de cluster_id)
                      │
                      ├───────────────────────────┐
                      ▼                           ▼
       [Base Deduplicada: 909 Únicos]   [Fatiamento Agêntico: 176 Registros]
