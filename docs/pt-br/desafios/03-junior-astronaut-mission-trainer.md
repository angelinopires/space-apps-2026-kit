# 03. Construa um simulador de missão para jovens astronautas

**Título original:** Build a Junior Astronaut Mission Trainer

**Dificuldade:** Intermediário / Iniciante/Jovens
**Áreas temáticas:** Jogos, Planetas e luas, Software, Exploração espacial, Sol
**Página oficial:** https://www.spaceappschallenge.org/2026/challenges/junior-astronaut-mission-trainer/

> Fonte: página oficial do desafio no NASA Space Apps Challenge 2026. Tradução informativa para consulta offline; em caso de dúvida, a página oficial em inglês prevalece.

Conteúdos de STEM sobre o espaço costumam simplificar demais as escolhas de engenharia que definem uma missão real, ou apresentá-las em um nível complexo demais para prender a atenção de um jovem aprendiz. Poucas ferramentas tornam essas escolhas ao mesmo tempo tangíveis e divertidas. Seu desafio é projetar e construir um jogo ou aplicativo interativo que permita aos estudantes administrar um posto avançado lunar ou marciano, equilibrando demandas concorrentes como suporte à vida, proteção contra radiação, energia e produção de alimentos, para que vivenciem na prática as decisões que determinam se uma missão fracassa ou tem sucesso.

## Contexto
À medida que a NASA trabalha para estabelecer uma presença sustentada na Lua e estender a exploração humana em direção a Marte, um dos desafios mais persistentes não é apenas a engenharia do hardware, mas construir no público a compreensão do que a sobrevivência realmente exige nesses ambientes. Astronautas em um posto avançado lunar ou marciano precisam equilibrar demandas concorrentes: a energia limitada tem de ser dividida entre suporte à vida, comunicações e ciência; a exposição à radiação precisa ser pesada contra os objetivos da missão; e toda decisão traz um custo de recursos que se acumula com o tempo. São os mesmos tipos de escolha que os planejadores de missão da própria NASA enfrentam todos os dias, com base em dados reais: atividade solar e risco de radiação do Space Weather Database (DONKI), dosimetria de radiação de astronautas e pesquisa biológica do Open Science Data Repository (OSDR) e dados ambientais de missões Artemis e de superfície de Marte.
A lacuna está na tradução. Conteúdos educacionais sobre o espaço para crianças costumam ficar abstratos demais (por exemplo, pôsteres e fatos gerais) para transmitir escolhas reais, ou pressupõem uma formação técnica avançada demais para um público jovem se envolver de forma significativa. Como resultado, muitos estudantes nunca encontram a lógica de decisão por trás de uma missão, apenas seus resultados. Conteúdos puramente educacionais têm dificuldade de manter a atenção; conteúdos puramente voltados ao entretenimento podem perder precisão.
Os participantes podem priorizar mecânicas, e não apenas visuais, que espelhem restrições reais: uma escolha que economiza energia hoje pode custar oxigênio amanhã. Recomenda-se basear a jogabilidade em dados abertos reais da NASA, em vez de estatísticas inventadas. Entre as abordagens possíveis estão o gerenciamento de recursos no estilo sobrevivência, árvores de decisão narrativas ou simuladores de controle de missão no estilo painel, mas os participantes são incentivados a explorar o formato que melhor ensine a escolha subjacente, em vez de seguir um único modelo.

