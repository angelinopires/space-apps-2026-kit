# 09. Harmonização dos focos de calor MODIS e VIIRS

**Título original:** Harmonization of MODIS and VIIRS Hot Spots

**Dificuldade:** Avançado / Intermediário
**Áreas temáticas:** Ciência da Terra, Software
**Página oficial:** https://www.spaceappschallenge.org/2026/challenges/modis-and-viirs-hot-spots/

> Fonte: página oficial do desafio no NASA Space Apps Challenge 2026. Tradução informativa para consulta offline; em caso de dúvida, a página oficial em inglês prevalece.

Entender como a atividade de queimadas se distribui pelo planeta ao longo do tempo, incluindo incêndios florestais e queimadas agrícolas intensas o bastante para serem detectadas por sensores de satélite, permite antecipar períodos críticos, orientar o monitoramento e melhorar a resposta a incêndios. Os satélites acompanham focos de incêndio ativos há mais de duas décadas, mas o registro está dividido entre sensores cujos dados não podem ser comparados diretamente, deixando os gestores de incêndio sem um retrato consistente de quando e onde houve queimadas. O seu desafio é criar um aplicativo web que harmonize esses registros em um calendário de atividade de queimadas baseado em focos de incêndio ativos, permitindo que equipes de alerta precoce e de resposta a emergências, cientistas e gestores de terras examinem padrões históricos de incêndio, condições incomuns e períodos críticos dentro de uma área de interesse selecionada.

    

## Contexto
Regimes de fogo
Alguns ecossistemas precisam de incêndios periódicos para manter sua função e sua estrutura. No entanto, mudanças na intensidade, na extensão e na frequência dos incêndios podem ter impactos negativos sobre o clima, a sociedade e a biodiversidade, além dos serviços ecossistêmicos que ela oferece. Os incêndios também podem causar perda de vidas e de bens, degradação da saúde e risco agudo para os gestores de incêndio.
Como os humanos modificaram os padrões globais de vegetação, ignição e clima ao longo de milênios, os incêndios, tanto em escala local quanto global, estão cada vez mais ligados à ação humana.
A atividade de queimadas envolve incêndios florestais em vegetação natural e áreas de floresta, além de incêndios antrópicos associados à agricultura, ao desmatamento, ao descarte de resíduos e a atividades industriais. É um dos muitos fenômenos dinâmicos que podem ser detectados por sensoriamento remoto.
Detecção e monitoramento de incêndios por satélite
Modelos climáticos projetam que o clima propício a incêndios (fire weather) se tornará mais comum e mais intenso. Os satélites de observação da Terra (EO) oferecem soluções tecnológicas para detecção precoce, resposta rápida e avaliação pós-incêndio, medindo radiação térmica e fumaça de escalas regionais a globais.
Detecção de focos de calor na superfície da Terra
Os satélites EO fornecem informações sobre a localização, a intensidade e a evolução temporal dos incêndios. Sensores de satélite que operam na faixa do infravermelho térmico (TIR) podem detectar focos de calor na superfície da Terra gerados por incêndios urbanos e florestais, erupções vulcânicas e processos industriais, como os flares de gás em operações de petróleo e gás.
Para incêndios ativos, a detecção e o monitoramento dependem principalmente de medições no infravermelho médio (MIR) e no TIR, onde a combustão ativa produz seu sinal mais forte. Sensores como o MODIS e o VIIRS fornecem detecção de anomalias térmicas em tempo real, permitindo a identificação precoce de focos de calor e a avaliação de áreas queimadas.
Calendários de atividade de queimadas
Com base nos focos de calor detectados por satélite, é possível desenvolver calendários de atividade de incêndios que integrem informações históricas a dados recentes, permitindo a identificação visual rápida de padrões sazonais, anomalias e tendências em cada região.
Os sensores MODIS a bordo dos satélites Terra e Aqua fornecem mais de duas décadas de observações, mas estão chegando ao fim de sua vida operacional e estão sendo substituídos por sensores VIIRS. Seus registros não podem ser comparados diretamente sem harmonização, já que o MODIS e o VIIRS têm resoluções espaciais, sensibilidades e horários de observação diferentes.
Aí está a raiz do desafio. À medida que a frequência e a intensidade dos incêndios aumentam, os gestores de emergência se beneficiam de um calendário de focos de calor atualizado e consistente, que lhes permita visualizar rapidamente, por exemplo, quais meses e anos tiveram a maior atividade de incêndios, e comparar a atividade de queimadas do mês atual com a mediana histórica de uma área selecionada.
Você pode considerar harmonizar os focos de calor do FIRMS, da NASA Earthdata, combinando a extensa série histórica do MODIS com a continuidade e o maior nível de detalhe do VIIRS.
Os gestores de emergência poderiam então usar o aplicativo web para monitorar regiões sensíveis, reconhecer mudanças em relação aos padrões históricos e fortalecer a previsão e a resposta a incêndios.

