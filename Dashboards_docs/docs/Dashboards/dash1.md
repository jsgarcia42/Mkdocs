# Análise de churn

## Objetivos
Este dashboard tem como função apoiar os times xx, yy e zz no acompanhamento de cancelamentos e indicadores relacionados ao comportamento dos clientes da Bancorbras. 

## Descrição
O relatório é alimentado por dados provenientes de fontes como Excel, Datalake e Banco de Dados SQL, garantindo que a base de dados seja correta e confiável para análise.

As medidas e cálculos importantes incluem a xx, yy, zz, entre outros indicadores relevantes para o acompanhamento de comportamentos dos clientes, principalmente quanto à propenção de cancelamento. 

É importante mencionar que as informações são atualizadas diariamente por meio de atualizações agendadas no Power BI.

O Dashboard deve ser acessado através do dashboard **Dash Matriz** localizado no ambiente xyz. Existem acessos específicos para cada tipo de usuário.
Caso precise de auxílio com acesso, procure Fulaninho da Bancorbras ou Ciclano da A3Data.

## Histórico e evolução
Criador: [Nome do criador]
Data de Criação: [Data de criação]
Descrição: [Breve descrição do propósito e objetivo do Dashboard A]

### Contexto histórico
O Dashboard A foi inicialmente criado por [Nome do criador] em [Data de criação] para atender às demandas de acompanhamento de vendas da equipe de vendas. 

Durante o processo de desenvolvimento, [Nome do criador] enfrentou desafios relacionados à integração de dados de diferentes fontes e à otimização do desempenho das consultas. Após várias iterações e refinamentos, o Dashboard A evoluiu para uma ferramenta fundamental no monitoramento das metas de vendas e análise do desempenho da equipe.

### Observações Importantes
Inclua quaisquer observações relevantes sobre as decisões de design, suposições feitas, limitações técnicas ou outras informações importantes relacionadas aos dashboards.

### Principais decisões e recursos do dash
Decisão 1: [Explicação da decisão tomada e o motivo por trás dela]

Decisão 2: [Explicação da decisão tomada e o motivo por trás dela]

Decisão 3: [Explicação da decisão tomada e o motivo por trás dela]

## Documentação e modelagem de dados

### Tabelas e colunas
Este dashboard utiliza as seguintes tabelas e colunas para sua modelagem de dados:

**Tabela "dCliente"**
Contém informações básicas sobre os clientes da empresa. 
Conta com as seguintes colunas: 
- data
- região 
- produto
- quantidade vendida
- receita

**Tabela "dRFM"**
Contém apenas uma coluna referente à persona dos clientes da empresa.

**Tabela "Glossário"**
Contém informações importantes para esclarecimento dos principais termos presentes no dashboard. Conta com as seguintes colunas:

- Descrição
- Fórmula
- Nome do indicador
- Representação visual
- Tabela Data Lake
- Tabela Power BI


**Tabela "heatmap_populacao_total2"**
Contém informações detalhadas referentes a cada uma das personas da empresa.
Conta com as seguintes colunas: 

- Assíduo
- Data Estudo
- Data Final
- Data Inicio
- Família
- Família Plus
- Planejado
- Promissor Plus
- Recém
- RFM
- RMF Ordenado
- Total


**Tabela "heatmap_porcentagem_churn2"**
Contém informações detalhadas referentes a cancelamento, detalhando aspectos diferentes, relacionados a cada uma das personas da empresa.
Conta com as seguintes colunas:

- Assíduo
- Data Estudo
- Data Final
- Data Início
- Família
- Família Plus
- Planejado
- Promissor Plus
- Recém
- RFM
- RFM Ordenado
- Total


**Tabela "result_ocorrencia2"**
Contém informações financeiras relacionadas às personas da empresa.
Contém as seguintes colunas: 

- Código cliente
- Comportamental
- Data
- Idade
- Monetário
- Monetário 2
- Ocorrência churn
- Recência
- Recência entre reservas
- RFM
- Tempo de vida
- Tempo de Vida 2


**Tabela "RLS"**
Tabela de apoio para medidas de segurança em nível de linha.
Contém as seguintes colunas: 

- Carimbo de data/hora
- Email
- Endereço de e-mail
- Ordem
- Pagina
- Usuario


**Tabela "TB_Diaria_disponivel"**
Contém informações referentes à diárias disponíveis dos cliantes da empresa.
Conta com as seguintes colunas:

- cli_codigo
- data_movimentacao
- paq_codigo
- paq_indicativo_encerramento
- proximo_vencimento_diaria
- qtd_diaria_disponivel
- quantidade_diarias
- res_codigo
- res_data_fim
- res_data_inicio
- res_situacao
- tipo_conversao
- tipo_movimentacao
- tipo_operacao
- tit_numero
- total_titulo


