# Projeto da disciplina Algoritmos e Estruturas de Dados II. 
## Discentes: Felipe Gabriel Bezerra da Silva e Laíze Suélia da Silva Oliveira   </br> Docente: Ivanovitch Silva

## 1. Grafos e sua aplicação
O presente projeto tem como objetivo analisar documentos de processos movidos pelo Ministério Público de Contas do Estado de São Paulo (MPC-SP), que apontam graves riscos em investimentos milionários envolvendo Institutos de Previdência Municipal e o Banco Master. A metodologia consiste na extração de textos e na análise das relações entre os atores citados por meio do Reconhecimento de Entidades Nomeadas (NER), fundamentado em técnicas de Processamento de Linguagem Natural (PLN). Por fim, o trabalho aplica conceitos de Grafos e Redes Complexas para possibilitar análises visuais e estruturais sobre a rede de conexões identificada, integrando o conteúdo teórico ministrado em sala de aula à prática de auditoria de dados reais.

> As informações referentes aos processos foram extraídas do site oficial do [Ministério Público de Contas do Estado de São Paulo](https://www.mpc.sp.gov.br/procuradoria-do-mpc-sp-aponta-graves-riscos-em-investimentos-milionarios-feitos-por-instituto-de).

## 2. Configuração do ambiente e bibliotecas
Foi utilizado o ambiente do Google Colab para desenvolvimento e hospedagem do nosso código, sendo este escrito na linguagem Python. Para melhoria de performance e utilização de recursos extras, fez-se necessário instalar as seguintes bibliotecas:
- PyMuPDF (fitz)
- Spacy
- NetworkX
- Re
- Itertools
- Plotly
- Pandas

## 3. Etapas do processamento
De forma resumida, estão listadas, abaixo, as etapas do processamento do código desenvolvido.
> Link para o [Notebook Jupyter](https://github.com/fsilva19/P1_AED2_26-1/blob/main/Notebook/U1T1_felipe_laize.ipynb).
1) Extração do texto dos arquivos em PDF.
2) Limpeza das informações, removendo termos, ruídos, imagens, links e paginações desnecessárias para a análise, como cabeçalhos, rodapés e marcas d'água. 
3) Padronização de termos com variações ortográficas ou abreviações, a fim de evitar a criação de múltiplas entidades para um mesmo conceito.
4) Aplicação do NER com processamento de linguagem natural (NLP).
5) Construção do grafo, com inserção de nós e arestas a partir das entidades nomeadas e suas correlações.
6) Visualização do grafo por meio de recursos programáveis, visando facilitar a interpretação dos dados.
7) Análise dos resultados obtidos à nível técnico dos grafos e entidades nomeadas.
8) Análise dos resultados obtidos à nível de contexto, entendendo quais atores possuem maior importância aos casos.

### Grafo
Abaixo, mostra-se o grafo gerado do nó principal da rede. Os nós estão dimensionados de acordo com o grau de conexões de cada entidade, bem como agrupados e separados por cores para cada label: PER, LOC, ORG e MISC (Diversos).

<img width="1000" height="700" alt="grafo" src="https://github.com/user-attachments/assets/e49db5c3-55a5-47f7-a946-4f425b917f47" />

## 4. Resultados e conclusões
### Análise dos resultados
Como forma de analisar a rede, foram extraídas algumas métricas do Grafo completo (G) e feita a comparação com os valores referentes ao nó principal (G_main). 

- **Nó principal:** diz respeito ao maior caminho do grafo.
- **Número de nós:** corresponde à quantidade de elementos na rede.
- **Número de arestas:** corresponde à quantidade de conexões (correlações) entre os elementos.
- **Grau médio:** informa a média dos graus (quantidade de conexões) de cada elemento.
- **Densidade:** representa a razão entre o número de arestas do grafo e o número máximo de conexões.

#### ANÁLISE DAS MÉTRICAS DA REDE

| Métrica | Rede Completa | Nó Principal | Porcentagem |
| :--- | :---: | :---: | :---: |
| **Número de nós** | 192 | 127 | 66.15% |
| **Número de arestas** | 513 | 452 | 88.11% |
| **Grau médio** | 5.344 | 7.118 | - |
| **Densidade** | 0.028 | 0.056 | - |

### Conclusões -
1. O nó principal representa mais de **65%** da rede completa.
2. As arestas do nó principal representam mais **85%** das arestas da rede completa.
3. A densidade do nó principal é maior que a densidade da rede completa, indicando que nesse nó existem mais entidades em correlação.
4. Aproximadamente **35%** das entidades possuem pouca ou nenhuma correlação com o nó principal.

#### GRÁFICO COMPARATIVO

<img width="1340" height="525" alt="newplot" src="https://github.com/user-attachments/assets/268720a0-ff0e-4564-8ed6-8107ea928bb6" />

### Contextualizando os resultados
Com a tabela abaixo, conseguimos identificar as 10 entidades com maiores conexões. 

- Intermediação (Ponte): Mede o controle de fluxo, identificando as entidades que servem como elos indispensáveis entre diferentes grupos da rede.
- Proximidade (Centro): Indica a 'velocidade' de comunicação, destacando os nós que alcançam todos os outros atores com o menor número de saltos. 
</br>

#### RANKING TOP 10 ENTIDADES MAIS CONECTADAS

| Entidade | Grau (Conexões) | Intermediação (Ponte) ↓ | Proximidade (Centro) |
| :--- | :---: | :---: | :---: |
| **Regime Próprio de Previdência Social** | 41 | **0.412** | 0.578 |
| **Fundo Texas** | 37 | **0.310** | 0.541 |
| **São Paulo** | 31 | **0.215** | 0.529 |
| **Brodowski** | 28 | **0.205** | 0.525 |
| **Banco Central do Brasil** | 20 | **0.096** | 0.452 |
| **Banco Master** | 12 | **0.076** | 0.432 |
| **Comitê de Investimentos** | 16 | **0.069** | 0.412 |
| **DAIR (Investimento de Recursos)** | 12 | **0.054** | 0.412 |
| **Política de Investimentos** | 18 | **0.050** | 0.463 |
| **São Roque** | 18 | **0.035** | 0.383 |

- Para as duas métricas acima, o termo **'Regime Próprio de Previdência Social'** aparece como a entidade com os maiores valores, ou seja, é o termo que mais faz relação com outras entidades e é o tema central nos três arquivos.
- Em segunda lugar no ranking, temos o termo **'Fundo Texas'**, com valores próximos ao primeiro lugar.

#### TOP 10 ENTIDADES COM MAIORES GRAUS

<img width="1200" height="525" alt="10maiores" src="https://github.com/user-attachments/assets/13090279-1753-474c-8804-d7b58cc38086" />

> **Em conclusão, pode-se admitir que os processos judiciais analisados pelo MPC-SP têm como eixo central a investigação de valores milionários investidos, majoritariamente, no Fundo Texas. As evidências encontradas apontam que os principais atores afetados são os Institutos de Previdência Municipal (RPPS), cujos recursos utilizados foram expostos a grandes riscos financeiros. Embora não seja o ator principal em todos os processos, um grande risco identificado foi o aporte de altas quantias no Banco Master, instituição que esteve envolvida em irregularidades financeiras e judiciais nos últimos meses.**