## Objetivos
O seu desafio é desenvolver, em um aplicativo web, um calendário harmonizado de atividade de queimadas baseado em focos de incêndio ativos, combinando a extensa série histórica do MODIS com a continuidade e o maior nível de detalhe do VIIRS, para oferecer uma série temporal consistente da atividade de focos de calor.
Este desafio pode ser abordado em duas partes. A primeira é a harmonização dos focos de calor do MODIS e do VIIRS, de modo que, ao final dessa fase, o sensor de origem deixe de importar e o foco passe a ser os padrões, as tendências e as anomalias.
A segunda envolve desenvolver um aplicativo web que receba como entrada os dados harmonizados de focos de calor. Por meio dessa ferramenta visual, o usuário poderia selecionar uma região e um intervalo de datas específico e depois baixar análises e visualizações da atividade de incêndios.
Um calendário de atividade de queimadas que mostre o número de focos de calor detectados do início dos anos 2000 até hoje, construído sobre o conjunto de dados harmonizado e integrado ao aplicativo web, daria aos gestores de emergência uma visão do histórico de incêndios de uma área: quais períodos do ano têm mais incêndios, quais anos tiveram mais atividade de queimadas e como um incêndio atual se compara aos anteriores.
Além das informações numéricas, você pode considerar como rampas de cores poderiam representar semelhanças e diferenças no número de focos de calor detectados ao longo dos meses, oferecendo uma forma acessível e intuitiva de visualizar a atividade de incêndios. Um arquivo CSV para download com os focos de calor detectados em uma busca seria outra saída útil.

## Pontos a considerar
Você pode (mas não é obrigado a) considerar o seguinte:
- Seu público-alvo pode incluir equipes de alerta precoce e de resposta a emergências, cientistas, gestores de terras e bombeiros.
- Considere tornar seu aplicativo web interativo, por exemplo, com um mapa em que os usuários possam desenhar a área de interesse, ou com uma opção para digitar latitude e longitude.
- Considere usar rampas de cores acessíveis.
- Sua ferramenta poderia apresentar um calendário de queimadas
- Sua ferramenta poderia focar em alguns índices e números-chave e apresentá-los por meio de visualizações de dados, como:
- Comparações históricas, incluindo anomalias em relação a médias de vários anos
- Número de incêndios detectados e registrados

Para dados e recursos relacionados a este desafio, consulte a aba Resources no topo da página. Mais recursos podem ser adicionados antes do início do hackathon.

Crédito da foto: Comisión Nacional de Actividades Espaciales da Argentina (CONAE)

## Recursos

> A NASA não endossa nenhuma entidade que não seja do governo dos EUA e não se responsabiliza pelas informações contidas em sites que não sejam do governo dos EUA. Nos sites que não são do governo dos EUA, os participantes devem cumprir os parâmetros de uso de dados de cada site.

## Dados e recursos da NASA
- [FIRMS NASA EARTHDATA: Fire Information for Resource Management System](https://www.earthdata.nasa.gov/data/tools/firms): O Fire Information for Resource Management System (FIRMS) permite acessar imagens de satélite globais em tempo quase real, incêndios ativos/focos de calor e produtos relacionados para identificar a localização, a extensão e a intensidade da atividade de incêndios florestais. As ferramentas e aplicações do FIRMS fornecem dados geoespaciais, produtos e serviços para apoiar a comunidade mais ampla de gestão de incêndios e informar o público em geral.
