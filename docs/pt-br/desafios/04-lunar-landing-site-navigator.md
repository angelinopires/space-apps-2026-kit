# 04. Navegador de locais de pouso lunar

**Título original:** Lunar Landing Site Navigator

**Dificuldade:** Avançado / Intermediário
**Áreas temáticas:** Exploração humana, Lua, Software, Exploração espacial
**Página oficial:** https://www.spaceappschallenge.org/2026/challenges/lunar-landing-site-navigator/

> Fonte: página oficial do desafio no NASA Space Apps Challenge 2026. Tradução informativa para consulta offline; em caso de dúvida, a página oficial em inglês prevalece.

Missões ao polo sul da Lua enfrentam restrições extremas de iluminação e de comunicação, e planejá-las exige coordenação cuidadosa entre as equipes de ciência e de engenharia. Existem ferramentas para determinar as posições do Sol e da Terra em locais de pouso candidatos, mas suas interfaces complicadas dificultam avaliar com eficiência as informações críticas. Seu desafio é criar uma ferramenta ou aplicativo intuitivo que permita a planejadores de missão, educadores e ao público comparar rapidamente locais e datas de pouso, visualizando as posições do Sol e da Terra em relação ao horizonte para avaliar o potencial de geração de energia e as janelas de comunicação direta com a Terra.

## Contexto
O programa Commercial Lunar Payload Services (CLPS) da NASA e outras missões lunares dependem da escolha cuidadosa de locais e datas de pouso que equilibrem as necessidades das equipes de ciência e de engenharia. Um dos maiores desafios desse processo é entender o ambiente local de iluminação e de comunicação em um possível local de pouso. A posição do Sol determina a disponibilidade de energia para os painéis solares e as condições térmicas dos equipamentos, enquanto a posição da Terra determina se a comunicação direta é possível sem satélites de retransmissão.
Esse desafio é particularmente agudo no polo sul da Lua, onde muitas missões futuras estão planejadas devido à presença de gelo de água e de outros recursos de valor científico. A geometria do polo sul cria variações extremas na iluminação solar e na visibilidade da Terra ao longo de diferentes dias e estações lunares. Pequenas mudanças no local ou na data de pouso podem afetar drasticamente tanto o potencial de geração de energia quanto as janelas de comunicação, o que torna essencial avaliar rapidamente os locais.
Na prática, o desenvolvimento de uma missão raramente segue um cronograma fixo. Desafios no desenvolvimento do hardware, atrasos de lançamento ou outros fatores muitas vezes obrigam os planejadores a reconsiderar a data e o local de pouso originais. Quando isso acontece, os engenheiros precisam avaliar rapidamente locais alternativos na mesma região, ou datas alternativas no mesmo local, para entender como essas mudanças afetam a viabilidade da missão. Uma ferramenta que permita comparar de forma rápida e intuitiva vários cenários aceleraria esse processo de decisão e ajudaria as equipes a identificar alternativas viáveis quando as restrições mudam.
Ferramentas que fornecem essas informações, como o Quickmap da NASA, o Moon Trek e o JPL Horizons System, são feitas para análises detalhadas e muitas vezes são difíceis de usar bem por não especialistas na comparação rápida de cenários. Avaliar cada combinação de local e data significa navegar por várias interfaces e interpretar dados brutos. Isso deixa uma lacuna entre os dados técnicos disponíveis e as ferramentas acessíveis necessárias para apoiar um planejamento ágil de missões. Uma interface intuitiva que traduza dados complexos de efemérides e de topografia em visualizações claras e comparáveis poderia ajudar a preencher essa lacuna.

## Objetivos
Seu desafio é criar uma ferramenta ou aplicativo que permita avaliar rapidamente as opções de locais de pouso lunar. Sua solução pode incluir:
- Seleção e comparação interativa de locais: você pode considerar permitir que os usuários escolham em uma lista curada de locais de pouso notáveis (como missões Apollo passadas, alvos de futuras missões CLPS, alvos de outras missões lunares comerciais ou locais de pouso de programas lunares de outros países), além de inserir coordenadas lunares personalizadas. Você também pode considerar a comparação lado a lado ou em sequência de vários locais, para ajudar os usuários a avaliar rapidamente as trocas envolvidas.
- Flexibilidade de data e hora: você pode considerar permitir que os usuários selecionem datas e horários de pouso e oferecer ferramentas para explorar como as condições mudam ao longo de diferentes dias ou estações lunares. Isso permite entender como ajustes no cronograma da missão afetam a viabilidade.
- Visualização das posições do Sol e da Terra: exiba as posições do Sol e da Terra em relação ao horizonte em um local de pouso selecionado, em uma data escolhida. Você pode considerar mostrar quanto tempo falta para o pôr do Sol ou da Terra, pois isso afeta diretamente as operações da missão e as janelas de geração de energia.
- Avaliação de energia e comunicação: você pode considerar destacar métricas-chave como o ângulo de elevação solar (que afeta a eficiência da geração de energia), a duração da luz solar e as janelas de visibilidade da Terra. Essas métricas ajudam os planejadores de missão a avaliar rapidamente se uma combinação de local e data é viável.
- Várias abordagens de visualização: você pode explorar mapas 2D, visualizações 3D da superfície ou outras representações criativas que ajudem os usuários a entender as relações espaciais entre o local de pouso, o Sol e a Terra.
- Dinâmica temporal: você pode considerar criar animações ou linhas do tempo que mostrem como as posições do Sol e da Terra mudam ao longo de um dia lunar ou de vários dias, ajudando os usuários a entender a duração e o momento das janelas operacionais.
- Acessibilidade para diferentes níveis de conhecimento: sua ferramenta pode atender tanto a planejadores de missão que buscam informações técnicas detalhadas para decidir rápido quanto a educadores e ao público em geral, curiosos sobre por que a Lua apresenta desafios de engenharia tão peculiares.

