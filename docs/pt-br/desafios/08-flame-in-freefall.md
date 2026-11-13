# 08. Chama em queda livre: informações sobre segurança contra incêndios com IA a partir de dados de combustão em microgravidade

**Título original:** Flame in Freefall: SI-Powered Fire Safety Insights from Microgravity Combustion Data

**Dificuldade:** Avançado / Intermediário
**Áreas temáticas:** Exploração espacial
**Página oficial:** https://www.spaceappschallenge.org/2026/challenges/flame-in-freefall/

> Fonte: página oficial do desafio no NASA Space Apps Challenge 2026. Tradução informativa para consulta offline; em caso de dúvida, a página oficial em inglês prevalece.

Há décadas a NASA estuda como chamas e incêndios se comportam em microgravidade, reunindo ao longo do caminho um tesouro de dados experimentais. Esse conhecimento importa mais do que nunca agora que os humanos se preparam para voltar à Lua e seguir rumo a Marte, mas o volume de resultados dificulta encontrá-los, compará-los e entendê-los. O seu desafio é criar um painel (dashboard) interativo, movido por IA (inteligência artificial), que resuma, classifique e interprete essas descobertas para gerar informações de segurança contra incêndios para a exploração espacial humana.

    

## Contexto
O risco de incêndio é extremamente perigoso na exploração espacial! Ao descrever um alarme de fumaça que disparou durante a recente missão Artemis II, o comandante comentou: "[Se] você quer chamar a atenção de alguém bem rápido, faça o alarme de incêndio disparar na sua espaçonave quando você ainda está a uns 80.000 milhas de casa." Décadas antes, a tripulação da Apollo 13 enfrentou as consequências, com risco de morte, da explosão de um tanque de oxigênio a caminho da Lua. Do mesmo modo, uma tripulação multinacional sobreviveu a um incêndio a bordo da estação espacial Mir, causado pela falha de um gerador de oxigênio. Em 1967, a tripulação da Apollo 1 morreu durante um teste antes do lançamento, quando um incêndio irrompeu na espaçonave cheia de oxigênio.
Em comparação com a Terra, as chamas em queda livre (ou seja, em microgravidade) costumam ser dramaticamente diferentes por causa da ausência de empuxo e, portanto, da subida de gases quentes. Em vez de uma gota trêmula, a chama de uma vela se torna uma esfera azul fantasmagórica que depende da difusão para obter oxigênio.
O trabalho de segurança contra incêndios em espaçonaves da NASA se concentra em prevenção, detecção e supressão. A prevenção se dá pelo controle de fontes de ignição e pela seleção de materiais, que depende de entender os limites de inflamabilidade. Para facilitar o uso de trajes espaciais, espera-se uma atmosfera com mais oxigênio e pressão menor do que a da Terra na planejada base lunar (Moon Base) e nos rovers pressurizados. A inflamabilidade depende muito da concentração de oxigênio, e o fluxo de ar também é importante em microgravidade. Os estudos de inflamabilidade se concentram em materiais sólidos, como tecidos e plásticos, estudados nas investigações Burning and Suppression of Solids (BASS e BASS-II) e Spacecraft Fire Safety Demonstration (Saffire-I, -II e -III).
A detecção de incêndio foi testada em microgravidade nos estudos Smoke and Aerosol Measurement Experiment (SAME e SAME-R). A supressão foi estudada no Flame Extinguishment Experiment (FLEX), por meio da diluição da atmosfera da câmara com dióxido de carbono e hélio, ambos suprimem o fogo.

## Objetivos
Os resultados de experimentos de combustão em baixa gravidade, realizados por exemplo na Estação Espacial Internacional (ISS), estão sendo disponibilizados publicamente no banco de dados Physical Science Informatics (PSI) da NASA, mas a quantidade de dados pode ser esmagadora. Pode ser difícil de encontrar, mais difícil de comparar e ainda mais difícil de interpretar.
O seu desafio é criar um painel (dashboard) web movido por IA que resuma, classifique e interprete investigações de ciência da combustão para gerar informações fundamentais críticas de segurança contra incêndios. Você pode considerar permitir que os usuários:
- Identifiquem as investigações mais relevantes para as necessidades de segurança contra incêndios de ambientes habitáveis para tripulações, incluindo espaçonaves, estações espaciais, bases nas superfícies da Lua e de Marte e rovers pressurizados.*
- Extraiam dados que apoiem a modelagem preditiva de inflamabilidade e de cenários de incêndio na exploração espacial.
- Destaquem pesquisas que subsidiem o desenvolvimento de controles e equipamentos de segurança contra incêndios de próxima geração.