## Objetivos
Seu desafio é projetar e construir um jogo ou aplicativo interativo que permita a crianças de 7 a 12 anos administrar um posto avançado lunar ou marciano, tomando decisões reais sobre suporte à vida, proteção contra radiação, orçamento de energia, produção de alimentos e atraso na comunicação, e vendo como essas escolhas se desenrolam ao longo de uma missão simulada.
Pense em como sua ferramenta pode transformar restrições reais de missão em jogabilidade: como é trocar reservas de oxigênio por uma oportunidade extra de pesquisa, ou reforçar a blindagem contra um evento de radiação ao custo da energia desta noite? Como você vai representar recursos concorrentes para que nenhuma escolha seja gratuita e toda decisão ensine algo verdadeiro sobre o que astronautas e planejadores de missão realmente enfrentam?
Você é incentivado a basear sua simulação em dados abertos reais da NASA sempre que possível, por exemplo, usando o DONKI para refletir a atividade solar e o risco de radiação reais, o OSDR para achados reais de saúde de astronautas e de pesquisa biológica, ou dados de missões Artemis e de superfície de Marte para definir as condições ambientais do local escolhido. Incorporar conjuntos de dados da NASA ao vivo ou arquivados, em vez de números fabricados, tornará a experiência mais autêntica e dará aos jogadores uma janela genuína para como se tomam decisões críticas de missão.
O formato é livre: você pode construir um jogo de sobrevivência com gerenciamento de recursos, um simulador de decisões guiado por narrativa, uma experiência no estilo painel de controle de missão ou algo totalmente diferente, para navegador, celular ou desktop. O objetivo é um protótipo funcional que demonstre a mecânica de escolha com clareza suficiente para que um jogador jovem saia entendendo uma restrição real da sobrevivência no espaço profundo, e não apenas tendo jogado um jogo divertido. Interpretações criativas de "posto avançado", "local" ou "missão" além da Lua e de Marte são bem-vindas, desde que o objetivo educacional subjacente (ensinar escolhas reais de engenharia por meio do jogo) continue central.

## Pontos a considerar
Você pode (mas não é obrigado a) considerar o seguinte:
Público e acessibilidade
- Seu público-alvo são crianças de 7 a 12 anos, mas considere se sua ferramenta pode se adaptar para envolver também irmãos mais velhos, pais ou ambientes de sala de aula.
- Prefira linguagem simples a jargão; quando um termo científico for inevitável (dose de radiação, microgravidade, sol marciano), explique-o brevemente no próprio contexto, sem pressupor conhecimento prévio.
- Uma barreira de entrada baixa importa: uma experiência jogável no navegador, sem download nem conta, alcançará mais participantes durante a avaliação e mais estudantes depois.

Uso de dados reais
- Sempre que possível, use as APIs públicas e os conjuntos de dados abertos da NASA em vez de inventar números que pareçam plausíveis. Mesmo uma pequena quantidade de dados reais (uma leitura real de radiação, uma foto real de Marte, um achado real sobre a saúde de astronautas) torna a experiência muito mais crível do que uma totalmente simulada.
- Atribua claramente as fontes de dados dentro da própria ferramenta, para que os jogadores entendam que estão lidando com ciência real da NASA, e não apenas com um jogo temático.
- Se chamadas de API ao vivo não forem viáveis no seu prazo de desenvolvimento, um conjunto de dados real e curado, embutido diretamente na ferramenta, é uma alternativa razoável e honesta, desde que você não apresente dados estáticos como se fossem ao vivo.

Armadilhas de jogabilidade e de design a evitar
- Evite criar uma escolha "segura" sem custo: o valor educacional vem de toda decisão envolver uma escolha real, espelhando o planejamento de missões de verdade.
- Não deixe o acabamento visual substituir a precisão mecânica: um jogo simples que ensina uma restrição real vale mais do que um jogo bonito que não ensina.
- Evite sobrecarregar jogadores jovens com sistemas demais para acompanhar ao mesmo tempo; dois ou três recursos centrais (suporte à vida, energia, blindagem) costumam funcionar melhor do que cinco ou seis.

O que faria uma solução se destacar
- Ferramentas que deixem os jogadores ver as consequências no mundo real de suas escolhas no jogo, ligando uma decisão de blindagem contra radiação ao clima espacial real do momento.
- Rejogabilidade: mecânicas ou eventos que variem entre as partidas incentivam as crianças a tentar estratégias diferentes e a aprender com o fracasso sem que ele pareça uma punição.
- Acompanhar o protótipo funcional de uma explicação curta sobre quais conjuntos de dados da NASA foram usados e por quê, tornando a ciência rastreável e verificável pelos avaliadores.

