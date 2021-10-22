 # 🏬 Previsão de Vendas: Hossman Store

O objetivo desse projeto é fornecer para o time de negócios uma previsão de vendas de produtos durante as próximas seis semanas, utilizando para essa algoritmos de "Machine Learning" para nos. Outro aspectos que realizamos é a validação ou não de hipótestes de negócios das quais visam gerar insights tanto para a equipe de megócios como para outros times.

O resultado final desse projeto será uma tabela contendo o melhor e o pior cenário.

| __Melhor Cenário__ | __Pior Cenário__ | __Previsão__ |
| ----------------- | ----------------- | ----------------- | 
| R$ 288.554.280,06 | R$ 286.397.838,89 | R$ 287.476.064,00 |
___
### 🏢 Contexto do negócio:

A Houssman Store é uma plataforma digital que tem como modelo de negócio a compra e a venda de produtos diversos, para melhorar o seu negócios e faturamentos, estes utilizam a tecnologia e os dados gerados por meio dessas tanto para analisar as melhores oportunidades de negócios, como para direcionar a empresa para um caminho.

O objetivo do case é fornecer um modelo de previsão da venda de produtos, dando este suporte para as futuras decisões da empresa que pode acatar ou não as previsões desse modelo assim como verificar se este condiz com a realidade das vendas caso a empresa resolva seguir com este modelo.

___
### 👨‍💼 Questão do negócio:

Como você é um dos poucos integrantes da equipe de ciência de dados da empresa, em um belo dia os gerentes começaram a te ligar pedindo uma previsão de vendas nas próximas seis semanas, antes de iniciar executando a tarefa que lhe foi fornecida você primeiro conversou com os gerentes e depois percorreu os três passos abaixo:

- __Motivação:__ qual foi a motivação que os gerentes tiveram para realizar essa requisição sobre a previsão de vendas, sendo que conversando com estes percebemos que a motivação foi o pedido feito pelo CEO da empresa.

- __Causa Raiz:__ Entendido a motivação iremos na causa raiz, ou seja, iremos conversar com o CEO e verificar o porque este realizou esta requisição, sendo que ao conversar mais com o CEO, vimos que ele realizou esse pedido de previsão de vendas pois este gostaria de reformar as lojas preexistentes e para isso ele precisaria saber o quanto de dinheiro poderia utilizar para essa reforma.

- __Formato da Solução:__ Entendido a causa raiz do problema iremo combinar o formato de entrega, como no mundo nos negócios tudo é negociável, dissemos  que para ter uma velocidade maior, iremos entregar nesse primeiro ciclo uma tabela contendo o faturamento total previsto com o pior e melhor cenário, para assim ele ter uma idéia do quanto de dinheiro irá chegar na empresa para então realizar a decisão de reformar ou não as lojas ou em quais lojas reformar.

### Ciclo CRISP

Um método que utilizaremos tanto neste como em outros projetos de portfólio é o método CRISP (Cross Industry Standard Process for Data Mining,)presente no link abaixo: <br>
https://www.ibm.com/docs/en/spss-modeler/SaaS?topic=dm-crisp-help-overview

O objetivo desse método é passar pela mesma tarefa várias vezes, tendo cada ciclo "end to end", nos dando esse ciclo uma velocidade de entrega assim como o mapeamento de possíveis problemas a serem ocorridos futuramente, sendo que o ciclo que montamos nesse projeto tem o seguinte desenho

