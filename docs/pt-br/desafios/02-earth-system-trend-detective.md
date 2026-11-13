# 02. Seja um detetive das tendências do sistema terrestre!

**Título original:** Be An Earth System Trend Detective!

**Dificuldade:** Avançado
**Áreas temáticas:** Ciência da Terra, Software
**Página oficial:** https://www.spaceappschallenge.org/2026/challenges/earth-system-trend-detective/

> Fonte: página oficial do desafio no NASA Space Apps Challenge 2026. Tradução informativa para consulta offline; em caso de dúvida, a página oficial em inglês prevalece.

O sistema ambiental interconectado da Terra está sempre mudando e, quando essa mudança segue uma direção consistente (subindo ou descendo, aumentando ou diminuindo, engrossando ou afinando), as variáveis medidas a refletem. Mas uma variável de dados de ciência da Terra pode apresentar tendência em um sentido em uma região e no sentido oposto em outra, mesmo quando o mesmo processo causa as duas. A enorme quantidade de variáveis de dados de ciência da Terra dificulta escolher variáveis que possam indicar mudança e depois fazer uma análise sobre elas. Seu desafio é criar uma ferramenta que selecione variáveis medidas por missões de ciência da Terra ou produzidas por modelos de ciência da Terra, visualize como elas mudam ao longo do tempo e determine o que está mudando, onde está mudando, quanto está mudando e se essas mudanças são o que os cientistas chamam de "significativas".

## Contexto
Instrumentos em satélites observam muitos aspectos diferentes do sistema terrestre: em terra, na atmosfera e nos oceanos. Modelos globais também usam dados de instrumentos de satélite e outros tipos de dados para examinar e analisar o sistema terrestre. Um motivo importante para isso é observar e caracterizar mudanças no sistema terrestre. As mudanças, especialmente as que seguem uma direção específica ao longo do tempo (uma tendência), indicam tanto os processos que as causam quanto os processos que responderão a elas.
Um fator complicador nesse trabalho é a grande variedade de variáveis que podem ser estudadas. Outro é que as mudanças em uma variável podem seguir uma direção em uma região e a direção oposta em outra, mesmo quando as duas tendências são causadas pelo mesmo processo! Assim, o problema tem duas partes importantes: encontrar variáveis com tendência, desde as simples, como temperatura e chuva, até as mais complexas, como evaporação ou vazão de rios; e analisar tendências em regiões específicas da terra, do oceano ou até em níveis da atmosfera.
Instrumentos como o Moderate Resolution Imaging Spectroradiometer (MODIS), o Ozone Monitoring Instrument (OMI), o Atmospheric Infrared Sounder (AIRS) e o Global Precipitation Measurement (GPM) fornecem variáveis analisáveis. Modelos globais, em especial o Modern Era Retrospective analysis for Research and Applications, Version 2 (MERRA-2) e o Global Land Data Assimilation System (GLDAS), fornecem muitas outras. Encontrar tendências significativas, analisá-las e relacioná-las aos processos que as causam é um dos usos mais importantes dos dados de ciência da Terra da NASA.

## Objetivos
Uma resposta bem-sucedida a este desafio reunirá vários elementos importantes.
O primeiro é identificar variáveis de ciência da Terra de interesse que possam ser investigadas em busca de possíveis tendências. Como o Contexto observa, a NASA e outras agências espaciais oferecem inúmeras variáveis, algumas familiares e outras mais especializadas, para uso em ramos específicos da ciência.
O segundo é obter as variáveis de dados para uma região específica, já que a maioria das tendências nos dados não será global (embora algumas possam ser!).
O terceiro é gerar e visualizar uma série temporal da variável e da região de interesse, cobrindo um período longo o bastante para permitir análise estatística.
O elemento final do desafio é fazer uma análise estatística básica dessa série temporal, indicando a taxa de variação ao longo do tempo, e testar a significância da tendência com métodos como o teste t, o teste de Mann-Kendall ou intervalos de confiança.
Sites de dados oferecem ferramentas que geram séries temporais, e pacotes de análise estatística fornecem testes básicos de significância. Uma resposta que faça tanto a visualização quanto a análise atende ao escopo completo deste desafio.

## Pontos a considerar
Você pode (mas não é obrigado a) considerar o seguinte:
Público
- Este desafio envolve dados científicos e análise estatística, então o público provável são estudantes do ensino médio e universitários, além de pessoas do público em geral com alguma formação científica.
- Fornecer definições simples das variáveis ajudaria bastante esses usuários.
- A ideia é ajudar os usuários a se tornarem detetives de dados: encontrar variáveis de interesse e depois determinar se elas apresentam uma tendência e se essa tendência é significativa.

Abordagem
- Os usuários poderiam responder a uma pequena série de perguntas sobre o que ou onde gostariam de investigar, e as respostas permitiriam buscar variáveis de dados relacionadas. Seria muito útil oferecer alguns exemplos de demonstração que o usuário pudesse assistir e que o ajudassem a entender como a ferramenta funciona.
- Embora não seja obrigatório, a IA poderia ser útil aqui para identificar dados com potencial de mostrar tendências em áreas específicas, com base em notícias e artigos de pesquisa ou nas características de uma região, como um deserto, uma floresta tropical, um estuário de maré ou a atmosfera acima de uma grande cidade.