Para dados e recursos relacionados a este desafio, consulte a aba Recursos no topo da página. Mais recursos podem ser adicionados antes do início do hackathon.

## Recursos

> A NASA não endossa nenhuma entidade que não seja do governo dos EUA e não é responsável pelas informações contidas em sites que não sejam do governo dos EUA. Em sites que não sejam do governo dos EUA, os participantes devem cumprir os parâmetros de uso de dados do site em questão.

## Dados e recursos da NASA
- [NASA Open APIs](https://api.nasa.gov/): O portal central de APIs públicas da NASA, que oferece acesso programático gratuito a conjuntos de dados como a Astronomy Picture of the Day (APOD), as Mars Rover Photos e o Space Weather Database (DONKI). É possível solicitar na hora uma chave de API gratuita (com limites de uso maiores que os da chave de demonstração compartilhada), um bom ponto de partida para qualquer equipe do desafio que construa um protótipo conectado a dados.
- [Space Weather Database Of Notifications, Knowledge, Information (DONKI)](https://ccmc.gsfc.nasa.gov/tools/DONKI/): Dados reais e atualizados regularmente sobre erupções solares, ejeções de massa coronal e outros eventos de clima espacial que geram risco de radiação para astronautas e espaçonaves. Útil para basear qualquer mecânica de blindagem contra radiação, de interrupção de comunicações ou de risco de missão em condições reais e atuais, em vez de números inventados.
- [NASA Open Science Data Repository (OSDR)](https://osdr.nasa.gov/bio/repo/): ([search API](https://osdr.nasa.gov/osdr/data/search?term=KEYWORD)) O arquivo público da NASA de pesquisas de biologia espacial e saúde de astronautas, incluindo estudos sobre como o voo espacial afeta a densidade óssea, a massa muscular, a resposta imunológica, o sono e mais em muitos organismos. Pode ser pesquisado por palavra-chave, o que o torna adequado para ferramentas que queiram trazer ciência real e publicada da NASA relevante para as escolhas de saúde humana no espaço.
- [RadLab (OSDR Radiation Dosimetry Database)](https://visualization.osdr.nasa.gov/radlab/gui/data-api/): Medições reais de dose de radiação registradas por instrumentos de dosimetria a bordo da Estação Espacial Internacional, fornecidas por várias agências espaciais internacionais. Traz dados autênticos de exposição de astronautas à radiação (por exemplo, taxa de dose absorvida), úteis para qualquer ferramenta que modele blindagem, risco à saúde ou escolhas de missões de longa duração.
- [Mars Trek](https://trek.nasa.gov/mars/): Um portal interativo de visualização e download de dados com imagens reais da superfície de Marte, elevação e terreno, compilados das missões da NASA a Marte (incluindo Curiosity e Perseverance). Útil para equipes que queiram dados ambientais ou geográficos reais para basear um local de posto avançado em Marte ou uma visualização de terreno em condições reais de superfície.

## Recursos das agências espaciais parceiras
CSA (Canadian Space Agency)
- [Space resources for STEM and youth organizations](https://www.asc-csa.gc.ca/eng/youth-educators/resources-stem-and-youth-organizations.asp): A página Space Resources for STEM and Youth Organizations da CSA oferece ferramentas e atividades gratuitas e bilíngues para ajudar educadores a envolver jovens com o espaço e com STEM. Pensados para museus, bibliotecas, acampamentos, clubes extracurriculares, grupos comunitários e organizações de extensão, esses recursos apoiam o aprendizado além da sala de aula.
- [Food production on the moon and in remote areas](https://www.asc-csa.gc.ca/eng/youth-educators/toolkits/food-production/): Este pacote web é um recurso completo para educadores e jovens que querem aprender sobre alimentação no espaço. O kit busca mostrar como a produção de alimentos no espaço se relaciona com a saúde e a nutrição dos astronautas, além de beneficiar as pessoas na Terra.