Você é incentivado a ser criativo na forma de apresentar essas informações. Sua solução pode ser um aplicativo web, um aplicativo móvel, uma visualização interativa, um jogo educacional ou outro formato, desde que torne a avaliação rápida de locais clara e eficiente.

## Pontos a considerar
Você pode (mas não é obrigado a) considerar o seguinte:
Abordagem técnica:
- Dados de efemérides (as posições e os movimentos dos corpos celestes) podem ser calculados com ferramentas como o JPL Horizons System, ou você pode considerar o uso de conjuntos de dados pré-calculados.
- Dados de topografia lunar de fontes como o Lunar Orbiter Laser Altimeter (LOLA) podem ajudar a criar visualizações realistas da superfície e cálculos precisos do horizonte.
- Considere como tratar a ausência de atmosfera na Lua ao calcular as posições do horizonte. Sem refração atmosférica, o horizonte é determinado pelo terreno local e pela borda da esfera lunar vista do local de pouso.
- O ângulo de elevação solar é uma métrica-chave para a geração de energia, e você pode considerar calculá-lo e exibi-lo com destaque.

Experiência do usuário:
- Sua interface poderia priorizar a comparação rápida de cenários, permitindo que os planejadores de missão avaliem várias combinações de local e data com eficiência.
- Considere como comunicar com clareza o tempo restante antes do pôr do Sol ou da Terra, pois essa é uma informação operacional crítica.
- Pense em como tornar evidentes as diferenças extremas entre as condições lunares e terrestres: elas podem ser marcantes quando bem visualizadas.
- Você pode considerar recursos que ajudem os usuários a entender por que pequenas mudanças de local ou de data têm grande impacto na viabilidade da missão.

Dados e precisão:
- Considere levar em conta a topografia real da Lua, pois a elevação do terreno pode afetar de forma significativa as posições do horizonte e as janelas de visibilidade.
- Considere se sua ferramenta vai levar em conta fatores como a libração da Terra (oscilação) ou as variações orbitais da Lua.
- O terreno do polo sul é particularmente complexo, e você pode considerar como representar as encostas íngremes e as crateras profundas que criam condições extremas de sombra.

Engajamento e impacto:
- Sua solução poderia apoiar os planejadores de missão na coordenação entre as equipes de ciência e de engenharia durante o desenvolvimento da missão.
- Ela poderia ajudar as equipes a responder rapidamente quando mudanças de cronograma ou desafios no desenvolvimento do hardware exigirem ajustes na data ou no local de pouso.
- Ela também poderia servir como ferramenta educacional para ajudar estudantes e o público a entender os desafios da exploração lunar e por que o planejamento de missões é tão complexo.

Para dados e recursos relacionados a este desafio, consulte a aba Recursos no topo da página. Mais recursos podem ser adicionados antes do início do hackathon.

## Recursos

> A NASA não endossa nenhuma entidade que não seja do governo dos EUA e não é responsável pelas informações contidas em sites que não sejam do governo dos EUA. Em sites que não sejam do governo dos EUA, os participantes devem cumprir os parâmetros de uso de dados do site em questão.

## Dados e recursos da NASA
- [Quickmap](https://quickmap.lroc.asu.edu/): Uma ferramenta interativa de mapeamento desenvolvida pela Arizona State University que dá acesso a imagens lunares de alta resolução, dados topográficos e outros conjuntos de dados do Lunar Reconnaissance Orbiter da NASA. Você pode usar o Quickmap para explorar locais de pouso, visualizar o terreno e entender a superfície lunar em detalhe, o que é especialmente útil para compreender a topografia complexa das regiões do polo sul.
- [Moon Trek](https://trek.nasa.gov/moon/): A ferramenta interativa de visualização 3D da NASA para a exploração lunar. O Moon Trek permite explorar a superfície lunar, ver dados topográficos e entender o terreno em possíveis locais de pouso. Oferece uma interface intuitiva para a compreensão espacial de locais lunares e pode ajudar a visualizar como o terreno afeta as posições do horizonte.
- [Horizons System](https://ssd.jpl.nasa.gov/horizons/): Uma poderosa ferramenta de cálculo de efemérides desenvolvida pelo Jet Propulsion Laboratory da NASA, que calcula as posições e velocidades de corpos celestes, incluindo o Sol e a Terra vistos de qualquer ponto da Lua. Você pode usar o Horizons para obter as posições angulares precisas do Sol e da Terra em horários e locais específicos, que formam a base das suas visualizações e das avaliações de energia e comunicação.

## Recursos das agências espaciais parceiras
CSA (Canadian Space Agency)
- [Moon Exploration](https://www.asc-csa.gc.ca/eng/astronomy/moon-exploration/): Explore o portal Moon Exploration da CSA para conhecer missões passadas, atuais e futuras à Lua. Descubra as contribuições do Canadá para a exploração lunar, incluindo tecnologias, pesquisa científica e participação no programa Artemis.