### Relacionamentos
Os relacionamentos entre as tabelas são configurados da seguinte maneira: 

- a tabela "result_ocorrencia2" está relacionada às tabelas "dCliente" e "TB_Diaria_disponivel" por meio da coluna "Código do cliente" e está relacionada às tabelas "heatmap_populacao_total2" e "dRFM" por meio da coluna "RFM"
- dRFM[RFM](1) - heatmap_porcentagem_churn2[RFM](1) = um para um (1-1)

### Tratamento dos dados
**Tabela "dCliente"**

- Alteração na tipagem dos dados, colocado a tipagem correta
- Remoção do Underscore 
- Primeira letra de cada palavra maiúscula na coluna 'categoria'

**Tabela "dRFM"**

- limpeza dos dados
- renomear colunas

**Tabela "Glossário"**
Nenhum tratamento realizado

**Tabela "heatmap_populacao_total2"** 

- Alteração na tipagem dos dados, colocado a tipagem correta
- Ajuste dos nomes dos clientes
- Data Final

**Tabela "heatmap_porcentagem_churn2"**

- teste
- abc abc cbda
- Testando frase
- Exemplo de tratamento realizado
- Aqui 123 e 456

**Tabela "result_ocorrencia2"**
Nenhum tratamento realizado

**Tabela "RLS"**
Nenhum tratamento realizado

**Tabela "TB_Diaria_disponivel"**
Nenhum tratamento realizado

### Medidas

- Custos
- Despesas
- Lucro
- Número de vendas
- Receita

## Descrição da visualização de dados
O Dashboard XYZ utiliza uma variedade de visualizações de dados para apresentar as informações de maneira clara e concisa. Essas visualizações são divididas em **duas páginas** , que podem ser acessadas através da **Home**:

- Análise de propensão ao cancelamento / churn
- Análise de Churn por Segmentação

Abaixo temos os visuais utilizados em cada página:

**Análise de propensão ao cancelamento / churn**

- Filtro cliente ativo: selecionar se deseja escolher os clientes ativos ou inativos;
- Data Estudo: visual com a última data de atualização dos dados;
- Proporção de churn por segmentação: gráfico de pizza que mostra a % de cancelados por cada segmentação de persona;
- Proporção de churn por comportamental: gráfico de pizza que mostra a % de cancelados por cada segmentação de detalhe da persona;
- Segmentação x Comportamental: gráfico de barras clusterizadas com a quantidade de cancelamentos por segmentação x comportamental;
- Proportção de propensão a taxa de churn: gráfico de rosca com a % de propensão à taxa de churn;
- Coluna à esquerda: opções de limpar todos os filtros e resetar o visual, voltar para a página que o usuário estava navegando antes ou ir para a Home.

**Análise de Churn por Segmentação**

- Filtros cliente ativo, nome do cliente e código do cliente: selecionar se deseja escolher os clientes ativos ou inativos, filtrar pelo nome ou código do cliente;
- Data Estudo: visual com a última data de atualização dos dados;
- Cards: informações de total de clientes, total selecionados e % dos selecionados conforme seleções realizadas nos outros visuais e filtros da página;
- Segmentação e comportamental: opções de filtro segmentados;
- Tabela: informações detalhadas para visualização das informações dos clientes conforme segmentações escolhidas em outros visuais e filtros da página;
- Coluna à esquerda: opções de limpar todos os filtros e resetar o visual, voltar para a página que o usuário estava navegando antes ou ir para a Home.

## Instruções de uso
Para utilizar o Dashboard Análise de Churn, siga as seguintes instruções:

1. Acesse o Power BI por meio do workspace do Power BI.
2. Faça login utilizando suas credenciais de acesso.
3. Navegue até a seção "Dashboards" e selecione o *Dashboard Matriz*. Através dele, acesso o dashboard *Análise de churn*.
4. Para filtrar os dados, utilize os filtros localizados na lateral direita do Dashboard. Selecione as opções desejadas para segmentar os dados exibidos.
5. Interaja com as visualizações clicando nos elementos para obter mais detalhes ou visualizar informações adicionais.
6. Caso deseje exportar os dados, utilize as opções de exportação disponíveis no Power BI para salvar as informações em formatos como Excel ou PDF.

## Notas e Comentários

- Durante a criação do Dashboard XYZ, foram consideradas as metas de desempenho da empresa e as necessidades específicas dos usuários finais.
- Para garantir a precisão dos dados, foram realizadas validações e reconciliações com as fontes originais, garantindo a confiabilidade dos resultados.
- As cores utilizadas nas visualizações foram escolhidas para garantir uma melhor legibilidade e destacar informações relevantes.
- É importante ressaltar que o Dashboard XYZ foi projetado para fins de análise e monitoramento, não substituindo uma análise aprofundada ou a tomada de decisões baseada em informações complementares.