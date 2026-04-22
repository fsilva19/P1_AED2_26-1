# Projeto da disciplina Algoritmos e Estruturas de Dados II. 
## Discentes: Felipe Gabriel Bezerra da Silva e Laíze Suélia da Silva Oliveira   </br> Docente: Ivanovitch Silva

## 1. Grafos e sua aplicação
<p> O presente projeto tem como objetivo analisar documentos de processos movidos pelo Ministério Público de Contas do Estado de São Paulo (MPC-SP), que apontam graves riscos em investimentos milionários envolvendo Institutos de Previdência Municipal e o Banco Master. A metodologia consiste na extração de textos e na análise das relações entre os atores citados por meio do Reconhecimento de Entidades Nomeadas (NER), fundamentado em técnicas de Processamento de Linguagem Natural (PLN). Por fim, o trabalho aplica conceitos de Grafos e Redes Complexas para possibilitar análises visuais e estruturais sobre a rede de conexões identificada, integrando o conteúdo teórico ministrado em sala de aula à prática de auditoria de dados reais. </p>

> As informações referentes aos processos foram extraídas do site oficial do [Ministério Público de Contas do Estado de São Paulo](https://www.mpc.sp.gov.br/procuradoria-do-mpc-sp-aponta-graves-riscos-em-investimentos-milionarios-feitos-por-instituto-de).

### 2. Configuração do ambiente e bibliotecas
Foi utilizado o ambiente do Google Colab para desenvolvimento e hospedagem do nosso código, sendo este escrito na linguagem Python. Para melhoria de performance e utilização de recursos extras, fez-se necessário instalar as seguintes bibliotecas:
- PyMuPDF (fitz)
- Spacy
- NetworkX
- Re
- Itertools
- Plotly
- Pandas

### 3. Etapas do processamento
De forma resumida, estão listadas, abaixo, as etapas do processamento do código desenvolvido.
1) Extração do texto dos arquivos em PDF.
2) Limpeza das informações, removendo termos, ruídos, imagens, links e paginações desnecessárias para a análise, como cabeçalhos, rodapés e marcas d'água. 
3) Padronização de termos com variações ortográficas ou abreviações, a fim de evitar a criação de múltiplas entidades para um mesmo conceito.
4) Aplicação do NER com processamento de linguagem natural (NLP).
5) Construção do grafo, com inserção de nós e arestas a partir das entidades nomeadas e suas correlações.
6) Visualização do grafo por meio de recursos programáveis, visando facilitar a interpretação dos dados.
7) Análise dos resultados obtidos à nível técnico dos grafos e entidades nomeadas.
8) Análise dos resultados obtidos à nível de contexto, entendendo quais atores possuem maior importância aos casos.


### 4. Resultados




### 5. Conclusões
