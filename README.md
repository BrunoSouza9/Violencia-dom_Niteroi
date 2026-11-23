Violência doméstica e feminicídio em Niterói
O que os dados abertos do ISP-RJ mostram entre 2018 e 2025
Projeto de Extensão da disciplina Tópicos de Big Data em Python 2026.2, da Estácio Niterói, sob orientação da Profa. Simone Gama.
Sobre o projeto
O projeto analisa dados abertos do Instituto de Segurança Pública do Rio de Janeiro (ISP-RJ) para responder a uma pergunta simples:
> A violência doméstica em Niterói está aumentando, ou só muda de mês para mês?
Para isso, o código em Python faz a limpeza dos dados, calcula estatísticas descritivas, identifica meses atípicos, ajusta uma regressão linear simples e cria um índice de alerta para meses críticos.
Dados
Fonte: base mensal por município do ISP-RJ, de acesso aberto (ispdados.rj.gov.br).
Base bruta: 14.076 linhas e 62 colunas.
Recorte analisado: Niterói, de 2018 a 2025 (96 meses).
Indicadores: lesão corporal dolosa, ameaça, estupro, homicídio doloso e feminicídio.
Violência doméstica (proxy): índice aproximado, igual à soma de lesão corporal dolosa, ameaça e estupro.
Os dados são públicos e agregados (contagem de ocorrências por mês). Não há informações de pessoas identificáveis.
O que o código faz
O código está organizado em nove etapas:
Configuração e carga dos dados
Limpeza
Estatísticas descritivas e desvio padrão
Outliers por boxplot (IQR) e z-score
Regressão linear simples e projeção de 12 meses
Índice de alerta de meses críticos
Agregação opcional em PySpark
Tabelas finais
Exportação em CSV e Excel
Tecnologias
Python
Pandas, NumPy, SciPy e Matplotlib
PySpark (opcional, usado na agregação por ano)
Google Colab
Como executar
Abra o código no Google Colab.
Execute as células na ordem. O código tenta baixar a base do ISP-RJ com tempo limite; se o site não responder, faça o envio manual do arquivo CSV quando o código pedir.
Ao final, as tabelas e os gráficos são gerados e exportados em CSV e Excel.
Principais resultados
Medida	Resultado
Meses analisados	96
Média mensal da violência doméstica (proxy)	312,42
Desvio padrão mensal	47,68
Regressão: inclinação (a)	0,3253 ocorrência por mês
Regressão: R²	0,036
Regressão: p-valor	0,0636 (não significativo a 5%)
Outliers da violência doméstica (proxy)	5 por IQR e 2 por z-score
Meses no índice de alerta	90 normais, 6 de atenção e 0 críticos
Conclusão: os dados apontam uma leve tendência de alta, mas sem evidência estatística suficiente para afirmar que a violência doméstica está aumentando. A maior parte da variação é oscilação de mês para mês.
Limitações
Feminicídio: só 15 dos 96 meses têm dado, com 2 registros no total (o primeiro em 01/2025). Por isso a série não foi preenchida e não foi possível calcular tendência nem regressão para esse indicador.
A base é agregada: "identificar feminicídios" aqui significa detectar períodos atípicos, e não casos individuais.
O índice de violência doméstica é uma aproximação (proxy), e não uma contagem oficial desse tipo de ocorrência.
Próximos passos
Obter a série longa de feminicídio.
Calcular taxas por 100 mil mulheres.
Testar modelos que considerem sazonalidade.
Incluir escuta da comunidade e de organizações de apoio às mulheres.
Autores
Bruno Conceição Pereira de Souza: arquivos, dados e slides
Kaio Côrtes do Valle: código em Python
Orientação: Profa. Simone Gama, Estácio Niterói.
Em caso de violência
Violência doméstica é crime. Denuncie pelo Ligue 180.
