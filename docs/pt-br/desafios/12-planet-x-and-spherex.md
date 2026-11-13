# 12. Planeta X e SPHEREx

**Título original:** Planet X and SPHEREx

**Dificuldade:** Avançado
**Áreas temáticas:** Astrophysics, Planets & Moons, Software
**Página oficial:** https://www.spaceappschallenge.org/2026/challenges/planet-x-and-spherex/

> Fonte: página oficial do desafio no NASA Space Apps Challenge 2026. Tradução informativa para consulta offline; em caso de dúvida, a página oficial em inglês prevalece.

Desde 2025, a missão SPHEREx da NASA mapeia o céu inteiro a cada seis meses em 102 bandas de luz do infravermelho próximo, devolvendo imagens de mais de um bilhão de objetos. Cometas, asteroides, estrelas, anãs marrons e até novos planetas se revelam ao mudar de posição entre as imagens, mas ninguém consegue peneirar todos esses dados sozinho. Seu desafio é criar uma ferramenta web pública para exibir imagens do céu da missão SPHEREx, facilitando que qualquer pessoa veja rapidamente como elas mudam ao longo do tempo.

## Contexto
Asteroides e cometas orbitam o Sol. Estrelas próximas marcham pelo céu ao orbitar a Galáxia. A Terra também orbita o Sol, fazendo com que objetos próximos de nós mudem de posição aparente. Observar esses movimentos nos ajuda a descobrir novos objetos astronômicos e também a medir as distâncias até eles. Por exemplo, o planeta anão Plutão foi descoberto quando um astrônomo comparou duas imagens do céu feitas em momentos diferentes e percebeu que um ponto de luz havia se deslocado entre elas.
Mais recentemente, astrônomos montaram buscas em larga escala por objetos próximos usando esse processo, com a ajuda do público. Centenas de milhares de voluntários usaram essa técnica para descobrir asteroides, cometas, estrelas e anãs marrons (bolas de gás massivas demais para serem consideradas planetas, mas sem massa suficiente para queimar como estrelas). Na verdade, a maioria dos cometas e anãs marrons conhecidos foi descoberta por voluntários dessa forma, por meio de projetos como o [backyardworlds.org](http://backyardworlds.org/).
Desde maio de 2025, a nova missão SPHEREx da NASA devolve dados únicos que podem render novas descobertas. O SPHEREx está mapeando o céu inteiro uma vez a cada seis meses em 102 bandas de luz do infravermelho próximo, o que o torna especialmente sensível a objetos ricos em hidrogênio, água, dióxido de carbono, monóxido de carbono e muitas outras moléculas. Haverá dados demais para que uma única pessoa, ou mesmo um código de computador, os compreenda por completo. Haverá imagens de mais de um bilhão de objetos (incluindo anãs marrons, quasares, cometas, asteroides, estrelas, supernovas e galáxias), que muitas vezes se sobrepõem ou variam de brilho. Precisamos de suas novas ferramentas criativas para aproveitar ao máximo esse tesouro e ajudar o maior número possível de pessoas a contribuir para as descobertas.

## Objetivos
Seu desafio é criar uma ferramenta web pública para exibir imagens do céu da missão SPHEREx, facilitando que qualquer pessoa veja rapidamente como elas mudam ao longo do tempo. Os usuários informarão as coordenadas de um trecho do céu (Right Ascension e declination). Sua ferramenta exibirá uma série de imagens desse trecho como um pequeno vídeo, facilitando a identificação de objetos em movimento.
Teste sua ferramenta na Estrela de Barnard, em Epsilon Indi B (um par de anãs marrons que orbitam uma estrela), em WISE 0855 (uma anã marrom de movimento rápido, Right Ascension 08h55m10.831s, declination -7d14m42.53s) e nas estrelas variáveis RW Aurigae e R Draconis.

## Pontos a considerar
Você pode (mas não é obrigado a) considerar o seguinte:
- Novos dados do SPHEREx estão chegando rápido! Projete uma ferramenta fácil de atualizar com as últimas liberações de dados.
- Pense com criatividade em como exibir essas 102 bandas de infravermelho para que os usuários possam aproveitá-las e fazer novas descobertas! Por exemplo, pode fazer sentido somar separadamente todos os dados captados por cada um dos seis arrays de detectores para melhorar a relação sinal-ruído das imagens exibidas. Pontos extras se sua ferramenta conseguir gerar espectros na hora.
- Pode ajudar os usuários a descobrir objetos em movimento se eles tiverem a opção de somar ou subtrair imagens feitas em momentos diferentes.
- Deixe os usuários escolherem o campo de visão! Campos de visão maiores permitem acompanhar fontes mais rápidas, ao custo de tempos de transferência de dados mais longos.
- Os usuários podem se beneficiar da opção de sobrepor dados astronômicos de outros telescópios, como a missão Gaia ou a missão WISE.
- Se sua ferramenta puder ser consultada com coordenadas na URL, os usuários poderão incorporá-la facilmente em outros sites e projetos.
- Pode ser útil exibir metadados, como flags de contaminação.
- Considere procurar ferramentas publicamente disponíveis que ajudem a tratar dados astronômicos, como as ferramentas do Astropy, e a exibi-los, como a ferramenta Aladin, desenvolvida pelo Strasbourg Astronomical Data Center (CDS).

Para dados e recursos relacionados a este desafio, consulte a aba Resources no topo da página. Mais recursos podem ser adicionados antes do início do hackathon.

## Recursos

> A NASA não endossa nenhuma entidade não pertencente ao governo dos EUA e não é responsável pelas informações contidas em sites não governamentais dos EUA. Para sites não governamentais dos EUA, os participantes devem cumprir os parâmetros de uso de dados desse site específico.

## Dados e recursos da NASA
- [NASA/IPAC Infrared Science Archive](https://irsa.ipac.caltech.edu/Missions/spherex.html): Recursos do SPHEREx.
- [SPHEREx Tutorial Notebooks](https://caltech-ipac.github.io/irsa-tutorials/spherex/): Exemplos de notebooks Jupyter sobre como acessar os dados do SPHEREx via Python.
- [WiseView](http://byw.tools/wiseview): Uma ferramenta semelhante, criada para visualizar dados de uma missão anterior da NASA chamada WISE. O público a usou para fazer centenas de descobertas. Fique à vontade para usá-la como modelo ou inspiração!
- [Gaia Mission Data](https://archive.stsci.edu/missions-and-data/gaia): Use sempre a liberação de dados mais recente (Data Release 3).

## Recursos das agências espaciais parceiras
CSA (Canadian Space Agency)
- [NEOSSat: Observing Asteroids, Space Debris and Exoplanets](https://www.asc-csa.gc.ca/eng/satellites/neossat/): Conheça o NEOSSat, o primeiro telescópio espacial do mundo dedicado a detectar e rastrear asteroides, cometas, satélites e detritos espaciais. Este recurso da CSA mostra como o Canadá ajuda a proteger nosso conhecimento do espaço próximo à Terra, contribuindo com esforços internacionais para identificar e monitorar objetos que possam representar riscos para a Terra ou para espaçonaves.
- [Canadian Astronomy Data Centre (CADC)](https://www.cadc-ccda.hia-iha.nrc-cnrc.gc.ca/en/): O CADC dá acesso a uma vasta coleção de observações astronômicas de telescópios e missões espaciais canadenses e internacionais. Por meio deste recurso, os participantes podem explorar dados científicos reais usados por astrônomos para estudar estrelas, galáxias, exoplanetas, asteroides e outros objetos celestes.
- [NEOSSat Data Tutorial](https://github.com/asc-csa/NEOSSAT_Tutorial): Este tutorial mostra como usar Python para visualizar dados da missão NEOSSat do Canadá. Siga as instruções passo a passo para acessar observações da espaçonave, criar visualizações e explorar os dados coletados pelo telescópio espacial canadense.
- [NEOSSat Dataset](https://data.asc-csa.gc.ca/dataset/neossat): Este conjunto de dados contém observações coletadas pelo NEOSSat, o Near-Earth Object Surveillance Satellite do Canadá. Os dados apoiam a detecção e o rastreamento de asteroides, cometas, satélites e detritos espaciais. Explore observações reais do telescópio espacial canadense e aprenda como os objetos são monitorados no espaço próximo à Terra.