Trabalhando com os dados
- Os dados de ciência da Terra estão disponíveis em várias resoluções temporais: horária, a cada 3 horas, diária e mensal. Para este desafio, os dados diários e mensais provavelmente são os mais fáceis de processar.
- Encontrar uma tendência é interessante mesmo que ela não chegue ao nível de significância. Às vezes, tudo de que uma tendência precisa para se tornar significativa é um período mais longo de dados.
- Considere procurar ferramentas publicamente disponíveis para plotar dados hidrológicos, oferecidas por organizações externas como o Consortium of Universities for the Advancement of Hydrologic Science, Inc. (CUAHSI).

A análise de tendências com dados de ciência da Terra pode ser complexa. As tendências podem ser não lineares, e algumas só ficam evidentes quando ciclos regulares, como o ciclo sazonal, são removidos. Análises de tendência mais complexas estão além do escopo previsto para este desafio; detectar e analisar tendências lineares seria um ótimo começo.
Para dados e recursos relacionados a este desafio, consulte a aba Recursos no topo da página. Mais recursos podem ser adicionados antes do início do hackathon.

## Recursos

> A NASA não endossa nenhuma entidade que não seja do governo dos EUA e não é responsável pelas informações contidas em sites que não sejam do governo dos EUA. Em sites que não sejam do governo dos EUA, os participantes devem cumprir os parâmetros de uso de dados do site em questão.

## Dados e recursos da NASA
- [Giovanni](https://giovanni.gsfc.nasa.gov/): Ferramenta versátil que oferece menus de inúmeras variáveis de dados e permite gerar séries temporais e baixar seus dados.
- [Hydrology Time Series](https://disc.gsfc.nasa.gov/information/tools?title=Hydrology%20Time%20Series): Permite gerar séries temporais com dados hidrológicos.
- [AppEEARS](https://appeears.earthdatacloud.nasa.gov/): Oferece uma forma simples e eficiente de acessar e transformar dados geoespaciais de vários arquivos de dados federais dos EUA. Inclui geração de séries temporais.
- [Climate Data Online (CDO)](https://www.ncei.noaa.gov/cdo-web/): O CDO dá acesso gratuito ao arquivo do NCDC com dados históricos globais de tempo e clima, além de informações sobre o histórico das estações. O site inclui uma ferramenta de mapas.
- [Time-Series Analysis of Remotely-Sensed SeaWiFS Chlorophyll in River-Influenced Coastal Regions](https://ntrs.nasa.gov/api/citations/20090042747/downloads/20090042747.pdf): Artigo de pesquisa que demonstra a criação de séries temporais e o teste de significância.

## Recursos das agências espaciais parceiras
- [Royal Netherlands Meteorological Institute (KNMI) Climate Explorer](https://climexp.knmi.nl/): O KNMI Climate Explorer é uma ferramenta científica de análise baseada na web, desenvolvida e mantida pelo KNMI. Foi criada para ajudar pesquisadores, estudantes e analistas do clima a explorar, analisar e visualizar dados climáticos de uma ampla gama de fontes.
- [Statistical test methods to detect trends in time series data](https://medium.com/@snp.kriss/statistical-test-methods-to-detect-trends-in-time-series-data-b361a0ec530b): Artigo sobre testes de tendência em dados.
- [A Comprehensive Guide to Statistical Significance](https://www.statsig.com/perspectives/a-comprehensive-guide-to-statistical-significance): Um guia sobre testes de significância.
CSA (Canadian Space Agency)
- [Radarsat Constellation Mission (RCM) - Data](https://donnees-data.asc-csa.gc.ca/en/dataset/rcm): A RADARSAT Constellation Mission (RCM) é a nova geração de satélites de observação da Terra do Canadá. A RCM inclui um trio de satélites de observação da Terra, capazes de varrer a Terra de dia ou de noite e em qualquer condição climática. A RCM foi projetada para oferecer soluções eficazes em três áreas principais: vigilância marítima (gelo, vento na superfície, poluição por óleo e monitoramento de navios); gestão de desastres (mitigação, alerta, resposta e recuperação); e monitoramento de ecossistemas (agricultura, áreas úmidas, silvicultura e mudanças costeiras).
- [Geo.ca](http://geo.ca/): O GEO.ca é a fonte definitiva de informações geoespaciais abertas do Canadá. Parte desses dados pode ser útil para monitorar questões ambientais no Canadá.
- [SWOT Mission - Information](https://www.asc-csa.gc.ca/eng/satellites/swot/): A missão SWOT nos fornece informações novas e detalhadas sobre um dos recursos mais importantes que compartilhamos: a água. Liderada pela NASA e pela agência espacial da França (CNES), em colaboração com a CSA e a UK Space Agency, a SWOT levanta 90% da água superficial da Terra, medindo ao longo do tempo as variações na elevação da superfície da água de lagos, rios, reservatórios e oceanos.
- [Monitoring and protecting our ecosystem from space](https://www.asc-csa.gc.ca/eng/satellites/everyday-lives/monitoring-and-protecting-our-ecosystems-from-space.asp): Este site traz mais informações sobre como os dados de satélite podem ajudar a monitorar mudanças e promover o uso responsável da terra e dos recursos naturais para proteger o ecossistema.
- [Synthetic Aperture Radar python Tutorial](https://github.com/asc-csa/Synthetic_Aperture_Radar_Tutorial): Este tutorial demonstra como trabalhar com imagens SAR usando Python e QGIS. Inclui passos fáceis e práticos para acessar e visualizar dados.
