# Portais de dados da NASA (gerais)

Cada página de desafio lista os datasets que a NASA recomenda para ele (veja `desafios/`). Esta página cobre os portais que servem para quase qualquer desafio, mais as armadilhas que consomem a manhã de sábado.

## Comece por aqui

| Portal | O que é | Login? |
| --- | --- | --- |
| [NASA Earthdata Search](https://search.earthdata.nasa.gov/) | Busca e download de todos os datasets de ciências da Terra da NASA (imagens de satélite, clima, queimadas, solo, oceano, atmosfera) | Conta Earthdata gratuita para baixar |
| [Worldview](https://worldview.earthdata.nasa.gov/) | Navegue por mais de 1.000 camadas de satélite num mapa, por data. O jeito mais rápido de *ver* o dado antes de baixar. Exporta PNG/GeoTIFF/KMZ | Não |
| [GIBS](https://www.earthdata.nasa.gov/engage/open-data-services-software/earthdata-developer-portal/gibs-api) | API de tiles por trás do Worldview. Coloca imagem de satélite no Leaflet/OpenLayers/Cesium com um template de URL | Não |
| [data.nasa.gov](https://data.nasa.gov/) | Catálogo de dados abertos de toda a NASA (não só Terra) | Não |
| [api.nasa.gov](https://api.nasa.gov/) | APIs públicas: APOD, fotos dos rovers de Marte, asteroides NEO, imagens da Terra EPIC, clima espacial DONKI. Chave gratuita em 1 minuto | Chave de API (grátis, imediata) |
| [NASA Open Source Software](https://code.nasa.gov/) | Código da NASA que você pode reutilizar | Não |
| [NASA Image and Video Library](https://images.nasa.gov/) | Imagens, vídeos e áudios em domínio público, com API JSON | Não |

## Por tema

**Observação da Terra e clima**
- [Giovanni](https://giovanni.gsfc.nasa.gov/giovanni/): gera séries temporais e mapas de variáveis de ciências da Terra no navegador, sem download.
- [AppEEARS](https://appeears.earthdatacloud.nasa.gov/): extrai recortes de MODIS/VIIRS/SRTM para um ponto ou área, devolve CSV/GeoTIFF.
- [NASA POWER](https://power.larc.nasa.gov/): dados solares e meteorológicos para qualquer lat/lon, API REST simples, ideal para desafios de agricultura e energia.
- [FIRMS](https://firms.modaps.eosdis.nasa.gov/): detecções de fogo ativo (MODIS e VIIRS), mapa, API e CSV.
- [Earth Observatory](https://earthobservatory.nasa.gov/): artigos e imagens explicando fenômenos da Terra, bom para storytelling.
- [Earth Information Center](https://science.nasa.gov/earth/earth-information-center/): visualizações de um planeta em mudança.
- [Missão NISAR](https://nisar.jpl.nasa.gov/) e [ASF DAAC](https://asf.alaska.edu/): dados de radar de abertura sintética (SAR).

**Lua, Marte e planetas**
- [Moon Trek](https://trek.nasa.gov/moon/) e [Mars Trek](https://trek.nasa.gov/mars/): portais de mapa web com camadas, elevação e 3D da Lua e de Marte.
- [LROC Quickmap](https://quickmap.lroc.asu.edu/): imagens e topografia lunar em alta resolução.
- [PDS (Planetary Data System)](https://pds.nasa.gov/): arquivo de dados brutos das missões planetárias.
- [JPL Horizons](https://ssd.jpl.nasa.gov/horizons/): posições de Sol, Terra, planetas e sondas em qualquer instante e lugar (efemérides), com API.
- [NASA Eyes](https://eyes.nasa.gov/) e [Solar System Treks](https://trek.nasa.gov/): visualizações 3D para buscar ideias.

**Astrofísica**
- [IRSA](https://irsa.ipac.caltech.edu/): arquivos em infravermelho (SPHEREx, WISE, Spitzer).
- [MAST](https://archive.stsci.edu/): Hubble, JWST, TESS, Kepler, espelho do Gaia.
- [HEASARC](https://heasarc.gsfc.nasa.gov/): astrofísica de altas energias.

**Voo espacial humano e ciências da vida**
- [NASA Open Science Data Repository (OSDR)](https://osdr.nasa.gov/): dados de biologia e fisiologia em voo espacial (antigos GeneLab e LSDA).
- [NASA Technical Reports Server (NTRS)](https://ntrs.nasa.gov/): artigos e relatórios, busca em texto completo e API.
- [PSI (Physical Sciences Informatics)](https://www.nasa.gov/psi/): dados de experimentos de ciências físicas em microgravidade, incluindo combustão.

**Clima espacial e Sol**
- [DONKI](https://ccmc.gsfc.nasa.gov/tools/DONKI/): banco de eventos de clima espacial com API (também em api.nasa.gov).
- [SDO](https://sdo.gsfc.nasa.gov/data/): imagens do Sol.

## Dados das agências espaciais parceiras

Parceiras de 2026: Angola, Bahrein, Brasil (AEB), CSA (Canadá), ESA (Europa), ISRO (Índia), ASI (Itália), JAXA (Japão), KASA (Coreia), MBRSC (Emirados), CONAE (Argentina), NASRDA (Nigéria), Paraguai, Senegal, Espanha, Turquia e UK Space Agency. O guia oficial diz aos times que usar dados das parceiras é incentivado. Cada página de desafio lista os recursos de parceiras que se aplicam.

Times brasileiros: dados do [INPE](https://www.gov.br/inpe/) (CBERS, desmatamento PRODES/DETER, queimadas BDQueimadas) são altamente relevantes para os desafios de Terra e conversam com a participação da AEB como parceira.

## Armadilhas que custam horas

- **Login Earthdata.** Crie a conta sábado de manhã, não na hora em que precisar do arquivo. Download por script exige token ou `.netrc`.
- **Formatos.** HDF5, NetCDF e GeoTIFF exigem bibliotecas (`xarray`, `netCDF4`, `rasterio`, `h5py`). Prefira serviços que devolvem CSV, JSON ou PNG (POWER, AppEEARS, FIRMS, GIBS, Giovanni) quando o desafio permitir.
- **Tamanho.** Um único grânulo pode ter gigabytes. Use serviços de recorte (AppEEARS, filtros espaciais e temporais do Earthdata Search, OPeNDAP) em vez de download bruto.
- **Limites de taxa.** A chave demo do api.nasa.gov permite 30 requisições por hora; a chave pessoal gratuita permite 1.000 por hora.
- **Mock primeiro.** Construa a interface com uma amostra estática pequena (um CSV, um PNG), publique, depois ligue o dado real. Uma demo com dados de amostra realistas vale mais que um fetch ao vivo quebrado.
- **Cite tudo.** O formulário de submissão tem um campo obrigatório de referências. Mantenha um `SOURCES.md` no repositório desde a primeira hora e cole no fim.