Neste desafio, você vai ajudar a transformar dados complexos em respostas claras e tornar o próximo grande salto mais seguro.
Seu painel também pode abordar possíveis aplicações dos dados do PSI na segurança contra incêndios na Terra. Os extintores de névoa de água fina desenvolvidos para uso na ISS têm aplicações práticas aqui na Terra, e a tecnologia da NASA também levou a melhorias na detecção de fumaça e nos equipamentos de bombeiros, incluindo roupas de proteção e cilindros de ar.
*A segurança contra incêndios envolvendo foguetes e propelentes geralmente está fora do escopo das pesquisas disponíveis no banco de dados PSI. As altas velocidades dentro dos motores de foguete tornam a combustão efetivamente independente da gravidade, embora o lançamento de um foguete dependa, é claro, fortemente da gravidade.

## Pontos a considerar
Você pode (mas não é obrigado a) considerar o seguinte:
- Seu público-alvo pode incluir professores, estudantes de pós-graduação, estudantes de graduação, pesquisadores aeroespaciais e engenheiros aeroespaciais.
- Considere como você poderia resumir e exibir atributos como:
- Objetivos experimentais
- Combustíveis, incluindo o formato e o tamanho das amostras ou dos queimadores
- Outras condições de teste, como concentração de oxigênio e velocidade do fluxo de ar
- Variáveis: como os testes de uma mesma investigação diferiram e como foram iguais?
- Sensores ou tipos de medição

- Considere como resumir e exibir semelhanças e diferenças entre diferentes investigações.
- Outras investigações no PSI- Um dos instrumentos usados para detecção de fumaça nos estudos SAME e SAME-R foi usado, em vez disso, para detectar poeira nos estudos Dust and Aerosol Measurement Feasibility Test (DAFT e DAFT-2).
- Embora queimasse combustíveis gasosos, o experimento Burning Rate Emulator (BRE), do projeto Advanced Combustion via Microgravity Experiments (ACME), foi um estudo da inflamabilidade de materiais em atmosferas paradas em função das propriedades do material.
- Outras investigações de combustão no banco de dados PSI (mas não citadas explicitamente acima) continuam relevantes para a segurança contra incêndios, só que de forma menos forte ou direta.

- Hardware- Os seis experimentos do projeto ACME apresentaram chamas de combustíveis gasosos e foram todos realizados com o mesmo conjunto modular de hardware do ACME no Combustion Integrated Rack (CIR).
- FLEX, FLEX-2 e a Cool Flames Investigation (CFI) apresentaram, cada um, gotas de combustível líquido em combustão e foram realizados com o Multi-user Droplet Combustion Apparatus (MDCA) no CIR.
- BASS, BASS-II, o Smoke Point In Co-flow Experiment (SPICE) e o Structure & Liftoff In Combustion Experiment (SLICE) apresentaram, em conjunto, combustíveis sólidos e gasosos. Cada uma dessas investigações foi realizada dentro do Microgravity Science Glovebox (MSG), usando o duto de fluxo modular com ventilador construído para o SPICE.

- Trajes espaciais e concentração de oxigênio- Para dar flexibilidade, os trajes espaciais são preenchidos com 100% de oxigênio a apenas 4,3 psi (libras por polegada quadrada), enquanto a pressão da Terra ao nível do mar é de 14,7 psi.
- Para evitar a doença da descompressão, os astronautas respiram oxigênio 100% antes da saída (pre-breathe) para eliminar o nitrogênio absorvido.
- Para reduzir a duração do pre-breathe e, assim, facilitar as excursões lunares, espera-se que a base lunar e o(s) rover(s) pressurizado(s) tenham pressão e concentração de oxigênio entre as do traje espacial e as da atmosfera da Terra.
- A concentração intermediária de oxigênio usada na Lua provavelmente será de 30% ou mais, com pressão correspondente de 10,2 psi ou menos. Em comparação com a atmosfera da Terra, isso é um aumento de mais de 40% na concentração de oxigênio, o que torna os materiais muito mais inflamáveis.
- Os testes em microgravidade com as maiores concentrações de oxigênio foram realizados como parte da Cool Flames Investigation with Gases (CFI-G) do ACME. Nesses testes, a câmara de combustão foi preenchida com uma mistura de nitrogênio e um gás inflamável (por exemplo, propano), enquanto uma mistura de oxigênio e nitrogênio com até 85% de oxigênio fluía do queimador esférico, criando uma chama de dentro para fora.

