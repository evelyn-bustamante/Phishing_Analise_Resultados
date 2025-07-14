# Caracterização de Phishing com Grandes Modelos de Linguagem (LLMs): Uma Avaliação Comparativa entre Gemini, DeepSeek e ChatGPT

Este repositório disponibiliza os resultados obtidos no estudo **“Caracterização de Phishing com Grandes Modelos de Linguagem (LLMs): Uma Avaliação Comparativa entre Gemini, DeepSeek e ChatGPT”**. Os dados aqui presentes foram gerados a partir da aplicação dos modelos de linguagem (LLMs) sobre um conjunto de e-mails, com o objetivo de identificar características de phishing e avaliar a performance dos modelos.

As informações contidas neste repositório subsidiam as análises quantitativas e qualitativas descritas no artigo.


# Estrutura do `README.md`

Este README.md está organizado nas seguintes seções:

1. **Título e Resumo**: Apresenta o título completo do projeto e uma descrição concisa do objetivo principal.
2. **Informações básicas**: Fornece um panorama do estudo realizado, incluindo o total de amostras analisadas, a origem dos dados e os critérios utilizados para classificação.
3. **Dependências**: Lista os requisitos necessários para o uso dos dados. 
4. **Preocupação com a segurança**: Indica se os arquivos não apresentam riscos de segurança ou não. 
5. **Instalação**: Instruções passo a passo para acessar os dados do projeto.
6. **Teste minimo**: Procedimento simples para validar se o artefato está acessível e íntegro.
7. **Experimentos**: Descrição dos principais experimentos realizados.
8. **Estrutura da Planilha**: Descreve o conteúdo e a organização dos dados.
9. **Licença**: Informações sobre a licença do projeto.

# Selos Considerados

Os selos considerados são: **Disponíveis (SeloD)**.

# Informações Básicas

Este artefato consiste em um arquivo Excel contendo os resultados da análise de detecção de phishing com três LLMs: **ChatGPT**, **Gemini** e **DeepSeek**.

