# Previsão de Acidentes de Trânsito: Um Estudo de Caso Usando Dados Históricos
Introdução
No início de 2023 comecei a acompanhar reportagens na televisão que relatavam a possível descontinuidade da presença de alguns radares de fiscalização eletrônica na cidade do Recife, o que acabou se concretizando em meados de Junho do mesmo ano. Segundo a matéria do G1 ([link de acesso]([url](https://g1.globo.com/pe/pernambuco/noticia/2024/02/27/parte-dos-radares-de-velocidade-no-recife-esta-desativada.ghtml))), alguns radares de velocidade foram desativados. Como morador e motorista na cidade do Recife, comecei a me questionar sobre quais poderiam ser os impactos da ausência desta fiscalização em vias importantes e decidi buscar entender melhor o que esperar diante deste cenário. Desenvolvi este projeto que tem como objetivo apresentar os resultados obtidos através da análise dos dados históricos de acidentes entre 2021 e 2023, da identificação de tendências e previsão para o número de acidentes no primeiro semestre de 2024, visando conscientizar os motoristas e alertar as autoridades responsáveis. Utilizando modelos de séries temporais, como o SARIMA, pude construir previsões para e este ano e analisar o impacto potencial da desativação dos radares de velocidade.

Objetivo do Estudo
O objetivo principal deste estudo é responder às seguintes perguntas:

Houve um aumento no número de acidentes desde a desativação dos radares?
Como o número de vítimas evoluiu ao longo do tempo?
Podemos prever o número de acidentes para o primeiro semestre de 2024?
Dados e Preparação
Os dados utilizados neste estudo foram obtidos na plataforma Dados Recife ([link de acesso]([url](http://dados.recife.pe.gov.br/dataset/acidentes-de-transito-com-e-sem-vitimas))), sendo esta alimentada anualmente com dados fornecidos pela própria prefeitura. Eles contêm informações detalhadas sobre acidentes de trânsito, incluindo o número de veículos envolvidos, tipo de veículos, vítimas e vítimas fatais, além da data e local do acidente.

Tratamento de Dados
Inicialmente, os dados passaram por um processo de limpeza e transformação:

Substituição de vírgulas por pontos nas colunas numéricas.
Conversão dos valores de diferentes tipos de veículos em números reais.
Conversão dos valores em “data” para o formato datetime.
Criação de novas colunas para facilitar a análise, como total_automoveis (soma de todos os veículos envolvidos).
Agregação dos Dados
Os dados foram agregados mensalmente e semestralmente, sendo a agregação mensal para capturar melhor as tendências temporais, já a semestral serviu para fins analíticos e informativos. Isso foi feito utilizando o método resample do Pandas, que permitiu a soma dos acidentes por mês e semestre.

Análise Exploratória
Realizei uma análise exploratória para entender melhor os dados:

O número de acidentes por mês e semestre.
A evolução do número de vítimas ao longo do tempo.
Comparação do período anterior e posterior à desativação dos radares.

Gráficos
Aqui estão alguns gráficos que ilustram essas tendências:

Gráficos de Linha mostrando a evolução do número de acidentes, veículos envolvidos e vítimas por mês e por semestre.


Modelo Preditivo
Para prever o número de acidentes em 2024, usei o modelo SARIMA, que é adequado para séries temporais com sazonalidade. Após experimentar diferentes combinações de parâmetros, encontrei uma configuração que oferecia o melhor ajuste.

Previsões
Com o modelo ajustado, fiz previsões para os próximos seis meses. O gráfico abaixo mostra a previsão comparada com os dados históricos.

Gráfico de Linha representando os dados históricos e a predição para o primeiro semestre de 2024 em relação ao número de veículos envolvidos em acidentes de trânsito
Gráfico de Linha representando os dados históricos e a predição para o primeiro semestre de 2024 em relação ao número de vítimas de acidentes de trânsito
Conclusão
As previsões indicam que o número de acidentes pode continuar aumentando em 2024, especialmente se não forem implementadas novas medidas de segurança. Este estudo destaca a importância dos radares de velocidade e outros controles para a prevenção de acidentes.

Próximos Passos
Continuar monitorando os dados de acidentes em 2024 para validar as previsões.
Explorar modelos de aprendizado de máquina, como Random Forest ou XGBoost, para compará-los com o SARIMA.
Avaliar o impacto de outras variáveis, como condições climáticas e eventos locais, no número de acidentes.