- Dados de gravidade parcial- Embora a NASA esteja muito focada no retorno de astronautas à superfície da Lua e no estabelecimento de uma base lunar em preparação para a futura exploração humana de Marte, atualmente não há dados de combustão em gravidade parcial disponíveis no PSI. Esperamos que esses dados sejam adicionados no futuro, por exemplo a partir dos experimentos Lunar-g Combustion Investigation (LUCI) e Flammability of Materials on the Moon (FM2).
- A gravidade parcial foi imitada no experimento Electric-Field Effects on Laminar Diffusion Flames (E-FIELD Flames) do ACME, por meio do efeito do campo elétrico sobre os íons que ocorrem naturalmente nas chamas.
- Os resultados em microgravidade e em gravidade normal poderiam delimitar o que ocorre em níveis intermediários de gravidade.

Para dados e recursos relacionados a este desafio, consulte a aba Resources no topo da página. Mais recursos podem ser adicionados antes do início do hackathon.

## Recursos

> A NASA não endossa nenhuma entidade que não seja do governo dos EUA e não se responsabiliza pelas informações contidas em sites que não sejam do governo dos EUA. Nos sites que não são do governo dos EUA, os participantes devem cumprir os parâmetros de uso de dados de cada site.

## Dados e recursos da NASA
- [PSI Data Repository: Combustion Science](https://psi.nasa.gov/physci/repo/search?q=combustion): Fonte do Physical Sciences Informatics (PSI) dos dados nos quais o aplicativo do NASA Space Apps deve se basear.
- [NASA Combustion Science](https://www.nasa.gov/glenn/glenn-expertise-space-exploration/physical-sciences-program/combustion-science/): Informações básicas sobre a maioria das investigações de combustão cujos dados estão no PSI Data Repository.
- [NASA ScienceCasts: The Power of Studying Combustion on the ISS](https://www.youtube.com/watch?v=W1oXykoz9zg): Introdução à pesquisa de combustão da NASA na Estação Espacial Internacional, em um vídeo de 3,6 minutos de 2018.
- [A Researcher’s Guide to International Space Station Combustion Science](https://www.nasa.gov/missions/station/a-researchers-guide-to-combustion-science/): Uma revisão de 2015 da pesquisa de combustão da NASA realizada, ou planejada, na Estação Espacial Internacional. Informações básicas sobre a maioria das investigações de combustão descritas neste documento de mais de 50 páginas estão no PSI Data Repository.
- [Apollo 1](https://sma.nasa.gov/sma-disciplines/accllp/apollo-1): Informações sobre a tripulação, a missão, o incêndio que irrompeu durante um teste antes do lançamento e matou a tripulação, a investigação e as lições aprendidas.
- [Apollo 13](https://sma.nasa.gov/sma-disciplines/accllp/apollo-13): Informações sobre a tripulação, a missão, a explosão do tanque de oxigênio ocorrida durante o voo para a Lua, a investigação e as lições aprendidas.
- [25 Years Ago: Fire Aboard Space Station Mir](https://www.nasa.gov/history/25-years-ago-fire-aboard-space-station-mir/): Informações básicas sobre um incêndio, causado pela falha de um gerador de oxigênio, que irrompeu na estação espacial russa Mir em 1997, durante operações conjuntas em preparação para a Estação Espacial Internacional (ocupada pela primeira vez em 2000).
- [Fireman’s Air Tanks](https://spinoff.nasa.gov/node/9582): Informações básicas sobre a adaptação, nos anos 1970, da tecnologia de trajes espaciais para melhorar os cilindros de ar e os equipamentos de respiração dos bombeiros.
- [Fire Detector](https://spinoff.nasa.gov/node/9407): Informações básicas sobre um detector de fumaça dos anos 1970 desenvolvido para o ônibus espacial que, ao distinguir fumaça de poeira, gera menos alarmes falsos. Por isso, tem aplicações industriais (por exemplo, em operações de mineração).
- [New Technology for the Fire Attire](https://spinoff.nasa.gov/node/9918): Informações básicas sobre uma aplicação, nos anos 1980, da tecnologia de trajes espaciais da NASA para melhorar a roupa dos bombeiros.