Todos os modelos foram instruídos com o mesmo prompt para garantir consistência nos resultados, analisando inicialmente 10 e depois 100 e-mails (total de 110 amostras, com 62 legítimos e 48 phishing), extraídos de um dataset público disponível no [Kaggle](https://www.kaggle.com/datasets/subhajournal/phishingemails/data?select=Phishing_Email.csv).

Os modelos foram solicitados a:
1. Identificar **características de phishing** nos e-mails.
2. Criar uma **planilha binária** com marcações `SIM` ou `NÃO` para cada característica.
3. Atribuir um valor de **probabilidade de phishing** com três níveis: `BAIXA`, `MÉDIA`, `ALTA`.

A probabilidade foi classificada conforme o número de características detectadas (`SIM`):
- 0–1 características: **BAIXA**
- 2–4 características: **MÉDIA**
- 5 ou mais características: **ALTA**

E-mails classificados com probabilidade **MÉDIA ou ALTA** foram considerados phishing.

Por fim, foram computadas métricas de desempenho para cada modelo, com base em suas classificações finais comparadas com os rótulos reais dos e-mails.

**Não há necessidade de ambiente de execução**, dependências técnicas ou configuração de hardware/software.

# Dependências

Não se aplicam. Os dados foram gerados previamente e estão consolidados no arquivo `Phishing_Analise_Resultados`. Nenhuma biblioteca ou ferramenta adicional é necessária para visualização.

# Preocupações com Segurança

Este artefato **não oferece riscos de segurança**. O único conteúdo são 4 arquivos `.csv`, livre de macros ou qualquer tipo de execução de código.

# Instalação

Nenhum processo de instalação é necessário. Para acessar os dados:

1. Faça o download dos arquivos:
- `Phishing_Analise_Resultados - Phishing_Analise-DeepSeek.csv`
- `Phishing_Analise_Resultados - Phishing_Analise-Gemini.csv`
- `Phishing_Analise_Resultados - Run1-Phishing_Analise-Gemini.csv`
- `Phishing_Analise_Resultados - Run1-Phishing_Analise-Gemini.csv (Revisado)`

3. Abra em qualquer visualizador de planilhas compatível com Microsoft Excel, LibreOffice ou Google Sheets.

# Teste Mínimo

Para validar o acesso e conteúdo do artefato:

1. Faça o download do arquivo `Phishing_Analise_Resultados`.
   
2. Abra em qualquer leitor de planilhas (Excel, LibreOffice ou Google Sheets).

3. Verifique se o arquivo contém:
   - Respostas dos modelos analisados (ChatGPT, Gemini, DeepSeek).
   - Classificações atribuídas por cada modelo.
   - Colunas com os resultados esperados (e-mail legítimo ou phishing).
   - Cálculo de métricas como acurácia, precisão, recall e F1-score.

# Experimentos

## Reivindicação #1: Extração de Características e Classificação de Phishing

Esta seção apresenta o passo a passo necessário para compreensão e validação das principais reivindicações do artigo. Os dados utilizados e gerados estão disponíveis no arquivo `Phishing_Analise_Resultados`, com uma planilha distinta para cada modelo avaliado.

- Cada modelo foi submetido ao mesmo conjunto de e-mails com prompts padronizados.
- As LLMs retornaram colunas com **características textuais de phishing**, como: remetente suspeito, senso de urgência, anexos estranhos, erros gramaticais, entre outros.
- Cada modelo criou seu próprio conjunto de colunas binárias (`SIM` / `NÃO`) indicando a presença ou ausência dessas características.
- Além disso, foi gerada uma **classificação de probabilidade de phishing** com três níveis (`BAIXA`, `MÉDIA`, `ALTA`), baseada no número de características detectadas.
- E-mails classificados como `MÉDIA` ou `ALTA` foram considerados **phishing**.

Essas informações estão localizadas nas planilhas:
- `Phishing_Analise_Resultados - Phishing_Analise-ChatGPT.csv`
- `Phishing_Analise_Resultados - Phishing_Analise-DeepSeek.csv`
- `Phishing_Analise_Resultados - Phishing_Analise-Gemini.csv`
- `Phishing_Analise_Resultados - Run1-Phishing_Analise-Gemini.csv (Revisado)`

## Reivindicação #2: Avaliação Quantitativa de Desempenho (Métricas)

- Com base nas classificações finais feitas por cada modelo, foram calculadas as seguintes métricas:
  - **VP** (Verdadeiro Positivo): phishing identificado corretamente.
  - **VN** (Verdadeiro Negativo): e-mail legítimo corretamente identificado.
  - **FP** (Falso Positivo): e-mail legítimo classificado incorretamente como phishing.
  - **FN** (Falso Negativo): e-mail de phishing classificado como legítimo.
- A partir disso, foram computadas:
  - **Acurácia**
  - **Precisão**
  - **Recall**
  - **F1-score**

Essas métricas estão disponíveis na seção final de cada planilha, permitindo a comparação direta entre os modelos.

| Modelo             | Acurácia | Precisão | Recall | F1-Score |
|--------------------|----------|----------|--------|----------|
| ChatGPT            | 89,40%   | 90,05%   | 88,42% | 89,23%   |
| DeepSeek           | 93,36%   | 96,68%   | 88,45% | 92,38%   |
| Gemini             | 90,29%   | 96,35%   | 81,33% | 88,20%   |
| Gemini (Revisado)  | 90,88%   | 98,01%   | 80,34% | 88,30%   |

Esses valores estão diretamente ligados às conclusões do artigo sobre **qual modelo foi mais eficiente** na tarefa de detecção de phishing.

## Estrutura das Planilhas

Cada planilha (uma para cada modelo: ChatGPT, DeepSeek, Gemini e Gemini Revisado) contém:

- `Coluna E-mails`: conteúdo textual de cada e-mail analisado.
- `Colunas de Características`: marcações `SIM` ou `NÃO` para cada atributo detectado pelo modelo.
- `Probabilidade de Phishing`: valor `BAIXA`, `MÉDIA` ou `ALTA`, conforme número de características detectadas.
- `Resultado`: se o e-mail foi classificado como phishing ou legítimo.
- `E-mail Type`: valor real (rotulado) do e-mail.
- `VP`, `VN`, `FP`, `FN`: usados para cálculo das métricas.
- `Totais`: soma dos valores para cada modelo.
- `Métricas`: resultados de acurácia, precisão, recall e F1-score.

Essas informações permitem reproduzir a análise estatística e comparar o desempenho entre os modelos.


# LICENSE

Este repositório está licenciado sob a [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), permitindo uso e redistribuição desde que a devida atribuição seja feita.

---