![Captura de tela de 2021-10-22 16-08-23](https://user-images.githubusercontent.com/46419374/138510162-7bf05413-c5ad-495f-94bd-aebbfb8fc897.png)

- **Questão e Entendimento do Negócio:** Nessas etapas como dito anteriormente realizaremos uma conversão com as outras equipes identificando a fonte do problema e em seguida definimos o formato da solução.
 
- **Coleta de Dados:** Neste realizaremos ou uma busca do banco de dados da empresa utilizando SQL ou então buscaremos dados fora destas, nesse projeto os dados foram fornecidos pela plataforma "Kaggle".
 
- **Limpeza dos Dados:** Realizaremos um preenchimento dos dados faltantes, assim como verificaremos os tipos de dados, estatísticas descritivas e renomeação de colunas.

- **Exploração dos Dados:** Essa é uma das etapas em que realizaremos o levantamento das hipóteses no intuito de gerar "insights" que sejam escaláveis para a empresa.

- **Modelagem dos Dados:** Chamamos essa etapa de "Feature Engeneering" da qual realizaremos a criação de hipóteses que facilitará 
___
### 📚 Dados:

Os dados foram extraídos da plataforma "Kaggle", usando o link abaixo:

https://www.kaggle.com/c/rossmann-store-sales

Contendo os seguintes atributos:

|***Atributo*** | ***Descrição*** |
| -------- | --------- |
|**Id**| Identificação que representa a dupla (data, loja).|
|**Store**| Identificação da loja |
|**Sales**| vendas da loja naquele dia |
|**Customers**|Número de clientes no dia |
|**Open**| Indicador se a loja está aberta ou fechada: 0 = fechada, 1 = aberta |
|**StateHoliday**| Indicador da presença de feriados, sendo estes. a = ferados públicos, b = Páscoa, c = Natal, 0 = Nenhum |
|**SchoolHoliday**| Indica se há ou não a presença de feriados escolares: 0 = não, 1 = sim. |
|**StoreType**| diferentes tipos de lojas, sendo estas a, b, c, d |
|**Assortment**| Indica a variedade de produtos por levels, sendo esses: a = básico, b = extra, c = extendido |
|**CompetitionDistance**|distância em metros com a loja competidora próxima |
|**CompetitionOpenSince[Month/Year]**| Indica o o ano e mês aproximado que o competidor mais próximo abrir a loja |
|**Promo**| Indica se a loja abriu uma promoção naquele dia | 
|**Promo2**| Indica se a loja continuou a Promo: 0 = Loja não está participando, 1 = Loja está participando |
|**Promo2Since[Year/Week]**| Descreve o ano e semana que a loja participou da promo2 |
|**PromoInterval**| Descreve os meses consecutivos que a loja participou da promoção.| 

___
### 💼 Premissas do negócio:

Antes de analisarmos os dados teremos que conhecer do negócio que estamos lidando, para isso podemos tanto conversar com outras equipes da empresa, realizando uma reunião com estas no intuito de tirar dúvidas e gerar "insights" ou então podemos estudar o negócio e gerar essas dúvidas e ideias nós mesmos. Como atualmente não temos contato com outras áreas iremos optar por pesquisar sobre o negócio e então retirar nossos "insights".

Uma das formas de gerar insights para o negócio é realizando um "mapa mental" como na imagem abaixo

![Captura de tela de 2021-10-22 14-59-40](https://user-images.githubusercontent.com/46419374/138501756-a4d9bb5f-9932-42ea-a9bb-9b62173ac194.png)

Esse aspecto será importante pois é a partir do levantamento desse mapa mental que iremos validar as hipóteses de negócios conforme nas etapas 

___
## Planejamento da solução:

### 🗺️ Exploração e Alteração de dados:

A primeira etapa do projeto foi realizar a coleta, tratamento e exploração dos dados. Nessa etapa foi possível realizar identificar necessidades de limpeza e transformação dos dados, sendo que neste projeto, realizamos uma análise estatística descritiva do conjunto de dados assim como também a criação de novas *features* para facilitar e proporcionar as visualizações e criações dos insights gerados a partir de hipótese de negócios que serão apresentados. A motivação da criação das novas features serão explanadas em outro momento.

  - *season:* estação do ano da venda do imóvel
  - *yr_life:* anos de vida do imóvel.
  - *level:* separa o preço dos imóveis em quartis, classificando  

### 📑 Hipóteses de negócios:

No intuito de melhor entender o negócio assim como auxiliar na análise exploratória, realizamos algumas hipóteses:

| __Hipótese__ | __Resultado__ | __Tradução para negócio__ |
| ------------ | ------------ | ------------ |
| __H1__ -Imóveis com vista para a água são em média mais caros se sim em quantos %? | Verdadeira | Imóveis com vista para água são aproximadamente 50% mais caros. Procurar investir em imóveis sem vista para água, por terem custo de negócio menor |
| __H2__ - Imóveis antigos são mais baratos, se sim em quantos %? | Falsa | A idade dos imóveis não contribui para a diminuição do preço dos imóveis |
| __H3__ - Quais são os atributos que mais contribuem para o aumento do preço? | - | Os atributos que contribuem para o aumento do preços são: ***quantidade de banheiros***, ***design do edifício*** e a ***área do imóvel*** |
___
### Seleção dos imóveis:

Para iniciar a resposta para as perguntas de negócio, foram realizados os seguintes passos:

__Quais são os imóveis que a House Rocket deveria comprar e por qual preço ?__
- Agrupar os imóveis por região ( *zipcode* );
- Cálculo da mediana dos preços pelo cep.
- Com a mediana calculada estabelecemos a seguintes cenários para realizar a compra de um imóvel: <br><br>
    - ***Cenário 1:***  Iremos comprar (Buy) se o preço do imóvel for menor que a média dos preços e a condição for maior que 3: <br>
    -    Compra = ( Preço < Média dos preços ) & (Condição >= 3)<br><br>
    - ***Cenário 2:***  Iremos comprar (Buy) se o preço do imóvel for menor que a média dos preços e a avaliação do design do edifício for maior que 7:<br>
    -    Compra = ( Preço < Média dos preços ) & (Design Edifício >= 7)<br><br>
    - ***Cenário 3:*** Iremos comprar (Buy) se o preço do imóvel for menor que a média dos preços, a condição for maior que 3 e a avaliação do design do edifício for maior que 7:<br>
    -    Compra = ( Preço < Média dos preços ) & (Condição >= 3) & (Design Edifício >= 7)

__Uma vez a casa comprada, qual o melhor momento para vendê-las e por qual preço ?__
- Com os dados selecionados da questão anterior, vemos que estes variam o preço conforme a temporada, com isso iremos agrupa-los por região ( *zipcode* ) e também por temporada (*season*);
- Dentro de cada região e temporada, calculamos a mediana do preço do imóvel em cada sazonalidade.
- Em seguida, calculamos o preço de venda dos imóveis levando em consideração as seguintes condições:

   1. Se o preço da compra for maior que a mediana da região + sazonalidade. O preço da venda será igual ao preço da compra + 10%
       - Preço Venda = Preço > Mediana Sazonalidade x 1,10
   2. Se o preço da compra for menor que a mediana da região + sazonalidade. O preço da venda será igual ao preço da compra + 30%
       -  Preço Venda = Preço < Mediana Sazonalidade x 1,30

## 📈 Resultados financeiros:

O objetivo desse projeto era responder as questões de negócio e fornecer uma lista de imóveis com opções de compra e venda, e consequentemente o __lucro máximo__ que poderá ser obtido se todas as transações ocorrerem. Sendo que o resultado financeiro previsto caso todas essas transações ocorram seria de acordo com a tabela abaixo

| __Número de imóveis__ | __Custo total__ | __Receita de vendas__ | __Lucro (profit)__ |
| ----------------- | ----------------- | ----------------- | ----------------- |
| 12.975 | US$ 5.345.126.211,00 | US$ 6.322.951.472,29 | US$ 977.825.261,30 |

## 😄 Conclusão:

O projeto tem como princípio responder a questão de negócio assim como gerar insights baseados em hipóteses de negócios que formulamos ou que foram trazidas pela empresa. Com esse problema respondido geramos o lucro total que seria gerado em nossa análise caso as nossas pré condições fossem estabelecidas.
