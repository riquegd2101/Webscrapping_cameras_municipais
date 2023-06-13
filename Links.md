```python
<a class="btn-pesquisa active" href="javascript:;" onclick="accordion($(this),'next');">Câmaras Municipais Mineiras</a>

from bs4 import BeautifulSoup
import requests

url = 'https://www.almg.gov.br/apoio_camaras/links/index.html'
response = requests.get(url)
soup = BeautifulSoup(response.text, 'html.parser')

# Encontre todos os elementos a com a classe btn-pesquisa
links = soup.find_all('a', class_='btn-pesquisa')

# Itere sobre a lista de links e acesse o atributo onclick
for link in links:
    onclick_value = link.get('onclick')
    print(onclick_value)
```


      Input In [20]
        <a class="btn-pesquisa active" href="javascript:;" onclick="accordion($(this),'next');">Câmaras Municipais Mineiras</a>
        ^
    SyntaxError: invalid syntax
    



```python
from bs4 import BeautifulSoup

html = """
<a href="http://www.camaradeaimores.mg.gov.br" target="_blank">Câmara Municipal de Aimorés</a><br />
<a href="http://www.camaraaiuruoca.mg.gov.br/" target="_blank">Câmara Municipal de Aiuruoca</a><br />
<a href="http://www.albertina.cam.mg.gov.br/home/index.php" target="_blank">Câmara Municipal de Albertina</a><br />
<a href="http://www.alemparaiba.cam.mg.gov.br/" target="_blank">Câmara Municipal de Além Paraíba</a><br />
<a href="http://www.cmalfenas.mg.gov.br" target="_blank">Câmara Municipal de Alfenas</a><br />
<a href="http://www.camaraalfredovasconcelos.mg.gov.br" target="_blank">Câmara Municipal de Alfredo Vasconcelos</a><br />
<a href="http://www.almenara.cam.mg.gov.br/" target="_blank">Câmara Municipal de Almenara</a><br />
<a href="http://www.cmalterosa.mg.gov.br" target="_blank">Câmara Municipal de Alterosa</a><br />
<a href="http://www.cmaltocaparao.mg.gov.br/" target="_blank">Câmara Municipal de Alto Caparaó</a><br />
<a href="http://www.cmaltojequitiba.mg.gov.br/" target="_blank">Câmara Municipal de Alto Jequitibá</a><br />
<a href="http://www.alvarengacamara.com.br/" target="_blank">Câmara Municipal de Alvarenga</a><br />
<a href="http://www.camaraandradas.mg.gov.br" target="_blank">Câmara Municipal de Andradas</a><br />
<a href="http://www.camaraandrelandia.mg.gov.br/" target="_blank">Câmara Municipal de Andrelândia</a><br />
<a href="http://www.cmac.mg.gov.br" target="_blank">Câmara Municipal de Antônio Carlos</a><br />
<a href="http://www.camaraaraguari.mg.gov.br/" target="_blank">Câmara Municipal de Araguari</a><br />
<a href="http://www.camaraarapora.mg.gov.br/" target="_blank">Câmara Municipal de Araporã</a><br />
<a href="http://187.32.64.185:8180/portal" target="_blank">Câmara Municipal de Araxá</a><br />
<a href="http://www.camaraarceburgo.mg.gov.br/" target="_blank">Câmara Municipal de Arceburgo</a><br />
<a href="http://www.camaraarcos.mg.gov.br/" target="_blank">Câmara Municipal de Arcos</a><br />
<a href="http://www.camaradeareado.mg.gov.br/novo/index.php" target="_blank">Câmara Municipal de Areado</a><br />
<a href="http://www.camaraarinos.mg.gov.br/" target="_blank">Câmara Municipal de Arinos</a><br />
<a href="http://camaraataleia.mg.gov.br/" target="_blank">Câmara Municipal de Ataleia</a><br />
<a href="http://www.camarabaependi.mg.gov.br" target="_blank">Câmara Municipal de Baependi</a><br />
<a href="http://www.camarabambui.mg.gov.br" target="_blank">Câmara Municipal de Bambuí</a><br />
<a href="http://www.cmbaraodecocais.mg.gov.br" target="_blank">Câmara Municipal de Barão de Cocais</a><br />
<a href="http://www.camarabarbacena.mg.gov.br" target="_blank">Câmara Municipal de Barbacena</a><br />
<a href="http://www.camarabarroso.mg.gov.br" target="_blank">Câmara Municipal de Barroso</a><br />
<a href="http://www.camarabelavista.mg.gov.br" target="_blank">Câmara Municipal de Bela Vista de Minas</a><br />
<a href="http://www.cmbh.mg.gov.br/" target="_blank">Câmara Municipal de Belo Horizonte</a><br />
<a href="http://www.belovale.cam.mg.gov.br/" target="_blank">Câmara Municipal de Belo Vale</a><br />
<a href="http://camaramunicipalbertopolis.com.br/" target="_blank">Câmara Municipal de Bertópolis</a><br />
<a href="http://www.camarabetim.mg.gov.br/" target="_blank">Câmara Municipal de Betim</a><br />
<a href="http://www.camarabicas.mg.gov.br/" target="_blank">Câmara Municipal de Bicas</a><br />
<a href="http://www.camaraboaesperanca.mg.gov.br" target="_blank">Câmara Municipal de Boa Esperança</a><br />
<a href="http://www.camarabocainademinas.mg.gov.br/" target="_blank">Câmara Municipal de Bocaina de Minas</a><br />
<a href="http://www.camarabocaiuva.cam.mg.gov.br/" target="_blank">Câmara Municipal de Bocaiúva</a><br />
<a href="http://www.camarabd.mg.gov.br/" target="_blank">Câmara Municipal de Bom Despacho</a><br />
<a href="http://www.cmbj.mg.gov.br/" target="_blank">Câmara Municipal de Bom Jardim de Minas</a><br />
<a href="http://www.camarabomjesusdapenha.mg.gov.br/" target="_blank">Câmara Municipal de Bom Jesus da Penha</a><br />
<a href="http://www.bomjesusdoamparo.mg.leg.br/" target="_blank">Câmara Municipal de Bom Jesus do Amparo</a><br />
<a href="http://www.camarabonfin.mg.gov.br/" target="_blank">Câmara Municipal de Bonfinópolis de Minas</a><br />
<a href="http://www.camaradebotelhos.mg.gov.br/novo/" target="_blank">Câmara Municipal de Botelhos</a><br />
<a href="http://www.brasilandiademinas.mg.leg.br/" target="_blank">Câmara Municipal de Brasilândia de Minas</a><br />
<a href="http://camarabrasiliademinas.com.br/" target="_blank">Câmara Municipal de Brasília de Minas</a><br />
<a href="http://www.camarabrazopolis.mg.gov.br/" target="_blank">Câmara Municipal de Brazópolis</a><br />
<a href="http://www.cmbrumadinho.mg.gov.br/" target="_blank">Câmara Municipal de Brumadinho</a><br />
<a href="http://www.cmburitis.mg.gov.br/" target="_blank">Câmara Municipal de Buritis</a><br />
<a href="http://camaradeburitizeiro.mg.gov.br/" target="_blank">Câmara Municipal de Buritizeiro</a><br />
<a href="http://www.cmcg.mg.gov.br/" target="_blank">Câmara Municipal de Cabeceira Grande</a><br />
<a href="http://www.camaracachoeirademinas.mg.gov.br/" target="_blank">Câmara Municipal de Cachoeira de Minas</a><br />
<a href="http://www.camaradecaete.mg.gov.br" target="_blank">Câmara Municipal de Caeté</a><br />
<a href="http://www.camaracaiana.mg.gov.br/" target="_blank">Câmara Municipal de Caiana</a><br />
<a href="http://www.camaracaldas.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Caldas</a><br />
<a href="http://www.camaracamacho.mg.gov.br" target="_blank">Câmara Municipal de Camacho</a><br />
<a href="http://www.camaracamanducaia.mg.gov.br" target="_blank">Câmara Municipal de Camanducaia</a><br />
<a href="http://www.camaracambui.mg.gov.br/" target="_blank">Câmara Municipal de Cambuí</a><br />
<a href="http://www.camaracambuquira.mg.gov.br/" target="_blank">Câmara Municipal de Cambuquira</a><br />
<a href="http://www.campanario.cam.mg.gov.br/" target="_blank">Câmara Municipal de Campanário</a><br />
<a href="http://www.camaracampanha.mg.gov.br" target="_blank">Câmara Municipal de Campanha</a><br />
<a href="http://www.campinaverde.mg.leg.br/portal" target="_blank">Câmara Municipal de Campina Verde</a><br />
<a href="http://www.camara.campobelo.mg.gov.br/" target="_blank">Câmara Municipal de Campo Belo</a><br />
<a href="http://www.camaracampodomeio.mg.gov.br/" target="_blank">Câmara Municipal de Campo do Meio</a><br />
<a href="http://camaracamposaltos.mg.gov.br" target="_blank">Câmara Municipal de Campos Altos</a><br />
<a href="http://www.camaracg.mg.gov.br" target="_blank">Câmara Municipal de Campos Gerais</a><br />
<a href="http://www.canapolis.mg.leg.br/site/" target="_blank">Câmara Municipal de Canápolis</a><br />
<a href="http://www.camaracapelinha.com.br/" target="_blank">Câmara Municipal de Capelinha</a><br />
<a href="http://www.camaracapetinga.net/" target="_blank">Câmara Municipal de Capetinga</a><br />
<a href="http://www.camaradecapitaoandrade.com.br/" target="_blank">Câmara Municipal de Capitão Andrade</a><br />
<a href="http://www.capimbranco.mg.leg.br/" target="_blank">Câmara Municipal de Capim Branco</a><br />
<a href="http://www.camaracapinopolis.mg.gov.br" target="_blank">Câmara Municipal de Capinópolis</a><br />
<a href="http://www.cmcaputira.mg.gov.br/" target="_blank">Câmara Municipal de Caputira</a><br />
<a href="http://www.camaracarandai.mg.gov.br/" target="_blank">Câmara Municipal de Carandaí</a><br />
<a href="http://www.camaracarangola.mg.gov.br" target="_blank">Câmara Municipal de Carangola</a><br />
<a href="http://www.cmcaratinga.mg.gov.br" target="_blank">Câmara Municipal de Caratinga</a><br />
<a href="http://www.cmcarbonita.mg.gov.br" target="_blank">Câmara Municipal de Carbonita</a><br />
<a href="http://www.cmcareacu.mg.gov.br/" target="_blank">Câmara Municipal de Careaçu</a><br />
<a href="http://carmesia.cam.mg.gov.br/" target="_blank">Câmara Municipal de Carmésia</a><br />
<a href="http://www.camaradecachoeira.com.br" target="_blank">Câmara Municipal de Carmo da Cachoeira</a><br />
<a href="http://camaracarmodamata.mg.gov.br/" target="_blank">Câmara Municipal de Carmo da Mata</a><br />
<a href="http://www.cmcm.mg.gov.br/" target="_blank">Câmara Municipal de Carmo de Minas</a><br />
<a href="http://www.camaracarmodocajuru.mg.gov.br/" target="_blank">Câmara Municipal de Carmo do Cajuru</a><br />
<a href="http://www.carmodoparanaiba.mg.leg.br/" target="_blank">Câmara Municipal de Carmo do Paranaíba</a><br />
<a href="http://www.carmodorioclaro.cam.mg.gov.br/" target="_blank">Câmara Municipal de Carmo do Rio Claro</a><br />
<a href="http://www.camaracarmopolis.mg.gov.br" target="_blank">Câmara Municipal de Carmópolis de Minas</a><br />
<a href="http://www.cmcarneirinho.mg.gov.br" target="_blank">Câmara Municipal de Carneirinho</a><br />
<a href="http://www.camaradecarrancas.mg.gov.br/" target="_blank">Câmara Municipal de Carrancas</a><br />
<a href="http://www.carvalhopolis.mg.leg.br/" target="_blank">Câmara Municipal de Carvalhópolis</a><br />
<a href="http://www.camaracasagrande.mg.gov.br" target="_blank">Câmara Municipal de Casa Grande</a><br />
<a href="http://www.cassia.cam.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Cássia</a><br />
<a href="http://www.cataguases.mg.leg.br/" target="_blank">Câmara Municipal de Cataguases</a><br />
<a href="http://www.camaracaxambu.mg.gov.br" target="_blank">Câmara Municipal de Caxambu</a><br />
<a href="http://www.cmchale.mg.gov.br/" target="_blank">Câmara Municipal de Chalé</a><br />
<a href="http://www.camaraclaraval.mg.gov.br/" target="_blank">Câmara Municipal de Claraval</a><br />
<a href="http://www.camaraclaudio.mg.gov.br/" target="_blank">Câmara Municipal de Cláudio</a><br />
<a href="http://camaraconceicao.mg.gov.br/" target="_blank">Câmara Municipal de Conceição das Alagoas</a><br />
<a href="http://www.cmci.mg.gov.br/" target="_blank">Câmara Municipal de Conceição de Ipanema</a><br />
<a href="http://www.conceicaodopara.cam.mg.gov.br" target="_blank">Câmara Municipal de Conceição do Pará</a><br />
<a href="http://www.conceicaodosouros.mg.leg.br/" target="_blank">Câmara Municipal de Conceição dos Ouros</a><br />
<a href="http://www.confins.mg.leg.br/" target="_blank">Câmara Municipal de Confins</a><br />
<a href="http://www.camaracongonhal.mg.gov.br/" target="_blank">Câmara Municipal de Congonhal</a><br />
<a href="http://www.camaracongonhas.mg.gov.br/" target="_blank">Câmara Municipal de Congonhas</a><br />
<a href="http://camaraconquista.mg.gov.br/" target="_blank">Câmara Municipal de Conquista</a><br />
<a href="http://www.camaraconselheirolafaiete.mg.gov.br" target="_blank">Câmara Municipal de Conselheiro Lafaiete</a><br />
<a href="http://www.cmcpena.mg.gov.br/" target="_blank">Câmara Municipal de Conselheiro Pena</a><br />
<a href="http://www.camaraconsolacao.mg.gov.br/" target="_blank">Câmara Municipal de Consolação</a><br />
<a href="http://www.cmc.mg.gov.br" target="_blank">Câmara Municipal de Contagem</a><br />
<a href="http://camaracordislandia.mg.gov.br/" target="_blank">Câmara Municipal de Cordislândia</a><br />
<a href="http://www.camaracoromandel.mg.gov.br" target="_blank">Câmara Municipal de Coromandel</a><br />
<a href="http://www.camarafabriciano.mg.gov.br/" target="_blank">Câmara Municipal de Coronel Fabriciano</a><br />
<a href="http://coronelpacheco.cam.mg.gov.br/" target="_blank">Câmara Municipal de Coronel Pacheco</a><br />
<a href="http://www.camaracxc.mg.gov.br/sitio/" target="_blank">Câmara Municipal de Coronel Xavier Chaves</a><br />
<a href="http://www.camaracorregodanta.mg.gov.br/" target="_blank">Câmara Municipal de Córrego Danta</a><br />
<a href="http://www.camaracbjesus.com.br/" target="_blank">Câmara Municipal de Córrego do Bom Jesus</a><br />
<a href="http://www.coutodemagalhaesdeminas.mg.leg.br/" target="_blank">Câmara Municipal de Couto de Magalhães de Minas</a><br />
<a href="http://www.cristianootoni.cam.mg.gov.br/" target="_blank">Câmara Municipal de Cristiano Otoni</a><br />
<a href="http://crisolita.mg.leg.br/" target="_blank">Câmara Municipal de Crisólita</a><br />
<a href="http://cristina.cam.mg.gov.br/" target="_blank">Câmara Municipal de Cristina</a><br />
<a href="http://www.camaracruzilia.mg.gov.br" target="_blank">Câmara Municipal de Cruzília</a><br />
<a href="http://www.cmcurvelo.mg.gov.br/" target="_blank">Câmara Municipal de Curvelo</a><br />
<a href="http://www.delfinopolis.cam.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Delfinópolis</a><br />
<a href="http://www.delta.mg.leg.br/" target="_blank">Câmara Municipal de Delta</a><br />
<a href="http://www.descoberto.mg.leg.br/" target="_blank">Câmara Municipal de Descoberto</a><br />
<a href="http://www.camaradiamantina.cam.mg.gov.br/" target="_blank">Câmara Municipal de Diamantina</a><br />
<a href="http://www.dionisio.cam.mg.gov.br/" target="_blank">Câmara Municipal de Dionísio</a><br />
<a href="http://www.camaradivinolandia.mg.gov.br/" target="_blank">Câmara Municipal de Divinolândia de Minas</a><br />
<a href="http://www.camaradiv.mg.gov.br" target="_blank">Câmara Municipal de Divinópolis</a><br />
<a href="http://www.dombosco.mg.leg.br/" target="_blank">Câmara Municipal de Dom Bosco</a><br />
<a href="http://www.camaradomsilverio.mg.gov.br/" target="_blank">Câmara Municipal de Dom Silvério</a><br />
<a href="http://www.donaeuzebia.mg.leg.br/" target="_blank">Câmara Municipal de Dona Euzébia</a><br />
<a href="http://www.camaradoresdecampos.com.br/" target="_blank">Câmara Municipal de Dores de Campos</a><br />
<a href="http://www.cmdoresdoindaia.mg.gov.br/" target="_blank">Câmara Municipal de Dores do Indaiá</a><br />
<a href="http://entreriosdeminas.cam.mg.gov.br/" target="_blank">Câmara Municipal de Entre Rios de Minas</a><br />
<a href="http://www.camaraervalia.mg.gov.br/" target="_blank">Câmara Municipal de Ervália</a><br />
<a href="http://www.camaraesmeraldas.mg.gov.br/" target="_blank">Câmara Municipal de Esmeraldas</a><br />
<a href="http://www.camaraefeliz.mg.gov.br" target="_blank">Câmara Municipal de Espera Feliz</a><br />
<a href="http://www.camaraestiva.mg.gov.br/" target="_blank">Câmara Municipal de Estiva</a><br />
<a href="http://www.estreladoindaia.cam.mg.gov.br/" target="_blank">Câmara Municipal de Estrela do Indaiá</a><br />
<a href="http://www.camaraestreladosul.mg.gov.br/" target="_blank">Câmara Municipal de Estrela do Sul</a><br />
<a href="http://www.camaraextrema.mg.gov.br/" target="_blank">Câmara Municipal de Extrema</a><br />
<a href="http://www.cmfama.mg.gov.br" target="_blank">Câmara Municipal de Fama</a><br />
<a href="http://camaradefarialemos.com.br/" target="_blank">Câmara Municipal de Faria Lemos</a><br />
<a href="http://www.ferros.cam.mg.gov.br/" target="_blank">Câmara Municipal de Ferros</a><br />
<a href="http://www.fervedouro.mg.leg.br/" target="_blank">Câmara Municipal de Fervedouro</a><br />
<a href="http://www.florestal.mg.leg.br/" target="_blank">Câmara Municipal de Florestal</a><br />
<a href="http://www.camaraformiga.mg.gov.br/" target="_blank">Câmara Municipal de Formiga</a><br />
<a href="http://www.formoso.mg.leg.br/" target="_blank">Câmara Municipal de Formoso</a><br />
<a href="http://www.camarafortalezademinas.mg.gov.br/" target="_blank">Câmara Municipal de Fortaleza de Minas</a><br />
<a href="http://www.cmfortunademinas.mg.gov.br/" target="_blank">Câmara Municipal de Fortuna de Minas</a><br />
<a href="http://www.camarafronteira.mg.gov.br" target="_blank">Câmara Municipal de Fronteira</a><br />
<a href="http://www.camarafrutal.mg.gov.br/" target="_blank">Câmara Municipal de Frutal</a><br />
<a href="http://www.galileia.cam.mg.gov.br/" target="_blank">Câmara Municipal de Galileia</a><br />
<a href="http://www.camaragoncalves.mg.gov.br/" target="_blank">Câmara Municipal de Gonçalves</a><br />
<a href="http://www.camaragv.mg.gov.br/" target="_blank">Câmara Municipal de Governador Valadares</a><br />
<a href="http://www.cmgm.mg.gov.br/" target="_blank">Câmara Municipal de Grão Mogol</a><br />
<a href="http://www.camaradeguanhaes.mg.gov.br" target="_blank">Câmara Municipal de Guanhães</a><br />
<a href="http://www.camaraguaranesia.mg.gov.br/" target="_blank">Câmara Municipal de Guaranésia</a><br />
<a href="http://www.cmguarani.mg.gov.br/" target="_blank">Câmara Municipal de Guarani</a><br />
<a href="http://www.camaraguardamor.mg.gov.br/" target="_blank">Câmara Municipal de Guarda-Mor</a><br />
<a href="http://camaraguaxupe.mg.gov.br/" target="_blank">Câmara Municipal de Guaxupé</a><br />
<a href="http://www.guimarania.mg.leg.br/" target="_blank">Câmara Municipal de Guimarânia</a><br />
<a href="http://www.cmheliodora.mg.gov.br/" target="_blank">Câmara Municipal de Heliodora</a><br />
<a href="http://www.ibia.mg.leg.br/" target="_blank">Câmara Municipal de Ibiá</a><br />
<a href="http://www.camaraibiraci.mg.gov.br/" target="_blank">Câmara Municipal de Ibiraci</a><br />
<a href="http://www.camaraibirite.mg.gov.br/" target="_blank">Câmara Municipal de Ibirité</a><br />
<a href="http://www.cmigarape.mg.gov.br/" target="_blank">Câmara Municipal de Igarapé</a><br />
<a href="http://www.camaraigaratinga.mg.gov.br/" target="_blank">Câmara Municipal de Igaratinga</a><br />
<a href="http://www.cyberbalada.com/iguatama/" target="_blank">Câmara Municipal de Iguatama</a><br />
<a href="http://www.camarainconfidentes.mg.gov.br" target="_blank">Câmara Municipal de Inconfidentes</a><br />
<a href="http://www.indaiabira.mg.leg.br/" target="_blank">Câmara Municipal de Indaiabira</a><br />
<a href="http://camaraindianopolis.mg.gov.br/" target="_blank">Câmara Municipal de Indianópolis</a><br />
<a href="http://www.cminimutaba.com.br/" target="_blank">Câmara Municipal de Inimutaba</a><br />
<a href="http://www.camaraipanema.mg.gov.br" target="_blank">Câmara Municipal de Ipanema</a><br />
<a href="http://www.camaraipatinga.mg.gov.br" target="_blank">Câmara Municipal de Ipatinga</a><br />
<a href="http://www.camaraipiacu.mg.gov.br/" target="_blank">Câmara Municipal de Ipiaçu</a><br />
<a href="http://www.iraideminas.cam.mg.gov.br/" target="_blank">Câmara Municipal de Iraí de Minas</a><br />
<a href="http://www.itabira.cam.mg.gov.br" target="_blank">Câmara Municipal de Itabira</a><br />
<a href="http://www.itabirito.cam.mg.gov.br/" target="_blank">Câmara Municipal de Itabirito</a><br />
<a href="http://camaraitaguara.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Itaguara</a><br />
<a href="http://www.itajuba.cam.mg.gov.br" target="_blank">Câmara Municipal de Itajubá</a><br />
<a href="http://www.itamogi.mg.leg.br/" target="_blank">Câmara Municipal de Itamogi</a><br />
<a href="http://www.camaramunicipaldeitamonte.net/" target="_blank">Câmara Municipal de Itamonte</a><br />
<a href="http://www.itanhandu.cam.mg.gov.br/" target="_blank">Câmara Municipal de Itanhandu</a><br />
<a href="http://www.cmitanhomi.com.br" target="_blank">Câmara Municipal de Itanhomi</a><br />
<a href="http://www.sitesrm.com.br/cmitaobim.mg.gov.br" target="_blank">Câmara Municipal de Itaobim</a><br />
<a href="http://www.cmitapagipe.mg.gov.br" target="_blank">Câmara Municipal de Itapagipe</a><br />
<a href="http://www.itapecerica.cam.mg.gov.br" target="_blank">Câmara Municipal de Itapecerica</a><br />
<a href="http://www.camaraitapeva.mg.gov.br" target="_blank">Câmara Municipal de Itapeva</a><br />
<a href="http://www.camaraitaudeminas.mg.gov.br/" target="_blank">Câmara Municipal de Itaú de Minas</a><br />
<a href="http://www.cmitauna.mg.gov.br" target="_blank">Câmara Municipal de Itaúna</a><br />
<a href="http://www.ituiutaba.mg.leg.br/" target="_blank">Câmara Municipal de Ituiutaba</a><br />
<a href="http://www.camaraiturama.com.br/" target="_blank">Câmara Municipal de Iturama</a><br />
<a href="http://www.cmjaboticatubas.mg.gov.br/" target="_blank">Câmara Municipal de Jaboticatubas</a><br />
<a href="http://camarajacinto.mg.gov.br/" target="_blank">Câmara Municipal de Jacinto</a><br />
<a href="http://www.jacui.mg.leg.br/" target="_blank">Câmara Municipal de Jacuí</a><br />
<a href="http://www.camarajacutinga.mg.gov.br/" target="_blank">Câmara Municipal de Jacutinga</a><br />
<a href="http://www.camarajaguaracu.com/" target="_blank">Câmara Municipal de Jaguaraçu</a><br />
<a href="http://www.jaiba.mg.leg.br/" target="_blank">Câmara Municipal de Jaíba</a><br />
<a href="http://www.jampruca.cam.mg.gov.br/" target="_blank">Câmara Municipal de Jampruca</a><br />
<a href="http://www.janauba.mg.leg.br/" target="_blank">Câmara Municipal de Janaúba</a><br />
<a href="http://www.camarajanuaria.mg.gov.br/" target="_blank">Câmara Municipal de Januária</a><br />
<a href="http://www.jequitinhonha.mg.leg.br/" target="_blank">Câmara Municipal de Jequitinhonha</a><br />
<a href="http://www.camarajesuania.mg.gov.br/" target="_blank">Câmara Municipal de Jesuânia</a><br />
<a href="http://www.joaima.mg.leg.br/" target="_blank">Câmara Municipal de Joaíma</a><br />
<a href="http://www.joaquimfelicio.mg.leg.br/" target="_blank">Câmara Municipal de Joaquim Felício</a><br />
<a href="http://www.camarajm.mg.gov.br" target="_blank">Câmara Municipal de João Monlevade</a><br />
<a href="http://www.joaopinheiro.mg.leg.br/" target="_blank">Câmara Municipal de João Pinheiro</a><br />
<a href="http://www.jordania.mg.leg.br/portal/" target="_blank">Câmara Municipal de Jordânia</a><br />
<a href="http://www.cmjuatuba.mg.gov.br/" target="_blank">Câmara Municipal de Juatuba</a><br />
<a href="http://isal.camarajf.mg.gov.br" target="_blank">Câmara Municipal de Juiz de Fora</a><br />
<a href="http://www.juruaia.cam.mg.gov.br/" target="_blank">Câmara Municipal de Juruaia</a><br />
<a href="http://www.juvenilia.net.br/" target="_blank">Câmara Municipal de Juvenília</a><br />
<a href="http://www.lagamar.mg.leg.br/" target="_blank">Câmara Municipal de Lagamar</a><br />
<a href="http://www.camaralp.mg.gov.br" target="_blank">Câmara Municipal de Lagoa da Prata</a><br />
<a href="http://www.camaralagoa.mg.gov.br" target="_blank">Câmara Municipal de Lagoa Formosa</a><br />
<a href="http://www.cmlagoasanta.mg.gov.br" target="_blank">Câmara Municipal de Lagoa Santa</a><br />
<a href="http://www.cmlajinha.mg.gov.br" target="_blank">Câmara Municipal de Lajinha</a><br />
<a href="http://www.camaralambari.mg.gov.br/" target="_blank">Câmara Municipal de Lambari</a><br />
<a href="http://www.camaradelassance.mg.gov.br/" target="_blank">Câmara Municipal de Lassance</a><br />
<a href="http://www.camaralavras.mg.gov.br/" target="_blank">Câmara Municipal de Lavras</a><br />
<a href="http://www.camaradeleopoldina.mg.gov.br" target="_blank">Câmara Municipal de Leopoldina</a><br />
<a href="http://camaraliberdade.mg.gov.br/site/" target="_blank">Câmara Municipal de Liberdade</a><br />
<a href="http://www.camarald.mg.gov.br" target="_blank">Câmara Municipal de Lima Duarte</a><br />
<a href="http://www.limeiradooeste.mg.leg.br/" target="_blank">Câmara Municipal de Limeira do Oeste</a><br />
<a href="http://www.luislandia.mg.leg.br/" target="_blank">Câmara Municipal de Luislândia</a><br />
<a href="http://www.luminarias.cam.mg.gov.br/" target="_blank">Câmara Municipal de Luminárias</a><br />
<a href="http://www.camaramunicipaldeluz.mg.gov.br" target="_blank">Câmara Municipal de Luz</a><br />
<a href="http://www.camaramachacalis.mg.gov.br/" target="_blank">Câmara Municipal de Machacalis</a><br />
<a href="http://www.camaramachado.mg.gov.br/" target="_blank">Câmara Municipal de Machado</a><br />
<a href="http://www.mamonas.mg.leg.br/" target="_blank">Câmara Municipal de Mamonas</a><br />
<a href="http://www.camaramanhuacu.com.br/" target="_blank">Câmara Municipal de Manhuaçu</a><br />
<a href="http://www.manhumirim.mg.leg.br/" target="_blank">Câmara Municipal de Manhumirim</a><br />
<a href="http://www.mantena.mg.leg.br/" target="_blank">Câmara Municipal de Mantena</a><br />
<a href="http://www.camarademariadafe.com/" target="_blank">Câmara Municipal de Maria da Fé</a><br />
<a href="http://camarademariana.mg.gov.br" target="_blank">Câmara Municipal de Mariana</a><br />
<a href="http://www.cmmc.mg.gov.br/" target="_blank">Câmara Municipal de Mário Campos</a><br />
<a href="http://www.cmmarmelopolis.mg.gov.br/" target="_blank">Câmara Municipal de Marmelópolis</a><br />
<a href="http://www.camaramcampos.mg.gov.br/" target="_blank">Câmara Municipal de Martinho Campos</a><br />
<a href="http://www.camaramateusleme.mg.gov.br/" target="_blank">Câmara Municipal de Mateus Leme</a><br />
<a href="http://cmmb.mg.gov.br" target="_blank">Câmara Municipal de Matias Barbosa</a><br />
<a href="http://www.camaramatozinhos.mg.gov.br" target="_blank">Câmara Municipal de Matozinhos</a><br />
<a href="http://minasnovas.mg.leg.br/" target="_blank">Câmara Municipal de Minas Novas</a><br />
<a href="http://www.camaramiradouro.mg.gov.br" target="_blank">Câmara Municipal de Miradouro</a><br />
<a href="http://mirai.cam.mg.gov.br/" target="_blank">Câmara Municipal de Miraí</a><br />
<a href="http://www.camarademoeda.com.br" target="_blank">Câmara Municipal de Moeda</a><br />
<a href="http://camaramoema.mg.gov.br/" target="_blank">Câmara Municipal de Moema</a><br />
<a href="http://www.cmmonjolos.mg.gov.br/" target="_blank">Câmara Municipal de Monjolos</a><br />
<a href="http://www.monsenhorpaulo.cam.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Monsenhor Paulo</a><br />
<a href="http://camaramontalvania.mg.gov.br/" target="_blank">Câmara Municipal de Montalvânia</a><br />
<a href="http://www.montealegredeminas.cam.mg.gov.br" target="_blank">Câmara Municipal de Monte Alegre de Minas</a><br />
<a href="http://www.camaramunicipaldemonteazul.mg.gov.br/" target="_blank">Câmara Municipal de Monte Azul</a><br />
<a href="http://www.camaramontebelo.mg.gov.br" target="_blank">Câmara Municipal de Monte Belo</a><br />
<a href="http://www.camaramontecarmelo.mg.gov.br" target="_blank">Câmara Municipal de Monte Carmelo</a><br />
<a href="http://www.montesantodeminas.mg.leg.br/" target="_blank">Câmara Municipal de Monte Santo de Minas</a><br />
<a href="http://www.camaramontesiao.com.br" target="_blank">Câmara Municipal de Monte Sião</a><br />
<a href="http://www.cmmoc.mg.gov.br/" target="_blank">Câmara Municipal de Montes Claros</a><br />
<a href="http://www.camaraemacao.mg.gov.br" target="_blank">Câmara Municipal de Morada Nova de Minas</a><br />
<a href="http://www.morrodagarca.cam.mg.gov.br/" target="_blank">Câmara Municipal de Morro da Garça</a><br />
<a href="http://www.camaramuriae.mg.gov.br" target="_blank">Câmara Municipal de Muriaé</a><br />
<a href="http://www.camaramutum.mg.gov.br/" target="_blank">Câmara Municipal de Mutum</a><br />
<a href="http://www.camaramuzambinho.mg.gov.br/" target="_blank">Câmara Municipal de Muzambinho</a><br />
<a href="http://www.camarananuque.com.br" target="_blank">Câmara Municipal de Nanuque</a><br />
<a href="http://www.camaranatalandia.mg.gov.br/" target="_blank">Câmara Municipal de Natalândia</a><br />
<a href="http://www.cmnatercia.mg.gov.br" target="_blank">Câmara Municipal de Natércia</a><br />
<a href="http://www.camaranepomuceno.com.br/" target="_blank">Câmara Municipal de Nepomuceno</a><br />
<a href="http://www.cmne.mg.gov.br" target="_blank">Câmara Municipal de Nova Era</a><br />
<a href="http://www.cmnovalima.mg.gov.br/" target="_blank">Câmara Municipal de Nova Lima</a><br />
<a href="http://www.novaserrana.cam.mg.gov.br" target="_blank">Câmara Municipal de Nova Serrana</a><br />
<a href="http://camara.olimpionoronha.mg.gov.br/" target="_blank">Câmara Municipal de Olímpio Noronha</a><br />
<a href="http://www.oliveira.cam.mg.gov.br/" target="_blank">Câmara Municipal de Oliveira</a><br />
<a href="http://camaraoratorios.mg.gov.br/" target="_blank">Câmara Municipal de Oratórios</a><br />
<a href="http://www.ourobranco.cam.mg.gov.br" target="_blank">Câmara Municipal de Ouro Branco</a><br />
<a href="http://www.camaraourofino.mg.gov.br/" target="_blank">Câmara Municipal de Ouro Fino</a><br />
<a href="http://www.cmop.mg.gov.br" target="_blank">Câmara Municipal de Ouro Preto</a><br />
<a href="http://paineiras.cam.mg.gov.br/" target="_blank">Câmara Municipal de Paineiras</a><br />
<a href="http://www.camarapains.mg.gov.br" target="_blank">Câmara Municipal de Pains</a><br />
<a href="http://www.camarapm.mg.gov.br/" target="_blank">Câmara Municipal de Pará de Minas</a><br />
<a href="http://www.camaraptu.mg.gov.br/" target="_blank">Câmara Municipal de Paracatu</a><br />
<a href="http://www.camaradeparaguacu.mg.gov.br" target="_blank">Câmara Municipal de Paraguaçu</a><br />
<a href="http://www.paraopeba.cam.mg.gov.br/" target="_blank">Câmara Municipal de Paraopeba</a><br />
<a href="http://www.cmpassaquatro.mg.gov.br/" target="_blank">Câmara Municipal de Passa Quatro</a><br />
<a href="http://www.camarapassatempo.mg.gov.br/" target="_blank">Câmara Municipal de Passa Tempo</a><br />
<a href="http://www.camarapassos.mg.gov.br" target="_blank">Câmara Municipal de Passos</a><br />
<a href="http://www.camarapatos.mg.gov.br" target="_blank">Câmara Municipal de Patos de Minas</a><br />
<a href="http://cmpatrocinio.mg.gov.br" target="_blank">Câmara Municipal de Patrocínio</a><br />
<a href="http://www.pecanha.mg.leg.br/principal.asp" target="_blank">Câmara Municipal de Peçanha</a><br />
<a href="http://pedraazul.mg.leg.br/" target="_blank">Câmara Municipal de Pedra Azul</a><br />
<a href="http://camarapb.blogspot.com.br/" target="_blank">Câmara Municipal de Pedra Bonita</a><br />
<a href="http://www.camarapedraindaia.com.br/" target="_blank">Câmara Municipal de Pedra do Indaiá</a><br />
<a href="http://camarapd.mg.gov.br/" target="_blank">Câmara Municipal de Pedra Dourada</a><br />
<a href="http://www.pedralva.cam.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Pedralva</a><br />
<a href="http://www.pedrinopolis.mg.leg.br/" target="_blank">Câmara Municipal de Pedrinópolis</a><br />
<a href="http://www.camarapl.mg.gov.br" target="_blank">Câmara Municipal de Pedro Leopoldo</a><br />
<a href="http://www.pedroteixeira.cam.mg.gov.br/" target="_blank">Câmara Municipal de Pedro Teixeira</a><br />
<a href="http://www.camarapequi.mg.gov.br/" target="_blank">Câmara Municipal de Pequi</a><br />
<a href="http://www.camaraperdizes.com.br/" target="_blank">Câmara Municipal de Perdizes</a><br />
<a href="http://www.pescador.cam.mg.gov.br/" target="_blank">Câmara Municipal de Pescador</a><br />
<a href="http://piau.cam.mg.gov.br/" target="_blank">Câmara Municipal de Piau</a><br />
<a href="http://www.camarapiracema.mg.gov.br/" target="_blank">Câmara Municipal de Piracema</a><br />
<a href="http://www.cmpirangucu.com.br/" target="_blank">Câmara Municipal de Piranguçu</a><br />
<a href="http://www.camaradepiranguinho.com.br/" target="_blank">Câmara Municipal de Piranguinho</a><br />
<a href="http://www.pirapetinga.mg.leg.br/" target="_blank">Câmara Municipal de Pirapetinga</a><br />
<a href="http://www.camaradepirapora.mg.gov.br" target="_blank">Câmara Municipal de Pirapora</a><br />
<a href="http://www.cmpirauba.mg.gov.br/" target="_blank">Câmara Municipal de Piraúba</a><br />
<a href="http://www.camarapiumhi.mg.gov.br" target="_blank">Câmara Municipal de Piumhi</a><br />
<a href="http://www.cmplanura.mg.gov.br" target="_blank">Câmara Municipal de Planura</a><br />
<a href="http://www.camarapocos.mg.gov.br" target="_blank">Câmara Municipal de Poços de Caldas</a><br />
<a href="http://camaramunicipaldepompeu.mg.gov.br/" target="_blank">Câmara Municipal de Pompéu</a><br />
<a href="http://www.pontenova.mg.leg.br/" target="_blank">Câmara Municipal de Ponte Nova</a><br />
<a href="http://www.camarapv.com.br/" target="_blank">Câmara Municipal de Ponto dos Volantes</a><br />
<a href="http://www.cmpa.mg.gov.br" target="_blank">Câmara Municipal de Pouso Alegre</a><br />
<a href="http://www.pousoalto.mg.leg.br/" target="_blank">Câmara Municipal de Pouso Alto</a><br />
<a href="http://www.prados.cam.mg.gov.br/site/" target="_blank">Câmara Municipal de Prados</a><br />
<a href="http://www.camaraprata.mg.gov.br/" target="_blank">Câmara Municipal de Prata</a><br />
<a href="http://www.cmpo.mg.gov.br" target="_blank">Câmara Municipal de Presidente Olegário</a><br />
<a href="http://www.cmraposos.com.br" target="_blank">Câmara Municipal de Raposos</a><br />
<a href="http://www.cmraulsoares.mg.gov.br" target="_blank">Câmara Municipal de Raul Soares</a><br />
<a href="http://www.reduto.mg.leg.br/" target="_blank">Câmara Municipal de Reduto</a><br />
<a href="http://www.camaraderesendecosta.mg.gov.br/" target="_blank">Câmara Municipal de Resende Costa</a><br />
<a href="http://www.camaraderessaquinha.mg.gov.br/" target="_blank">Câmara Municipal de Ressaquinha</a><br />
<a href="http://www.cmrn.mg.gov.br" target="_blank">Câmara Municipal de Ribeirão das Neves</a><br />
<a href="http://www.rioacima.mg.leg.br/" target="_blank">Câmara Municipal de Rio Acima</a><br />
<a href="http://www.camarariocasca.mg.gov.br/" target="_blank">Câmara Municipal de Rio Casca</a><br />
<a href="http://www.camararionovo.mg.gov.br" target="_blank">Câmara Municipal de Rio Novo</a><br />
<a href="http://www.camararioparanaiba.mg.gov.br/" target="_blank">Câmara Municipal de Rio Paranaíba</a><br />
<a href="http://camararp.mg.gov.br" target="_blank">Câmara Municipal de Rio Piracicaba</a><br />
<a href="http://www.cmriopomba.mg.gov.br" target="_blank">Câmara Municipal de Rio Pomba<br />
</a><a href="http://www.cmrp.mg.gov.br" target="_blank">Câmara Municipal de Rio Preto</a><br />
<a href="http://www.ritapolis.mg.leg.br/" target="_blank">Câmara Municipal de Ritápolis</a><br />
<a href="http://rodeiro.mg.leg.br/" target="_blank">Câmara Municipal de Rodeiro</a><br />
<a href="http://camararubim.mg.gov.br/" target="_blank">Câmara Municipal de Rubim</a><br />
<a href="http://www.camarasabara.mg.gov.br/" target="_blank">Câmara Municipal de Sabará</a><br />
<a href="http://www.sabinopoliscam.com.br/" target="_blank">Câmara Municipal de Sabinópolis</a><br />
<a href="http://sacramento.cam.mg.gov.br/" target="_blank">Câmara Municipal de Sacramento</a><br />
<a href="http://www.camarasalinas.mg.gov.br/" target="_blank">Câmara Municipal de Salinas</a><br />
<a href="http://www.santabarbara.cam.mg.gov.br/" target="_blank">Câmara Municipal de Santa Bárbara</a><br />
<a href="http://www.cmsbl.com.br/" target="_blank">Câmara Municipal de Santa Bárbara do Leste</a><br />
<a href="http://cmsantabarbaradotugurio.mg.gov.br/" target="_blank">Câmara Municipal de Santa Bárbara do Tugúrio</a><br />
<a href="http://camaramunicipaldesantacruzdeminas.blogspot.com/" target="_blank">Câmara Municipal de Santa Cruz de Minas</a><br />
<a href="http://camarasantaefigeniademinas.com.br/" target="_blank">Câmara Municipal de Santa Efigênia de Minas</a><br />
<a href="http://www.santajuliana.cam.mg.gov.br" target="_blank">Câmara Municipal de Santa Juliana</a><br />
<a href="http://santahelenademinas.mg.leg.br/" target="_blank">Câmara Municipal de Santa Helena de Minas</a><br />
<a href="http://www.cmsantaluzia.mg.gov.br" target="_blank">Câmara Municipal de Santa Luzia</a><br />
<a href="http://camara.santaritadecaldas.mg.gov.br/" target="_blank">Câmara Municipal de Santa Rita de Caldas</a><br />
<a href="http://www.santaritadeibitipoca.cam.mg.gov.br/" target="_blank">Câmara Municipal de Santa Rita de Ibitipoca</a><br />
<a href="http://santaritadejacutinga.mg.leg.br/" target="_blank">Câmara Municipal de Santa Rita de Jacutinga</a><br />
<a href="http://www.cmsantaritademinas.mg.gov.br/" target="_blank">Câmara Municipal de Santa Rita de Minas</a><br />
<a href="http://www.santaritadosapucai.mg.leg.br/" target="_blank">Câmara Municipal de Santa Rita do Sapucaí</a><br />
<a href="http://camarasantarosadaserra.mg.gov.br/" target="_blank">Câmara Municipal de Santa Rosa da Serra</a><br />
<a href="http://www.camarasantavitoria.mg.gov.br/" target="_blank">Câmara Municipal de Santa Vitória</a><br />
<a href="http://www.camarasantana.com.br/" target="_blank">Câmara Municipal de Santana de Cataguases</a><br />
<a href="http://cmsj.mg.gov.br/" target="_blank">Câmara Municipal de Santana do Jacaré</a><br />
<a href="http://camaraparaiso.mg.gov.br/" target="_blank">Câmara Municipal de Santana do Paraíso</a><br />
<a href="http://www.camarasaa.mg.gov.br/" target="_blank">Câmara Municipal de Santo Antônio do Amparo</a><br />
<a href="http://camarasaaventureiro.com.br/" target="_blank">Câmara Municipal de Santo Antônio do Aventureiro</a><br />
<a href="http://cmsantoantoniodograma.mg.gov.br/" target="_blank">Câmara Municipal de Santo Antônio do Grama</a><br />
<a href="http://www.camarasam.mg.gov.br/" target="_blank">Câmara Municipal de Santo Antônio do Monte</a><br />
<a href="http://www.camarasd.mg.gov.br/" target="_blank">Câmara Municipal de Santos Dumont</a><br />
<a href="http://saobentoabade.cam.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de São Bento Abade</a><br />
<a href="http://www.saobrasdosuacui.cam.mg.gov.br/" target="_blank">Câmara Municipal de São Brás do Suaçuí</a><br />
<a href="http://www.camaradoprata.mg.gov.br/" target="_blank">Câmara Municipal de São Domingos do Prata</a><br />
<a href="http://saofelixdeminas.cam.mg.gov.br/" target="_blank">Câmara Municipal de São Félix de Minas</a><br />
<a href="http://www.camarasaofrancisco.mg.gov.br" target="_blank">Câmara Municipal de São Francisco</a><br />
<a href="http://www.camarasaofranciscodepaula.mg.gov.br/site/" target="_blank">Câmara Municipal de São Francisco de Paula</a><br />
<a href="http://camaramunicipalsfs.blogspot.com/" target="_blank">Câmara Municipal de São Francisco de Sales</a><br />
<a href="http://camarasaogoncalodopara.mg.gov.br/" target="_blank">Câmara Municipal de São Gonçalo do Pará</a><br />
<a href="http://www.camarasaogoncalo.mg.gov.br" target="_blank">Câmara Municipal de São Gonçalo do Rio Abaixo</a><br />
<a href="http://www.camarasgs.mg.gov.br/" target="_blank">Câmara Municipal de São Gonçalo do Sapucaí</a><br />
<a href="http://www.camarasaogotardo.mg.gov.br/" target="_blank">Câmara Municipal de São Gotardo</a><br />
<a href="http://www.camarasaojoaodelrei.com.br/" target="_blank">Câmara Municipal de São João del-Rei</a><br />
<a href="http://www.camarasjn.mg.gov.br/" target="_blank">Câmara Municipal de São João Nepomuceno</a><br />
<a href="http://camarasaojoaodamata.mg.gov.br/" target="_blank">Câmara Municipal de São João da Mata</a><br />
<a href="http://www.camarasaojoaquimdebicas.mg.gov.br/" target="_blank">Câmara Municipal de São Joaquim de Bicas</a><br />
<a href="http://camaradesaojosedabarra.webnode.com.br/" target="_blank">Câmara Municipal de São José da Barra</a><br />
<a href="http://www.camarasjl.mg.gov.br" target="_blank">Câmara Municipal de São José da Lapa</a><br />
<a href="http://saojosedavarginha.cam.mg.gov.br/site/" target="_blank">Câmara Municipal de São José da Varginha</a><br />
<a href="http://www.camarasl.mg.gov.br" target="_blank">Câmara Municipal de São Lourenço</a><br />
<a href="http://www.camarassbv.mg.gov.br" target="_blank">Câmara Municipal de São Sebastião da Bela Vista</a><br />
<a href="http://saosebastiaodooeste.cam.mg.gov.br/" target="_blank">Câmara Municipal de São Sebastião do Oeste</a><br />
<a href="http://www.camarassparaiso.mg.gov.br/.web3" target="_blank">Câmara Municipal de São Sebastião do Paraíso</a><br />
<a href="http://www.saosebastiaodorioverde.mg.leg.br/" target="_blank">Câmara Municipal de São Sebastião do Rio Verde</a><br />
<a href="http://camarasaotiago.mg.gov.br/" target="_blank">Câmara Municipal de São Tiago</a><br />
<a href="http://www.saothomedasletras.mg.leg.br/" target="_blank">Câmara Municipal de São Tomé das Letras</a><br />
<a href="http://www.camarasvm.mg.gov.br/" target="_blank">Câmara Municipal de São Vicente de Minas</a><br />
<a href="http://www.camarasapucaimirim.mg.gov.br/" target="_blank">Câmara Municipal de Sapucaí Mirim</a><br />
<a href="http://camarasardoa.mg.gov.br/" target="_blank">Câmara Municipal de Sardoá</a><br />
<a href="http://www.camarasarzedo.mg.gov.br" target="_blank">Câmara Municipal de Sarzedo</a><br />
<a href="http://www.senadorjosebento.mg.leg.br/" target="_blank">Câmara Municipal de Senador José Bento</a><br />
<a href="http://serraazuldeminas.cammg.com.br/" target="_blank">Câmara Municipal de Serra Azul de Minas</a><br />
<a href="http://www.camaraserranos.mg.gov.br/" target="_blank">Câmara Municipal de Serranos</a><br />
<a href="http://www.setelagoas.mg.leg.br/" target="_blank">Câmara Municipal de Sete Lagoas</a><br />
<a href="http://silveirania.cam.mg.gov.br/" target="_blank">Câmara Municipal de Silveirânia</a><br />
<a href="http://www.silvianopolis.mg.leg.br/" target="_blank">Câmara Municipal de Silvianópolis</a><br />
<a href="http://simaopereira.cam.mg.gov.br/" target="_blank">Câmara Municipal de Simão Pereira</a><br />
<a href="http://www.cmsoledadedeminas.com.br/" target="_blank">Câmara Municipal de Soledade de Minas</a><br />
<a href="http://www.taiobeiras.cam.mg.gov.br/" target="_blank">Câmara Municipal de Taiobeiras</a><br />
<a href="http://www.camarataparuba.mg.gov.br/" target="_blank">Câmara Municipal de Taparuba</a><br />
<a href="http://www.camaratapira.mg.gov.br/" target="_blank">Câmara Municipal de Tapira</a><br />
<a href="http://www.camaramunicipaldeteixeiras.org/" target="_blank">Câmara Municipal de Teixeiras</a><br />
<a href="http://www.cmto.mg.gov.br/" target="_blank">Câmara Municipal de Teófilo Otoni</a><br />
<a href="http://www.timoteo.cam.mg.gov.br/" target="_blank">Câmara Municipal de Timóteo</a><br />
<a href="http://www.camaratiradentes.mg.gov.br/" target="_blank">Câmara Municipal de Tiradentes</a><br />
<a href="http://www.cmtocantins.mg.gov.br/" target="_blank">Câmara Municipal de Tocantins</a><br />
<a href="http://www.tocosdomoji.mg.leg.br/" target="_blank">Câmara Municipal de Tocos do Moji</a><br />
<a href="http://www.camaratombos.mg.gov.br/" target="_blank">Câmara Municipal de Tombos</a><br />
<a href="http://www.camaratc.mg.gov.br/" target="_blank">Câmara Municipal de Três Corações</a><br />
<a href="http://www.tresmarias.cam.mg.gov.br/" target="_blank">Câmara Municipal de Três Marias</a><br />
<a href="http://www.camaratrespontas.mg.gov.br/" target="_blank">Câmara Municipal de Três Pontas</a><br />
<a href="http://www.tumiritinga.mg.leg.br/" target="_blank">Câmara Municipal de Tumiritinga</a><br />
<a href="http://www.camaratupaciguara.mg.gov.br" target="_blank">Câmara Municipal de Tupaciguara</a><br />
<a href="http://camaramunicipaldeturmalina-mg.blogspot.com/" target="_blank">Câmara Municipal de Turmalina</a><br />
<a href="http://camaraturvolandia.mg.gov.br/" target="_blank">Câmara Municipal de Turvolândia</a><br />
<a href="http://www.camarauba.mg.gov.br/" target="_blank">Câmara Municipal de Ubá</a><br />
<a href="http://www.cmubaporanga.mg.gov.br/" target="_blank">Câmara Municipal de Ubaporanga</a><br />
<a href="http://www.camarauberaba.mg.gov.br/" target="_blank">Câmara Municipal de Uberaba</a><br />
<a href="http://www.camarauberlandia.mg.gov.br/" target="_blank">Câmara Municipal de Uberlândia</a><br />
<a href="http://www.camaraunai.mg.gov.br/" target="_blank">Câmara Municipal de Unaí</a><br />
<a href="http://www.camarauniaodeminas.com.br/" target="_blank">Câmara Municipal de União de Minas</a><br />
<a href="http://www.camarauruana.mg.gov.br/" target="_blank">Câmara Municipal de Uruana de Minas</a><br />
<a href="http://camaravargembonita.mg.gov.br/" target="_blank">Câmara Municipal de Vargem Bonita</a><br />
<a href="http://www.camaravarginha.mg.gov.br" target="_blank">Câmara Municipal de Varginha</a><br />
<a href="http://www.varjaodeminas.mg.leg.br/" target="_blank">Câmara Municipal de Varjão de Minas</a><br />
<a href="http://www.camaradevarzeadapalma.mg.gov.br" target="_blank">Câmara Municipal de Várzea da Palma</a><br />
<a href="http://www.camaravarzelandia.mg.gov.br/" target="_blank">Câmara Municipal de Varzelândia</a><br />
<a href="http://www.camaravazante.mg.gov.br/" target="_blank">Câmara Municipal de Vazante</a><br />
<a href="http://www.camaraverissimo.mg.gov.br/index.htm" target="_blank">Câmara Municipal de Veríssimo</a><br />
<a href="http://www.vermelhonovo.cam.mg.gov.br/" target="_blank">Câmara Municipal de Vermelho Novo</a><br />
<a href="http://www.camaravespasiano.mg.gov.br/" target="_blank">Câmara Municipal de Vespasiano</a><br />
<a href="http://www.vicosa.mg.leg.br/" target="_blank">Câmara Municipal de Viçosa</a><br />
<a href="http://www.camaravgp.mg.gov.br/" target="_blank">Câmara Municipal de Virginópolis</a><br />
<a href="http://www.camaravirgolandia.mg.gov.br/site/" target="_blank">Câmara Municipal de Virgolândia</a><br />
<a href="http://www.camaravrb.mg.gov.br/" target="_blank">Câmara Municipal de Visconde do Rio Branco</a><br />
<a href="http://www.voltagrande.cam.mg.gov.br/" target="_blank">Câmara Municipal de Volta Grande</a></p>
"""

soup = BeautifulSoup(html, 'html.parser')

for link in soup.find_all('a'):
    print(f'"{link.get("href")}", ', end='')


```

    "http://www.camaradeaimores.mg.gov.br", "http://www.camaraaiuruoca.mg.gov.br/", "http://www.albertina.cam.mg.gov.br/home/index.php", "http://www.alemparaiba.cam.mg.gov.br/", "http://www.cmalfenas.mg.gov.br", "http://www.camaraalfredovasconcelos.mg.gov.br", "http://www.almenara.cam.mg.gov.br/", "http://www.cmalterosa.mg.gov.br", "http://www.cmaltocaparao.mg.gov.br/", "http://www.cmaltojequitiba.mg.gov.br/", "http://www.alvarengacamara.com.br/", "http://www.camaraandradas.mg.gov.br", "http://www.camaraandrelandia.mg.gov.br/", "http://www.cmac.mg.gov.br", "http://www.camaraaraguari.mg.gov.br/", "http://www.camaraarapora.mg.gov.br/", "http://187.32.64.185:8180/portal", "http://www.camaraarceburgo.mg.gov.br/", "http://www.camaraarcos.mg.gov.br/", "http://www.camaradeareado.mg.gov.br/novo/index.php", "http://www.camaraarinos.mg.gov.br/", "http://camaraataleia.mg.gov.br/", "http://www.camarabaependi.mg.gov.br", "http://www.camarabambui.mg.gov.br", "http://www.cmbaraodecocais.mg.gov.br", "http://www.camarabarbacena.mg.gov.br", "http://www.camarabarroso.mg.gov.br", "http://www.camarabelavista.mg.gov.br", "http://www.cmbh.mg.gov.br/", "http://www.belovale.cam.mg.gov.br/", "http://camaramunicipalbertopolis.com.br/", "http://www.camarabetim.mg.gov.br/", "http://www.camarabicas.mg.gov.br/", "http://www.camaraboaesperanca.mg.gov.br", "http://www.camarabocainademinas.mg.gov.br/", "http://www.camarabocaiuva.cam.mg.gov.br/", "http://www.camarabd.mg.gov.br/", "http://www.cmbj.mg.gov.br/", "http://www.camarabomjesusdapenha.mg.gov.br/", "http://www.bomjesusdoamparo.mg.leg.br/", "http://www.camarabonfin.mg.gov.br/", "http://www.camaradebotelhos.mg.gov.br/novo/", "http://www.brasilandiademinas.mg.leg.br/", "http://camarabrasiliademinas.com.br/", "http://www.camarabrazopolis.mg.gov.br/", "http://www.cmbrumadinho.mg.gov.br/", "http://www.cmburitis.mg.gov.br/", "http://camaradeburitizeiro.mg.gov.br/", "http://www.cmcg.mg.gov.br/", "http://www.camaracachoeirademinas.mg.gov.br/", "http://www.camaradecaete.mg.gov.br", "http://www.camaracaiana.mg.gov.br/", "http://www.camaracaldas.mg.gov.br/principal.asp", "http://www.camaracamacho.mg.gov.br", "http://www.camaracamanducaia.mg.gov.br", "http://www.camaracambui.mg.gov.br/", "http://www.camaracambuquira.mg.gov.br/", "http://www.campanario.cam.mg.gov.br/", "http://www.camaracampanha.mg.gov.br", "http://www.campinaverde.mg.leg.br/portal", "http://www.camara.campobelo.mg.gov.br/", "http://www.camaracampodomeio.mg.gov.br/", "http://camaracamposaltos.mg.gov.br", "http://www.camaracg.mg.gov.br", "http://www.canapolis.mg.leg.br/site/", "http://www.camaracapelinha.com.br/", "http://www.camaracapetinga.net/", "http://www.camaradecapitaoandrade.com.br/", "http://www.capimbranco.mg.leg.br/", "http://www.camaracapinopolis.mg.gov.br", "http://www.cmcaputira.mg.gov.br/", "http://www.camaracarandai.mg.gov.br/", "http://www.camaracarangola.mg.gov.br", "http://www.cmcaratinga.mg.gov.br", "http://www.cmcarbonita.mg.gov.br", "http://www.cmcareacu.mg.gov.br/", "http://carmesia.cam.mg.gov.br/", "http://www.camaradecachoeira.com.br", "http://camaracarmodamata.mg.gov.br/", "http://www.cmcm.mg.gov.br/", "http://www.camaracarmodocajuru.mg.gov.br/", "http://www.carmodoparanaiba.mg.leg.br/", "http://www.carmodorioclaro.cam.mg.gov.br/", "http://www.camaracarmopolis.mg.gov.br", "http://www.cmcarneirinho.mg.gov.br", "http://www.camaradecarrancas.mg.gov.br/", "http://www.carvalhopolis.mg.leg.br/", "http://www.camaracasagrande.mg.gov.br", "http://www.cassia.cam.mg.gov.br/principal.asp", "http://www.cataguases.mg.leg.br/", "http://www.camaracaxambu.mg.gov.br", "http://www.cmchale.mg.gov.br/", "http://www.camaraclaraval.mg.gov.br/", "http://www.camaraclaudio.mg.gov.br/", "http://camaraconceicao.mg.gov.br/", "http://www.cmci.mg.gov.br/", "http://www.conceicaodopara.cam.mg.gov.br", "http://www.conceicaodosouros.mg.leg.br/", "http://www.confins.mg.leg.br/", "http://www.camaracongonhal.mg.gov.br/", "http://www.camaracongonhas.mg.gov.br/", "http://camaraconquista.mg.gov.br/", "http://www.camaraconselheirolafaiete.mg.gov.br", "http://www.cmcpena.mg.gov.br/", "http://www.camaraconsolacao.mg.gov.br/", "http://www.cmc.mg.gov.br", "http://camaracordislandia.mg.gov.br/", "http://www.camaracoromandel.mg.gov.br", "http://www.camarafabriciano.mg.gov.br/", "http://coronelpacheco.cam.mg.gov.br/", "http://www.camaracxc.mg.gov.br/sitio/", "http://www.camaracorregodanta.mg.gov.br/", "http://www.camaracbjesus.com.br/", "http://www.coutodemagalhaesdeminas.mg.leg.br/", "http://www.cristianootoni.cam.mg.gov.br/", "http://crisolita.mg.leg.br/", "http://cristina.cam.mg.gov.br/", "http://www.camaracruzilia.mg.gov.br", "http://www.cmcurvelo.mg.gov.br/", "http://www.delfinopolis.cam.mg.gov.br/principal.asp", "http://www.delta.mg.leg.br/", "http://www.descoberto.mg.leg.br/", "http://www.camaradiamantina.cam.mg.gov.br/", "http://www.dionisio.cam.mg.gov.br/", "http://www.camaradivinolandia.mg.gov.br/", "http://www.camaradiv.mg.gov.br", "http://www.dombosco.mg.leg.br/", "http://www.camaradomsilverio.mg.gov.br/", "http://www.donaeuzebia.mg.leg.br/", "http://www.camaradoresdecampos.com.br/", "http://www.cmdoresdoindaia.mg.gov.br/", "http://entreriosdeminas.cam.mg.gov.br/", "http://www.camaraervalia.mg.gov.br/", "http://www.camaraesmeraldas.mg.gov.br/", "http://www.camaraefeliz.mg.gov.br", "http://www.camaraestiva.mg.gov.br/", "http://www.estreladoindaia.cam.mg.gov.br/", "http://www.camaraestreladosul.mg.gov.br/", "http://www.camaraextrema.mg.gov.br/", "http://www.cmfama.mg.gov.br", "http://camaradefarialemos.com.br/", "http://www.ferros.cam.mg.gov.br/", "http://www.fervedouro.mg.leg.br/", "http://www.florestal.mg.leg.br/", "http://www.camaraformiga.mg.gov.br/", "http://www.formoso.mg.leg.br/", "http://www.camarafortalezademinas.mg.gov.br/", "http://www.cmfortunademinas.mg.gov.br/", "http://www.camarafronteira.mg.gov.br", "http://www.camarafrutal.mg.gov.br/", "http://www.galileia.cam.mg.gov.br/", "http://www.camaragoncalves.mg.gov.br/", "http://www.camaragv.mg.gov.br/", "http://www.cmgm.mg.gov.br/", "http://www.camaradeguanhaes.mg.gov.br", "http://www.camaraguaranesia.mg.gov.br/", "http://www.cmguarani.mg.gov.br/", "http://www.camaraguardamor.mg.gov.br/", "http://camaraguaxupe.mg.gov.br/", "http://www.guimarania.mg.leg.br/", "http://www.cmheliodora.mg.gov.br/", "http://www.ibia.mg.leg.br/", "http://www.camaraibiraci.mg.gov.br/", "http://www.camaraibirite.mg.gov.br/", "http://www.cmigarape.mg.gov.br/", "http://www.camaraigaratinga.mg.gov.br/", "http://www.cyberbalada.com/iguatama/", "http://www.camarainconfidentes.mg.gov.br", "http://www.indaiabira.mg.leg.br/", "http://camaraindianopolis.mg.gov.br/", "http://www.cminimutaba.com.br/", "http://www.camaraipanema.mg.gov.br", "http://www.camaraipatinga.mg.gov.br", "http://www.camaraipiacu.mg.gov.br/", "http://www.iraideminas.cam.mg.gov.br/", "http://www.itabira.cam.mg.gov.br", "http://www.itabirito.cam.mg.gov.br/", "http://camaraitaguara.mg.gov.br/principal.asp", "http://www.itajuba.cam.mg.gov.br", "http://www.itamogi.mg.leg.br/", "http://www.camaramunicipaldeitamonte.net/", "http://www.itanhandu.cam.mg.gov.br/", "http://www.cmitanhomi.com.br", "http://www.sitesrm.com.br/cmitaobim.mg.gov.br", "http://www.cmitapagipe.mg.gov.br", "http://www.itapecerica.cam.mg.gov.br", "http://www.camaraitapeva.mg.gov.br", "http://www.camaraitaudeminas.mg.gov.br/", "http://www.cmitauna.mg.gov.br", "http://www.ituiutaba.mg.leg.br/", "http://www.camaraiturama.com.br/", "http://www.cmjaboticatubas.mg.gov.br/", "http://camarajacinto.mg.gov.br/", "http://www.jacui.mg.leg.br/", "http://www.camarajacutinga.mg.gov.br/", "http://www.camarajaguaracu.com/", "http://www.jaiba.mg.leg.br/", "http://www.jampruca.cam.mg.gov.br/", "http://www.janauba.mg.leg.br/", "http://www.camarajanuaria.mg.gov.br/", "http://www.jequitinhonha.mg.leg.br/", "http://www.camarajesuania.mg.gov.br/", "http://www.joaima.mg.leg.br/", "http://www.joaquimfelicio.mg.leg.br/", "http://www.camarajm.mg.gov.br", "http://www.joaopinheiro.mg.leg.br/", "http://www.jordania.mg.leg.br/portal/", "http://www.cmjuatuba.mg.gov.br/", "http://isal.camarajf.mg.gov.br", "http://www.juruaia.cam.mg.gov.br/", "http://www.juvenilia.net.br/", "http://www.lagamar.mg.leg.br/", "http://www.camaralp.mg.gov.br", "http://www.camaralagoa.mg.gov.br", "http://www.cmlagoasanta.mg.gov.br", "http://www.cmlajinha.mg.gov.br", "http://www.camaralambari.mg.gov.br/", "http://www.camaradelassance.mg.gov.br/", "http://www.camaralavras.mg.gov.br/", "http://www.camaradeleopoldina.mg.gov.br", "http://camaraliberdade.mg.gov.br/site/", "http://www.camarald.mg.gov.br", "http://www.limeiradooeste.mg.leg.br/", "http://www.luislandia.mg.leg.br/", "http://www.luminarias.cam.mg.gov.br/", "http://www.camaramunicipaldeluz.mg.gov.br", "http://www.camaramachacalis.mg.gov.br/", "http://www.camaramachado.mg.gov.br/", "http://www.mamonas.mg.leg.br/", "http://www.camaramanhuacu.com.br/", "http://www.manhumirim.mg.leg.br/", "http://www.mantena.mg.leg.br/", "http://www.camarademariadafe.com/", "http://camarademariana.mg.gov.br", "http://www.cmmc.mg.gov.br/", "http://www.cmmarmelopolis.mg.gov.br/", "http://www.camaramcampos.mg.gov.br/", "http://www.camaramateusleme.mg.gov.br/", "http://cmmb.mg.gov.br", "http://www.camaramatozinhos.mg.gov.br", "http://minasnovas.mg.leg.br/", "http://www.camaramiradouro.mg.gov.br", "http://mirai.cam.mg.gov.br/", "http://www.camarademoeda.com.br", "http://camaramoema.mg.gov.br/", "http://www.cmmonjolos.mg.gov.br/", "http://www.monsenhorpaulo.cam.mg.gov.br/principal.asp", "http://camaramontalvania.mg.gov.br/", "http://www.montealegredeminas.cam.mg.gov.br", "http://www.camaramunicipaldemonteazul.mg.gov.br/", "http://www.camaramontebelo.mg.gov.br", "http://www.camaramontecarmelo.mg.gov.br", "http://www.montesantodeminas.mg.leg.br/", "http://www.camaramontesiao.com.br", "http://www.cmmoc.mg.gov.br/", "http://www.camaraemacao.mg.gov.br", "http://www.morrodagarca.cam.mg.gov.br/", "http://www.camaramuriae.mg.gov.br", "http://www.camaramutum.mg.gov.br/", "http://www.camaramuzambinho.mg.gov.br/", "http://www.camarananuque.com.br", "http://www.camaranatalandia.mg.gov.br/", "http://www.cmnatercia.mg.gov.br", "http://www.camaranepomuceno.com.br/", "http://www.cmne.mg.gov.br", "http://www.cmnovalima.mg.gov.br/", "http://www.novaserrana.cam.mg.gov.br", "http://camara.olimpionoronha.mg.gov.br/", "http://www.oliveira.cam.mg.gov.br/", "http://camaraoratorios.mg.gov.br/", "http://www.ourobranco.cam.mg.gov.br", "http://www.camaraourofino.mg.gov.br/", "http://www.cmop.mg.gov.br", "http://paineiras.cam.mg.gov.br/", "http://www.camarapains.mg.gov.br", "http://www.camarapm.mg.gov.br/", "http://www.camaraptu.mg.gov.br/", "http://www.camaradeparaguacu.mg.gov.br", "http://www.paraopeba.cam.mg.gov.br/", "http://www.cmpassaquatro.mg.gov.br/", "http://www.camarapassatempo.mg.gov.br/", "http://www.camarapassos.mg.gov.br", "http://www.camarapatos.mg.gov.br", "http://cmpatrocinio.mg.gov.br", "http://www.pecanha.mg.leg.br/principal.asp", "http://pedraazul.mg.leg.br/", "http://camarapb.blogspot.com.br/", "http://www.camarapedraindaia.com.br/", "http://camarapd.mg.gov.br/", "http://www.pedralva.cam.mg.gov.br/principal.asp", "http://www.pedrinopolis.mg.leg.br/", "http://www.camarapl.mg.gov.br", "http://www.pedroteixeira.cam.mg.gov.br/", "http://www.camarapequi.mg.gov.br/", "http://www.camaraperdizes.com.br/", "http://www.pescador.cam.mg.gov.br/", "http://piau.cam.mg.gov.br/", "http://www.camarapiracema.mg.gov.br/", "http://www.cmpirangucu.com.br/", "http://www.camaradepiranguinho.com.br/", "http://www.pirapetinga.mg.leg.br/", "http://www.camaradepirapora.mg.gov.br", "http://www.cmpirauba.mg.gov.br/", "http://www.camarapiumhi.mg.gov.br", "http://www.cmplanura.mg.gov.br", "http://www.camarapocos.mg.gov.br", "http://camaramunicipaldepompeu.mg.gov.br/", "http://www.pontenova.mg.leg.br/", "http://www.camarapv.com.br/", "http://www.cmpa.mg.gov.br", "http://www.pousoalto.mg.leg.br/", "http://www.prados.cam.mg.gov.br/site/", "http://www.camaraprata.mg.gov.br/", "http://www.cmpo.mg.gov.br", "http://www.cmraposos.com.br", "http://www.cmraulsoares.mg.gov.br", "http://www.reduto.mg.leg.br/", "http://www.camaraderesendecosta.mg.gov.br/", "http://www.camaraderessaquinha.mg.gov.br/", "http://www.cmrn.mg.gov.br", "http://www.rioacima.mg.leg.br/", "http://www.camarariocasca.mg.gov.br/", "http://www.camararionovo.mg.gov.br", "http://www.camararioparanaiba.mg.gov.br/", "http://camararp.mg.gov.br", "http://www.cmriopomba.mg.gov.br", "http://www.cmrp.mg.gov.br", "http://www.ritapolis.mg.leg.br/", "http://rodeiro.mg.leg.br/", "http://camararubim.mg.gov.br/", "http://www.camarasabara.mg.gov.br/", "http://www.sabinopoliscam.com.br/", "http://sacramento.cam.mg.gov.br/", "http://www.camarasalinas.mg.gov.br/", "http://www.santabarbara.cam.mg.gov.br/", "http://www.cmsbl.com.br/", "http://cmsantabarbaradotugurio.mg.gov.br/", "http://camaramunicipaldesantacruzdeminas.blogspot.com/", "http://camarasantaefigeniademinas.com.br/", "http://www.santajuliana.cam.mg.gov.br", "http://santahelenademinas.mg.leg.br/", "http://www.cmsantaluzia.mg.gov.br", "http://camara.santaritadecaldas.mg.gov.br/", "http://www.santaritadeibitipoca.cam.mg.gov.br/", "http://santaritadejacutinga.mg.leg.br/", "http://www.cmsantaritademinas.mg.gov.br/", "http://www.santaritadosapucai.mg.leg.br/", "http://camarasantarosadaserra.mg.gov.br/", "http://www.camarasantavitoria.mg.gov.br/", "http://www.camarasantana.com.br/", "http://cmsj.mg.gov.br/", "http://camaraparaiso.mg.gov.br/", "http://www.camarasaa.mg.gov.br/", "http://camarasaaventureiro.com.br/", "http://cmsantoantoniodograma.mg.gov.br/", "http://www.camarasam.mg.gov.br/", "http://www.camarasd.mg.gov.br/", "http://saobentoabade.cam.mg.gov.br/principal.asp", "http://www.saobrasdosuacui.cam.mg.gov.br/", "http://www.camaradoprata.mg.gov.br/", "http://saofelixdeminas.cam.mg.gov.br/", "http://www.camarasaofrancisco.mg.gov.br", "http://www.camarasaofranciscodepaula.mg.gov.br/site/", "http://camaramunicipalsfs.blogspot.com/", "http://camarasaogoncalodopara.mg.gov.br/", "http://www.camarasaogoncalo.mg.gov.br", "http://www.camarasgs.mg.gov.br/", "http://www.camarasaogotardo.mg.gov.br/", "http://www.camarasaojoaodelrei.com.br/", "http://www.camarasjn.mg.gov.br/", "http://camarasaojoaodamata.mg.gov.br/", "http://www.camarasaojoaquimdebicas.mg.gov.br/", "http://camaradesaojosedabarra.webnode.com.br/", "http://www.camarasjl.mg.gov.br", "http://saojosedavarginha.cam.mg.gov.br/site/", "http://www.camarasl.mg.gov.br", "http://www.camarassbv.mg.gov.br", "http://saosebastiaodooeste.cam.mg.gov.br/", "http://www.camarassparaiso.mg.gov.br/.web3", "http://www.saosebastiaodorioverde.mg.leg.br/", "http://camarasaotiago.mg.gov.br/", "http://www.saothomedasletras.mg.leg.br/", "http://www.camarasvm.mg.gov.br/", "http://www.camarasapucaimirim.mg.gov.br/", "http://camarasardoa.mg.gov.br/", "http://www.camarasarzedo.mg.gov.br", "http://www.senadorjosebento.mg.leg.br/", "http://serraazuldeminas.cammg.com.br/", "http://www.camaraserranos.mg.gov.br/", "http://www.setelagoas.mg.leg.br/", "http://silveirania.cam.mg.gov.br/", "http://www.silvianopolis.mg.leg.br/", "http://simaopereira.cam.mg.gov.br/", "http://www.cmsoledadedeminas.com.br/", "http://www.taiobeiras.cam.mg.gov.br/", "http://www.camarataparuba.mg.gov.br/", "http://www.camaratapira.mg.gov.br/", "http://www.camaramunicipaldeteixeiras.org/", "http://www.cmto.mg.gov.br/", "http://www.timoteo.cam.mg.gov.br/", "http://www.camaratiradentes.mg.gov.br/", "http://www.cmtocantins.mg.gov.br/", "http://www.tocosdomoji.mg.leg.br/", "http://www.camaratombos.mg.gov.br/", "http://www.camaratc.mg.gov.br/", "http://www.tresmarias.cam.mg.gov.br/", "http://www.camaratrespontas.mg.gov.br/", "http://www.tumiritinga.mg.leg.br/", "http://www.camaratupaciguara.mg.gov.br", "http://camaramunicipaldeturmalina-mg.blogspot.com/", "http://camaraturvolandia.mg.gov.br/", "http://www.camarauba.mg.gov.br/", "http://www.cmubaporanga.mg.gov.br/", "http://www.camarauberaba.mg.gov.br/", "http://www.camarauberlandia.mg.gov.br/", "http://www.camaraunai.mg.gov.br/", "http://www.camarauniaodeminas.com.br/", "http://www.camarauruana.mg.gov.br/", "http://camaravargembonita.mg.gov.br/", "http://www.camaravarginha.mg.gov.br", "http://www.varjaodeminas.mg.leg.br/", "http://www.camaradevarzeadapalma.mg.gov.br", "http://www.camaravarzelandia.mg.gov.br/", "http://www.camaravazante.mg.gov.br/", "http://www.camaraverissimo.mg.gov.br/index.htm", "http://www.vermelhonovo.cam.mg.gov.br/", "http://www.camaravespasiano.mg.gov.br/", "http://www.vicosa.mg.leg.br/", "http://www.camaravgp.mg.gov.br/", "http://www.camaravirgolandia.mg.gov.br/site/", "http://www.camaravrb.mg.gov.br/", "http://www.voltagrande.cam.mg.gov.br/", 


```python
from bs4 import BeautifulSoup

html = """
<a href="http://www.camaradeaimores.mg.gov.br" target="_blank">Câmara Municipal de Aimorés</a><br />
<a href="http://www.camaraaiuruoca.mg.gov.br/" target="_blank">Câmara Municipal de Aiuruoca</a><br />
<a href="http://www.albertina.cam.mg.gov.br/home/index.php" target="_blank">Câmara Municipal de Albertina</a><br />
<a href="http://www.alemparaiba.cam.mg.gov.br/" target="_blank">Câmara Municipal de Além Paraíba</a><br />
<a href="http://www.cmalfenas.mg.gov.br" target="_blank">Câmara Municipal de Alfenas</a><br />
<a href="http://www.camaraalfredovasconcelos.mg.gov.br" target="_blank">Câmara Municipal de Alfredo Vasconcelos</a><br />
<a href="http://www.almenara.cam.mg.gov.br/" target="_blank">Câmara Municipal de Almenara</a><br />
<a href="http://www.cmalterosa.mg.gov.br" target="_blank">Câmara Municipal de Alterosa</a><br />
<a href="http://www.cmaltocaparao.mg.gov.br/" target="_blank">Câmara Municipal de Alto Caparaó</a><br />
<a href="http://www.cmaltojequitiba.mg.gov.br/" target="_blank">Câmara Municipal de Alto Jequitibá</a><br />
<a href="http://www.alvarengacamara.com.br/" target="_blank">Câmara Municipal de Alvarenga</a><br />
<a href="http://www.camaraandradas.mg.gov.br" target="_blank">Câmara Municipal de Andradas</a><br />
<a href="http://www.camaraandrelandia.mg.gov.br/" target="_blank">Câmara Municipal de Andrelândia</a><br />
<a href="http://www.cmac.mg.gov.br" target="_blank">Câmara Municipal de Antônio Carlos</a><br />
<a href="http://www.camaraaraguari.mg.gov.br/" target="_blank">Câmara Municipal de Araguari</a><br />
<a href="http://www.camaraarapora.mg.gov.br/" target="_blank">Câmara Municipal de Araporã</a><br />
<a href="http://187.32.64.185:8180/portal" target="_blank">Câmara Municipal de Araxá</a><br />
<a href="http://www.camaraarceburgo.mg.gov.br/" target="_blank">Câmara Municipal de Arceburgo</a><br />
<a href="http://www.camaraarcos.mg.gov.br/" target="_blank">Câmara Municipal de Arcos</a><br />
<a href="http://www.camaradeareado.mg.gov.br/novo/index.php" target="_blank">Câmara Municipal de Areado</a><br />
<a href="http://www.camaraarinos.mg.gov.br/" target="_blank">Câmara Municipal de Arinos</a><br />
<a href="http://camaraataleia.mg.gov.br/" target="_blank">Câmara Municipal de Ataleia</a><br />
<a href="http://www.camarabaependi.mg.gov.br" target="_blank">Câmara Municipal de Baependi</a><br />
<a href="http://www.camarabambui.mg.gov.br" target="_blank">Câmara Municipal de Bambuí</a><br />
<a href="http://www.cmbaraodecocais.mg.gov.br" target="_blank">Câmara Municipal de Barão de Cocais</a><br />
<a href="http://www.camarabarbacena.mg.gov.br" target="_blank">Câmara Municipal de Barbacena</a><br />
<a href="http://www.camarabarroso.mg.gov.br" target="_blank">Câmara Municipal de Barroso</a><br />
<a href="http://www.camarabelavista.mg.gov.br" target="_blank">Câmara Municipal de Bela Vista de Minas</a><br />
<a href="http://www.cmbh.mg.gov.br/" target="_blank">Câmara Municipal de Belo Horizonte</a><br />
<a href="http://www.belovale.cam.mg.gov.br/" target="_blank">Câmara Municipal de Belo Vale</a><br />
<a href="http://camaramunicipalbertopolis.com.br/" target="_blank">Câmara Municipal de Bertópolis</a><br />
<a href="http://www.camarabetim.mg.gov.br/" target="_blank">Câmara Municipal de Betim</a><br />
<a href="http://www.camarabicas.mg.gov.br/" target="_blank">Câmara Municipal de Bicas</a><br />
<a href="http://www.camaraboaesperanca.mg.gov.br" target="_blank">Câmara Municipal de Boa Esperança</a><br />
<a href="http://www.camarabocainademinas.mg.gov.br/" target="_blank">Câmara Municipal de Bocaina de Minas</a><br />
<a href="http://www.camarabocaiuva.cam.mg.gov.br/" target="_blank">Câmara Municipal de Bocaiúva</a><br />
<a href="http://www.camarabd.mg.gov.br/" target="_blank">Câmara Municipal de Bom Despacho</a><br />
<a href="http://www.cmbj.mg.gov.br/" target="_blank">Câmara Municipal de Bom Jardim de Minas</a><br />
<a href="http://www.camarabomjesusdapenha.mg.gov.br/" target="_blank">Câmara Municipal de Bom Jesus da Penha</a><br />
<a href="http://www.bomjesusdoamparo.mg.leg.br/" target="_blank">Câmara Municipal de Bom Jesus do Amparo</a><br />
<a href="http://www.camarabonfin.mg.gov.br/" target="_blank">Câmara Municipal de Bonfinópolis de Minas</a><br />
<a href="http://www.camaradebotelhos.mg.gov.br/novo/" target="_blank">Câmara Municipal de Botelhos</a><br />
<a href="http://www.brasilandiademinas.mg.leg.br/" target="_blank">Câmara Municipal de Brasilândia de Minas</a><br />
<a href="http://camarabrasiliademinas.com.br/" target="_blank">Câmara Municipal de Brasília de Minas</a><br />
<a href="http://www.camarabrazopolis.mg.gov.br/" target="_blank">Câmara Municipal de Brazópolis</a><br />
<a href="http://www.cmbrumadinho.mg.gov.br/" target="_blank">Câmara Municipal de Brumadinho</a><br />
<a href="http://www.cmburitis.mg.gov.br/" target="_blank">Câmara Municipal de Buritis</a><br />
<a href="http://camaradeburitizeiro.mg.gov.br/" target="_blank">Câmara Municipal de Buritizeiro</a><br />
<a href="http://www.cmcg.mg.gov.br/" target="_blank">Câmara Municipal de Cabeceira Grande</a><br />
<a href="http://www.camaracachoeirademinas.mg.gov.br/" target="_blank">Câmara Municipal de Cachoeira de Minas</a><br />
<a href="http://www.camaradecaete.mg.gov.br" target="_blank">Câmara Municipal de Caeté</a><br />
<a href="http://www.camaracaiana.mg.gov.br/" target="_blank">Câmara Municipal de Caiana</a><br />
<a href="http://www.camaracaldas.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Caldas</a><br />
<a href="http://www.camaracamacho.mg.gov.br" target="_blank">Câmara Municipal de Camacho</a><br />
<a href="http://www.camaracamanducaia.mg.gov.br" target="_blank">Câmara Municipal de Camanducaia</a><br />
<a href="http://www.camaracambui.mg.gov.br/" target="_blank">Câmara Municipal de Cambuí</a><br />
<a href="http://www.camaracambuquira.mg.gov.br/" target="_blank">Câmara Municipal de Cambuquira</a><br />
<a href="http://www.campanario.cam.mg.gov.br/" target="_blank">Câmara Municipal de Campanário</a><br />
<a href="http://www.camaracampanha.mg.gov.br" target="_blank">Câmara Municipal de Campanha</a><br />
<a href="http://www.campinaverde.mg.leg.br/portal" target="_blank">Câmara Municipal de Campina Verde</a><br />
<a href="http://www.camara.campobelo.mg.gov.br/" target="_blank">Câmara Municipal de Campo Belo</a><br />
<a href="http://www.camaracampodomeio.mg.gov.br/" target="_blank">Câmara Municipal de Campo do Meio</a><br />
<a href="http://camaracamposaltos.mg.gov.br" target="_blank">Câmara Municipal de Campos Altos</a><br />
<a href="http://www.camaracg.mg.gov.br" target="_blank">Câmara Municipal de Campos Gerais</a><br />
<a href="http://www.canapolis.mg.leg.br/site/" target="_blank">Câmara Municipal de Canápolis</a><br />
<a href="http://www.camaracapelinha.com.br/" target="_blank">Câmara Municipal de Capelinha</a><br />
<a href="http://www.camaracapetinga.net/" target="_blank">Câmara Municipal de Capetinga</a><br />
<a href="http://www.camaradecapitaoandrade.com.br/" target="_blank">Câmara Municipal de Capitão Andrade</a><br />
<a href="http://www.capimbranco.mg.leg.br/" target="_blank">Câmara Municipal de Capim Branco</a><br />
<a href="http://www.camaracapinopolis.mg.gov.br" target="_blank">Câmara Municipal de Capinópolis</a><br />
<a href="http://www.cmcaputira.mg.gov.br/" target="_blank">Câmara Municipal de Caputira</a><br />
<a href="http://www.camaracarandai.mg.gov.br/" target="_blank">Câmara Municipal de Carandaí</a><br />
<a href="http://www.camaracarangola.mg.gov.br" target="_blank">Câmara Municipal de Carangola</a><br />
<a href="http://www.cmcaratinga.mg.gov.br" target="_blank">Câmara Municipal de Caratinga</a><br />
<a href="http://www.cmcarbonita.mg.gov.br" target="_blank">Câmara Municipal de Carbonita</a><br />
<a href="http://www.cmcareacu.mg.gov.br/" target="_blank">Câmara Municipal de Careaçu</a><br />
<a href="http://carmesia.cam.mg.gov.br/" target="_blank">Câmara Municipal de Carmésia</a><br />
<a href="http://www.camaradecachoeira.com.br" target="_blank">Câmara Municipal de Carmo da Cachoeira</a><br />
<a href="http://camaracarmodamata.mg.gov.br/" target="_blank">Câmara Municipal de Carmo da Mata</a><br />
<a href="http://www.cmcm.mg.gov.br/" target="_blank">Câmara Municipal de Carmo de Minas</a><br />
<a href="http://www.camaracarmodocajuru.mg.gov.br/" target="_blank">Câmara Municipal de Carmo do Cajuru</a><br />
<a href="http://www.carmodoparanaiba.mg.leg.br/" target="_blank">Câmara Municipal de Carmo do Paranaíba</a><br />
<a href="http://www.carmodorioclaro.cam.mg.gov.br/" target="_blank">Câmara Municipal de Carmo do Rio Claro</a><br />
<a href="http://www.camaracarmopolis.mg.gov.br" target="_blank">Câmara Municipal de Carmópolis de Minas</a><br />
<a href="http://www.cmcarneirinho.mg.gov.br" target="_blank">Câmara Municipal de Carneirinho</a><br />
<a href="http://www.camaradecarrancas.mg.gov.br/" target="_blank">Câmara Municipal de Carrancas</a><br />
<a href="http://www.carvalhopolis.mg.leg.br/" target="_blank">Câmara Municipal de Carvalhópolis</a><br />
<a href="http://www.camaracasagrande.mg.gov.br" target="_blank">Câmara Municipal de Casa Grande</a><br />
<a href="http://www.cassia.cam.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Cássia</a><br />
<a href="http://www.cataguases.mg.leg.br/" target="_blank">Câmara Municipal de Cataguases</a><br />
<a href="http://www.camaracaxambu.mg.gov.br" target="_blank">Câmara Municipal de Caxambu</a><br />
<a href="http://www.cmchale.mg.gov.br/" target="_blank">Câmara Municipal de Chalé</a><br />
<a href="http://www.camaraclaraval.mg.gov.br/" target="_blank">Câmara Municipal de Claraval</a><br />
<a href="http://www.camaraclaudio.mg.gov.br/" target="_blank">Câmara Municipal de Cláudio</a><br />
<a href="http://camaraconceicao.mg.gov.br/" target="_blank">Câmara Municipal de Conceição das Alagoas</a><br />
<a href="http://www.cmci.mg.gov.br/" target="_blank">Câmara Municipal de Conceição de Ipanema</a><br />
<a href="http://www.conceicaodopara.cam.mg.gov.br" target="_blank">Câmara Municipal de Conceição do Pará</a><br />
<a href="http://www.conceicaodosouros.mg.leg.br/" target="_blank">Câmara Municipal de Conceição dos Ouros</a><br />
<a href="http://www.confins.mg.leg.br/" target="_blank">Câmara Municipal de Confins</a><br />
<a href="http://www.camaracongonhal.mg.gov.br/" target="_blank">Câmara Municipal de Congonhal</a><br />
<a href="http://www.camaracongonhas.mg.gov.br/" target="_blank">Câmara Municipal de Congonhas</a><br />
<a href="http://camaraconquista.mg.gov.br/" target="_blank">Câmara Municipal de Conquista</a><br />
<a href="http://www.camaraconselheirolafaiete.mg.gov.br" target="_blank">Câmara Municipal de Conselheiro Lafaiete</a><br />
<a href="http://www.cmcpena.mg.gov.br/" target="_blank">Câmara Municipal de Conselheiro Pena</a><br />
<a href="http://www.camaraconsolacao.mg.gov.br/" target="_blank">Câmara Municipal de Consolação</a><br />
<a href="http://www.cmc.mg.gov.br" target="_blank">Câmara Municipal de Contagem</a><br />
<a href="http://camaracordislandia.mg.gov.br/" target="_blank">Câmara Municipal de Cordislândia</a><br />
<a href="http://www.camaracoromandel.mg.gov.br" target="_blank">Câmara Municipal de Coromandel</a><br />
<a href="http://www.camarafabriciano.mg.gov.br/" target="_blank">Câmara Municipal de Coronel Fabriciano</a><br />
<a href="http://coronelpacheco.cam.mg.gov.br/" target="_blank">Câmara Municipal de Coronel Pacheco</a><br />
<a href="http://www.camaracxc.mg.gov.br/sitio/" target="_blank">Câmara Municipal de Coronel Xavier Chaves</a><br />
<a href="http://www.camaracorregodanta.mg.gov.br/" target="_blank">Câmara Municipal de Córrego Danta</a><br />
<a href="http://www.camaracbjesus.com.br/" target="_blank">Câmara Municipal de Córrego do Bom Jesus</a><br />
<a href="http://www.coutodemagalhaesdeminas.mg.leg.br/" target="_blank">Câmara Municipal de Couto de Magalhães de Minas</a><br />
<a href="http://www.cristianootoni.cam.mg.gov.br/" target="_blank">Câmara Municipal de Cristiano Otoni</a><br />
<a href="http://crisolita.mg.leg.br/" target="_blank">Câmara Municipal de Crisólita</a><br />
<a href="http://cristina.cam.mg.gov.br/" target="_blank">Câmara Municipal de Cristina</a><br />
<a href="http://www.camaracruzilia.mg.gov.br" target="_blank">Câmara Municipal de Cruzília</a><br />
<a href="http://www.cmcurvelo.mg.gov.br/" target="_blank">Câmara Municipal de Curvelo</a><br />
<a href="http://www.delfinopolis.cam.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Delfinópolis</a><br />
<a href="http://www.delta.mg.leg.br/" target="_blank">Câmara Municipal de Delta</a><br />
<a href="http://www.descoberto.mg.leg.br/" target="_blank">Câmara Municipal de Descoberto</a><br />
<a href="http://www.camaradiamantina.cam.mg.gov.br/" target="_blank">Câmara Municipal de Diamantina</a><br />
<a href="http://www.dionisio.cam.mg.gov.br/" target="_blank">Câmara Municipal de Dionísio</a><br />
<a href="http://www.camaradivinolandia.mg.gov.br/" target="_blank">Câmara Municipal de Divinolândia de Minas</a><br />
<a href="http://www.camaradiv.mg.gov.br" target="_blank">Câmara Municipal de Divinópolis</a><br />
<a href="http://www.dombosco.mg.leg.br/" target="_blank">Câmara Municipal de Dom Bosco</a><br />
<a href="http://www.camaradomsilverio.mg.gov.br/" target="_blank">Câmara Municipal de Dom Silvério</a><br />
<a href="http://www.donaeuzebia.mg.leg.br/" target="_blank">Câmara Municipal de Dona Euzébia</a><br />
<a href="http://www.camaradoresdecampos.com.br/" target="_blank">Câmara Municipal de Dores de Campos</a><br />
<a href="http://www.cmdoresdoindaia.mg.gov.br/" target="_blank">Câmara Municipal de Dores do Indaiá</a><br />
<a href="http://entreriosdeminas.cam.mg.gov.br/" target="_blank">Câmara Municipal de Entre Rios de Minas</a><br />
<a href="http://www.camaraervalia.mg.gov.br/" target="_blank">Câmara Municipal de Ervália</a><br />
<a href="http://www.camaraesmeraldas.mg.gov.br/" target="_blank">Câmara Municipal de Esmeraldas</a><br />
<a href="http://www.camaraefeliz.mg.gov.br" target="_blank">Câmara Municipal de Espera Feliz</a><br />
<a href="http://www.camaraestiva.mg.gov.br/" target="_blank">Câmara Municipal de Estiva</a><br />
<a href="http://www.estreladoindaia.cam.mg.gov.br/" target="_blank">Câmara Municipal de Estrela do Indaiá</a><br />
<a href="http://www.camaraestreladosul.mg.gov.br/" target="_blank">Câmara Municipal de Estrela do Sul</a><br />
<a href="http://www.camaraextrema.mg.gov.br/" target="_blank">Câmara Municipal de Extrema</a><br />
<a href="http://www.cmfama.mg.gov.br" target="_blank">Câmara Municipal de Fama</a><br />
<a href="http://camaradefarialemos.com.br/" target="_blank">Câmara Municipal de Faria Lemos</a><br />
<a href="http://www.ferros.cam.mg.gov.br/" target="_blank">Câmara Municipal de Ferros</a><br />
<a href="http://www.fervedouro.mg.leg.br/" target="_blank">Câmara Municipal de Fervedouro</a><br />
<a href="http://www.florestal.mg.leg.br/" target="_blank">Câmara Municipal de Florestal</a><br />
<a href="http://www.camaraformiga.mg.gov.br/" target="_blank">Câmara Municipal de Formiga</a><br />
<a href="http://www.formoso.mg.leg.br/" target="_blank">Câmara Municipal de Formoso</a><br />
<a href="http://www.camarafortalezademinas.mg.gov.br/" target="_blank">Câmara Municipal de Fortaleza de Minas</a><br />
<a href="http://www.cmfortunademinas.mg.gov.br/" target="_blank">Câmara Municipal de Fortuna de Minas</a><br />
<a href="http://www.camarafronteira.mg.gov.br" target="_blank">Câmara Municipal de Fronteira</a><br />
<a href="http://www.camarafrutal.mg.gov.br/" target="_blank">Câmara Municipal de Frutal</a><br />
<a href="http://www.galileia.cam.mg.gov.br/" target="_blank">Câmara Municipal de Galileia</a><br />
<a href="http://www.camaragoncalves.mg.gov.br/" target="_blank">Câmara Municipal de Gonçalves</a><br />
<a href="http://www.camaragv.mg.gov.br/" target="_blank">Câmara Municipal de Governador Valadares</a><br />
<a href="http://www.cmgm.mg.gov.br/" target="_blank">Câmara Municipal de Grão Mogol</a><br />
<a href="http://www.camaradeguanhaes.mg.gov.br" target="_blank">Câmara Municipal de Guanhães</a><br />
<a href="http://www.camaraguaranesia.mg.gov.br/" target="_blank">Câmara Municipal de Guaranésia</a><br />
<a href="http://www.cmguarani.mg.gov.br/" target="_blank">Câmara Municipal de Guarani</a><br />
<a href="http://www.camaraguardamor.mg.gov.br/" target="_blank">Câmara Municipal de Guarda-Mor</a><br />
<a href="http://camaraguaxupe.mg.gov.br/" target="_blank">Câmara Municipal de Guaxupé</a><br />
<a href="http://www.guimarania.mg.leg.br/" target="_blank">Câmara Municipal de Guimarânia</a><br />
<a href="http://www.cmheliodora.mg.gov.br/" target="_blank">Câmara Municipal de Heliodora</a><br />
<a href="http://www.ibia.mg.leg.br/" target="_blank">Câmara Municipal de Ibiá</a><br />
<a href="http://www.camaraibiraci.mg.gov.br/" target="_blank">Câmara Municipal de Ibiraci</a><br />
<a href="http://www.camaraibirite.mg.gov.br/" target="_blank">Câmara Municipal de Ibirité</a><br />
<a href="http://www.cmigarape.mg.gov.br/" target="_blank">Câmara Municipal de Igarapé</a><br />
<a href="http://www.camaraigaratinga.mg.gov.br/" target="_blank">Câmara Municipal de Igaratinga</a><br />
<a href="http://www.cyberbalada.com/iguatama/" target="_blank">Câmara Municipal de Iguatama</a><br />
<a href="http://www.camarainconfidentes.mg.gov.br" target="_blank">Câmara Municipal de Inconfidentes</a><br />
<a href="http://www.indaiabira.mg.leg.br/" target="_blank">Câmara Municipal de Indaiabira</a><br />
<a href="http://camaraindianopolis.mg.gov.br/" target="_blank">Câmara Municipal de Indianópolis</a><br />
<a href="http://www.cminimutaba.com.br/" target="_blank">Câmara Municipal de Inimutaba</a><br />
<a href="http://www.camaraipanema.mg.gov.br" target="_blank">Câmara Municipal de Ipanema</a><br />
<a href="http://www.camaraipatinga.mg.gov.br" target="_blank">Câmara Municipal de Ipatinga</a><br />
<a href="http://www.camaraipiacu.mg.gov.br/" target="_blank">Câmara Municipal de Ipiaçu</a><br />
<a href="http://www.iraideminas.cam.mg.gov.br/" target="_blank">Câmara Municipal de Iraí de Minas</a><br />
<a href="http://www.itabira.cam.mg.gov.br" target="_blank">Câmara Municipal de Itabira</a><br />
<a href="http://www.itabirito.cam.mg.gov.br/" target="_blank">Câmara Municipal de Itabirito</a><br />
<a href="http://camaraitaguara.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Itaguara</a><br />
<a href="http://www.itajuba.cam.mg.gov.br" target="_blank">Câmara Municipal de Itajubá</a><br />
<a href="http://www.itamogi.mg.leg.br/" target="_blank">Câmara Municipal de Itamogi</a><br />
<a href="http://www.camaramunicipaldeitamonte.net/" target="_blank">Câmara Municipal de Itamonte</a><br />
<a href="http://www.itanhandu.cam.mg.gov.br/" target="_blank">Câmara Municipal de Itanhandu</a><br />
<a href="http://www.cmitanhomi.com.br" target="_blank">Câmara Municipal de Itanhomi</a><br />
<a href="http://www.sitesrm.com.br/cmitaobim.mg.gov.br" target="_blank">Câmara Municipal de Itaobim</a><br />
<a href="http://www.cmitapagipe.mg.gov.br" target="_blank">Câmara Municipal de Itapagipe</a><br />
<a href="http://www.itapecerica.cam.mg.gov.br" target="_blank">Câmara Municipal de Itapecerica</a><br />
<a href="http://www.camaraitapeva.mg.gov.br" target="_blank">Câmara Municipal de Itapeva</a><br />
<a href="http://www.camaraitaudeminas.mg.gov.br/" target="_blank">Câmara Municipal de Itaú de Minas</a><br />
<a href="http://www.cmitauna.mg.gov.br" target="_blank">Câmara Municipal de Itaúna</a><br />
<a href="http://www.ituiutaba.mg.leg.br/" target="_blank">Câmara Municipal de Ituiutaba</a><br />
<a href="http://www.camaraiturama.com.br/" target="_blank">Câmara Municipal de Iturama</a><br />
<a href="http://www.cmjaboticatubas.mg.gov.br/" target="_blank">Câmara Municipal de Jaboticatubas</a><br />
<a href="http://camarajacinto.mg.gov.br/" target="_blank">Câmara Municipal de Jacinto</a><br />
<a href="http://www.jacui.mg.leg.br/" target="_blank">Câmara Municipal de Jacuí</a><br />
<a href="http://www.camarajacutinga.mg.gov.br/" target="_blank">Câmara Municipal de Jacutinga</a><br />
<a href="http://www.camarajaguaracu.com/" target="_blank">Câmara Municipal de Jaguaraçu</a><br />
<a href="http://www.jaiba.mg.leg.br/" target="_blank">Câmara Municipal de Jaíba</a><br />
<a href="http://www.jampruca.cam.mg.gov.br/" target="_blank">Câmara Municipal de Jampruca</a><br />
<a href="http://www.janauba.mg.leg.br/" target="_blank">Câmara Municipal de Janaúba</a><br />
<a href="http://www.camarajanuaria.mg.gov.br/" target="_blank">Câmara Municipal de Januária</a><br />
<a href="http://www.jequitinhonha.mg.leg.br/" target="_blank">Câmara Municipal de Jequitinhonha</a><br />
<a href="http://www.camarajesuania.mg.gov.br/" target="_blank">Câmara Municipal de Jesuânia</a><br />
<a href="http://www.joaima.mg.leg.br/" target="_blank">Câmara Municipal de Joaíma</a><br />
<a href="http://www.joaquimfelicio.mg.leg.br/" target="_blank">Câmara Municipal de Joaquim Felício</a><br />
<a href="http://www.camarajm.mg.gov.br" target="_blank">Câmara Municipal de João Monlevade</a><br />
<a href="http://www.joaopinheiro.mg.leg.br/" target="_blank">Câmara Municipal de João Pinheiro</a><br />
<a href="http://www.jordania.mg.leg.br/portal/" target="_blank">Câmara Municipal de Jordânia</a><br />
<a href="http://www.cmjuatuba.mg.gov.br/" target="_blank">Câmara Municipal de Juatuba</a><br />
<a href="http://isal.camarajf.mg.gov.br" target="_blank">Câmara Municipal de Juiz de Fora</a><br />
<a href="http://www.juruaia.cam.mg.gov.br/" target="_blank">Câmara Municipal de Juruaia</a><br />
<a href="http://www.juvenilia.net.br/" target="_blank">Câmara Municipal de Juvenília</a><br />
<a href="http://www.lagamar.mg.leg.br/" target="_blank">Câmara Municipal de Lagamar</a><br />
<a href="http://www.camaralp.mg.gov.br" target="_blank">Câmara Municipal de Lagoa da Prata</a><br />
<a href="http://www.camaralagoa.mg.gov.br" target="_blank">Câmara Municipal de Lagoa Formosa</a><br />
<a href="http://www.cmlagoasanta.mg.gov.br" target="_blank">Câmara Municipal de Lagoa Santa</a><br />
<a href="http://www.cmlajinha.mg.gov.br" target="_blank">Câmara Municipal de Lajinha</a><br />
<a href="http://www.camaralambari.mg.gov.br/" target="_blank">Câmara Municipal de Lambari</a><br />
<a href="http://www.camaradelassance.mg.gov.br/" target="_blank">Câmara Municipal de Lassance</a><br />
<a href="http://www.camaralavras.mg.gov.br/" target="_blank">Câmara Municipal de Lavras</a><br />
<a href="http://www.camaradeleopoldina.mg.gov.br" target="_blank">Câmara Municipal de Leopoldina</a><br />
<a href="http://camaraliberdade.mg.gov.br/site/" target="_blank">Câmara Municipal de Liberdade</a><br />
<a href="http://www.camarald.mg.gov.br" target="_blank">Câmara Municipal de Lima Duarte</a><br />
<a href="http://www.limeiradooeste.mg.leg.br/" target="_blank">Câmara Municipal de Limeira do Oeste</a><br />
<a href="http://www.luislandia.mg.leg.br/" target="_blank">Câmara Municipal de Luislândia</a><br />
<a href="http://www.luminarias.cam.mg.gov.br/" target="_blank">Câmara Municipal de Luminárias</a><br />
<a href="http://www.camaramunicipaldeluz.mg.gov.br" target="_blank">Câmara Municipal de Luz</a><br />
<a href="http://www.camaramachacalis.mg.gov.br/" target="_blank">Câmara Municipal de Machacalis</a><br />
<a href="http://www.camaramachado.mg.gov.br/" target="_blank">Câmara Municipal de Machado</a><br />
<a href="http://www.mamonas.mg.leg.br/" target="_blank">Câmara Municipal de Mamonas</a><br />
<a href="http://www.camaramanhuacu.com.br/" target="_blank">Câmara Municipal de Manhuaçu</a><br />
<a href="http://www.manhumirim.mg.leg.br/" target="_blank">Câmara Municipal de Manhumirim</a><br />
<a href="http://www.mantena.mg.leg.br/" target="_blank">Câmara Municipal de Mantena</a><br />
<a href="http://www.camarademariadafe.com/" target="_blank">Câmara Municipal de Maria da Fé</a><br />
<a href="http://camarademariana.mg.gov.br" target="_blank">Câmara Municipal de Mariana</a><br />
<a href="http://www.cmmc.mg.gov.br/" target="_blank">Câmara Municipal de Mário Campos</a><br />
<a href="http://www.cmmarmelopolis.mg.gov.br/" target="_blank">Câmara Municipal de Marmelópolis</a><br />
<a href="http://www.camaramcampos.mg.gov.br/" target="_blank">Câmara Municipal de Martinho Campos</a><br />
<a href="http://www.camaramateusleme.mg.gov.br/" target="_blank">Câmara Municipal de Mateus Leme</a><br />
<a href="http://cmmb.mg.gov.br" target="_blank">Câmara Municipal de Matias Barbosa</a><br />
<a href="http://www.camaramatozinhos.mg.gov.br" target="_blank">Câmara Municipal de Matozinhos</a><br />
<a href="http://minasnovas.mg.leg.br/" target="_blank">Câmara Municipal de Minas Novas</a><br />
<a href="http://www.camaramiradouro.mg.gov.br" target="_blank">Câmara Municipal de Miradouro</a><br />
<a href="http://mirai.cam.mg.gov.br/" target="_blank">Câmara Municipal de Miraí</a><br />
<a href="http://www.camarademoeda.com.br" target="_blank">Câmara Municipal de Moeda</a><br />
<a href="http://camaramoema.mg.gov.br/" target="_blank">Câmara Municipal de Moema</a><br />
<a href="http://www.cmmonjolos.mg.gov.br/" target="_blank">Câmara Municipal de Monjolos</a><br />
<a href="http://www.monsenhorpaulo.cam.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Monsenhor Paulo</a><br />
<a href="http://camaramontalvania.mg.gov.br/" target="_blank">Câmara Municipal de Montalvânia</a><br />
<a href="http://www.montealegredeminas.cam.mg.gov.br" target="_blank">Câmara Municipal de Monte Alegre de Minas</a><br />
<a href="http://www.camaramunicipaldemonteazul.mg.gov.br/" target="_blank">Câmara Municipal de Monte Azul</a><br />
<a href="http://www.camaramontebelo.mg.gov.br" target="_blank">Câmara Municipal de Monte Belo</a><br />
<a href="http://www.camaramontecarmelo.mg.gov.br" target="_blank">Câmara Municipal de Monte Carmelo</a><br />
<a href="http://www.montesantodeminas.mg.leg.br/" target="_blank">Câmara Municipal de Monte Santo de Minas</a><br />
<a href="http://www.camaramontesiao.com.br" target="_blank">Câmara Municipal de Monte Sião</a><br />
<a href="http://www.cmmoc.mg.gov.br/" target="_blank">Câmara Municipal de Montes Claros</a><br />
<a href="http://www.camaraemacao.mg.gov.br" target="_blank">Câmara Municipal de Morada Nova de Minas</a><br />
<a href="http://www.morrodagarca.cam.mg.gov.br/" target="_blank">Câmara Municipal de Morro da Garça</a><br />
<a href="http://www.camaramuriae.mg.gov.br" target="_blank">Câmara Municipal de Muriaé</a><br />
<a href="http://www.camaramutum.mg.gov.br/" target="_blank">Câmara Municipal de Mutum</a><br />
<a href="http://www.camaramuzambinho.mg.gov.br/" target="_blank">Câmara Municipal de Muzambinho</a><br />
<a href="http://www.camarananuque.com.br" target="_blank">Câmara Municipal de Nanuque</a><br />
<a href="http://www.camaranatalandia.mg.gov.br/" target="_blank">Câmara Municipal de Natalândia</a><br />
<a href="http://www.cmnatercia.mg.gov.br" target="_blank">Câmara Municipal de Natércia</a><br />
<a href="http://www.camaranepomuceno.com.br/" target="_blank">Câmara Municipal de Nepomuceno</a><br />
<a href="http://www.cmne.mg.gov.br" target="_blank">Câmara Municipal de Nova Era</a><br />
<a href="http://www.cmnovalima.mg.gov.br/" target="_blank">Câmara Municipal de Nova Lima</a><br />
<a href="http://www.novaserrana.cam.mg.gov.br" target="_blank">Câmara Municipal de Nova Serrana</a><br />
<a href="http://camara.olimpionoronha.mg.gov.br/" target="_blank">Câmara Municipal de Olímpio Noronha</a><br />
<a href="http://www.oliveira.cam.mg.gov.br/" target="_blank">Câmara Municipal de Oliveira</a><br />
<a href="http://camaraoratorios.mg.gov.br/" target="_blank">Câmara Municipal de Oratórios</a><br />
<a href="http://www.ourobranco.cam.mg.gov.br" target="_blank">Câmara Municipal de Ouro Branco</a><br />
<a href="http://www.camaraourofino.mg.gov.br/" target="_blank">Câmara Municipal de Ouro Fino</a><br />
<a href="http://www.cmop.mg.gov.br" target="_blank">Câmara Municipal de Ouro Preto</a><br />
<a href="http://paineiras.cam.mg.gov.br/" target="_blank">Câmara Municipal de Paineiras</a><br />
<a href="http://www.camarapains.mg.gov.br" target="_blank">Câmara Municipal de Pains</a><br />
<a href="http://www.camarapm.mg.gov.br/" target="_blank">Câmara Municipal de Pará de Minas</a><br />
<a href="http://www.camaraptu.mg.gov.br/" target="_blank">Câmara Municipal de Paracatu</a><br />
<a href="http://www.camaradeparaguacu.mg.gov.br" target="_blank">Câmara Municipal de Paraguaçu</a><br />
<a href="http://www.paraopeba.cam.mg.gov.br/" target="_blank">Câmara Municipal de Paraopeba</a><br />
<a href="http://www.cmpassaquatro.mg.gov.br/" target="_blank">Câmara Municipal de Passa Quatro</a><br />
<a href="http://www.camarapassatempo.mg.gov.br/" target="_blank">Câmara Municipal de Passa Tempo</a><br />
<a href="http://www.camarapassos.mg.gov.br" target="_blank">Câmara Municipal de Passos</a><br />
<a href="http://www.camarapatos.mg.gov.br" target="_blank">Câmara Municipal de Patos de Minas</a><br />
<a href="http://cmpatrocinio.mg.gov.br" target="_blank">Câmara Municipal de Patrocínio</a><br />
<a href="http://www.pecanha.mg.leg.br/principal.asp" target="_blank">Câmara Municipal de Peçanha</a><br />
<a href="http://pedraazul.mg.leg.br/" target="_blank">Câmara Municipal de Pedra Azul</a><br />
<a href="http://camarapb.blogspot.com.br/" target="_blank">Câmara Municipal de Pedra Bonita</a><br />
<a href="http://www.camarapedraindaia.com.br/" target="_blank">Câmara Municipal de Pedra do Indaiá</a><br />
<a href="http://camarapd.mg.gov.br/" target="_blank">Câmara Municipal de Pedra Dourada</a><br />
<a href="http://www.pedralva.cam.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de Pedralva</a><br />
<a href="http://www.pedrinopolis.mg.leg.br/" target="_blank">Câmara Municipal de Pedrinópolis</a><br />
<a href="http://www.camarapl.mg.gov.br" target="_blank">Câmara Municipal de Pedro Leopoldo</a><br />
<a href="http://www.pedroteixeira.cam.mg.gov.br/" target="_blank">Câmara Municipal de Pedro Teixeira</a><br />
<a href="http://www.camarapequi.mg.gov.br/" target="_blank">Câmara Municipal de Pequi</a><br />
<a href="http://www.camaraperdizes.com.br/" target="_blank">Câmara Municipal de Perdizes</a><br />
<a href="http://www.pescador.cam.mg.gov.br/" target="_blank">Câmara Municipal de Pescador</a><br />
<a href="http://piau.cam.mg.gov.br/" target="_blank">Câmara Municipal de Piau</a><br />
<a href="http://www.camarapiracema.mg.gov.br/" target="_blank">Câmara Municipal de Piracema</a><br />
<a href="http://www.cmpirangucu.com.br/" target="_blank">Câmara Municipal de Piranguçu</a><br />
<a href="http://www.camaradepiranguinho.com.br/" target="_blank">Câmara Municipal de Piranguinho</a><br />
<a href="http://www.pirapetinga.mg.leg.br/" target="_blank">Câmara Municipal de Pirapetinga</a><br />
<a href="http://www.camaradepirapora.mg.gov.br" target="_blank">Câmara Municipal de Pirapora</a><br />
<a href="http://www.cmpirauba.mg.gov.br/" target="_blank">Câmara Municipal de Piraúba</a><br />
<a href="http://www.camarapiumhi.mg.gov.br" target="_blank">Câmara Municipal de Piumhi</a><br />
<a href="http://www.cmplanura.mg.gov.br" target="_blank">Câmara Municipal de Planura</a><br />
<a href="http://www.camarapocos.mg.gov.br" target="_blank">Câmara Municipal de Poços de Caldas</a><br />
<a href="http://camaramunicipaldepompeu.mg.gov.br/" target="_blank">Câmara Municipal de Pompéu</a><br />
<a href="http://www.pontenova.mg.leg.br/" target="_blank">Câmara Municipal de Ponte Nova</a><br />
<a href="http://www.camarapv.com.br/" target="_blank">Câmara Municipal de Ponto dos Volantes</a><br />
<a href="http://www.cmpa.mg.gov.br" target="_blank">Câmara Municipal de Pouso Alegre</a><br />
<a href="http://www.pousoalto.mg.leg.br/" target="_blank">Câmara Municipal de Pouso Alto</a><br />
<a href="http://www.prados.cam.mg.gov.br/site/" target="_blank">Câmara Municipal de Prados</a><br />
<a href="http://www.camaraprata.mg.gov.br/" target="_blank">Câmara Municipal de Prata</a><br />
<a href="http://www.cmpo.mg.gov.br" target="_blank">Câmara Municipal de Presidente Olegário</a><br />
<a href="http://www.cmraposos.com.br" target="_blank">Câmara Municipal de Raposos</a><br />
<a href="http://www.cmraulsoares.mg.gov.br" target="_blank">Câmara Municipal de Raul Soares</a><br />
<a href="http://www.reduto.mg.leg.br/" target="_blank">Câmara Municipal de Reduto</a><br />
<a href="http://www.camaraderesendecosta.mg.gov.br/" target="_blank">Câmara Municipal de Resende Costa</a><br />
<a href="http://www.camaraderessaquinha.mg.gov.br/" target="_blank">Câmara Municipal de Ressaquinha</a><br />
<a href="http://www.cmrn.mg.gov.br" target="_blank">Câmara Municipal de Ribeirão das Neves</a><br />
<a href="http://www.rioacima.mg.leg.br/" target="_blank">Câmara Municipal de Rio Acima</a><br />
<a href="http://www.camarariocasca.mg.gov.br/" target="_blank">Câmara Municipal de Rio Casca</a><br />
<a href="http://www.camararionovo.mg.gov.br" target="_blank">Câmara Municipal de Rio Novo</a><br />
<a href="http://www.camararioparanaiba.mg.gov.br/" target="_blank">Câmara Municipal de Rio Paranaíba</a><br />
<a href="http://camararp.mg.gov.br" target="_blank">Câmara Municipal de Rio Piracicaba</a><br />
<a href="http://www.cmriopomba.mg.gov.br" target="_blank">Câmara Municipal de Rio Pomba<br />
</a><a href="http://www.cmrp.mg.gov.br" target="_blank">Câmara Municipal de Rio Preto</a><br />
<a href="http://www.ritapolis.mg.leg.br/" target="_blank">Câmara Municipal de Ritápolis</a><br />
<a href="http://rodeiro.mg.leg.br/" target="_blank">Câmara Municipal de Rodeiro</a><br />
<a href="http://camararubim.mg.gov.br/" target="_blank">Câmara Municipal de Rubim</a><br />
<a href="http://www.camarasabara.mg.gov.br/" target="_blank">Câmara Municipal de Sabará</a><br />
<a href="http://www.sabinopoliscam.com.br/" target="_blank">Câmara Municipal de Sabinópolis</a><br />
<a href="http://sacramento.cam.mg.gov.br/" target="_blank">Câmara Municipal de Sacramento</a><br />
<a href="http://www.camarasalinas.mg.gov.br/" target="_blank">Câmara Municipal de Salinas</a><br />
<a href="http://www.santabarbara.cam.mg.gov.br/" target="_blank">Câmara Municipal de Santa Bárbara</a><br />
<a href="http://www.cmsbl.com.br/" target="_blank">Câmara Municipal de Santa Bárbara do Leste</a><br />
<a href="http://cmsantabarbaradotugurio.mg.gov.br/" target="_blank">Câmara Municipal de Santa Bárbara do Tugúrio</a><br />
<a href="http://camaramunicipaldesantacruzdeminas.blogspot.com/" target="_blank">Câmara Municipal de Santa Cruz de Minas</a><br />
<a href="http://camarasantaefigeniademinas.com.br/" target="_blank">Câmara Municipal de Santa Efigênia de Minas</a><br />
<a href="http://www.santajuliana.cam.mg.gov.br" target="_blank">Câmara Municipal de Santa Juliana</a><br />
<a href="http://santahelenademinas.mg.leg.br/" target="_blank">Câmara Municipal de Santa Helena de Minas</a><br />
<a href="http://www.cmsantaluzia.mg.gov.br" target="_blank">Câmara Municipal de Santa Luzia</a><br />
<a href="http://camara.santaritadecaldas.mg.gov.br/" target="_blank">Câmara Municipal de Santa Rita de Caldas</a><br />
<a href="http://www.santaritadeibitipoca.cam.mg.gov.br/" target="_blank">Câmara Municipal de Santa Rita de Ibitipoca</a><br />
<a href="http://santaritadejacutinga.mg.leg.br/" target="_blank">Câmara Municipal de Santa Rita de Jacutinga</a><br />
<a href="http://www.cmsantaritademinas.mg.gov.br/" target="_blank">Câmara Municipal de Santa Rita de Minas</a><br />
<a href="http://www.santaritadosapucai.mg.leg.br/" target="_blank">Câmara Municipal de Santa Rita do Sapucaí</a><br />
<a href="http://camarasantarosadaserra.mg.gov.br/" target="_blank">Câmara Municipal de Santa Rosa da Serra</a><br />
<a href="http://www.camarasantavitoria.mg.gov.br/" target="_blank">Câmara Municipal de Santa Vitória</a><br />
<a href="http://www.camarasantana.com.br/" target="_blank">Câmara Municipal de Santana de Cataguases</a><br />
<a href="http://cmsj.mg.gov.br/" target="_blank">Câmara Municipal de Santana do Jacaré</a><br />
<a href="http://camaraparaiso.mg.gov.br/" target="_blank">Câmara Municipal de Santana do Paraíso</a><br />
<a href="http://www.camarasaa.mg.gov.br/" target="_blank">Câmara Municipal de Santo Antônio do Amparo</a><br />
<a href="http://camarasaaventureiro.com.br/" target="_blank">Câmara Municipal de Santo Antônio do Aventureiro</a><br />
<a href="http://cmsantoantoniodograma.mg.gov.br/" target="_blank">Câmara Municipal de Santo Antônio do Grama</a><br />
<a href="http://www.camarasam.mg.gov.br/" target="_blank">Câmara Municipal de Santo Antônio do Monte</a><br />
<a href="http://www.camarasd.mg.gov.br/" target="_blank">Câmara Municipal de Santos Dumont</a><br />
<a href="http://saobentoabade.cam.mg.gov.br/principal.asp" target="_blank">Câmara Municipal de São Bento Abade</a><br />
<a href="http://www.saobrasdosuacui.cam.mg.gov.br/" target="_blank">Câmara Municipal de São Brás do Suaçuí</a><br />
<a href="http://www.camaradoprata.mg.gov.br/" target="_blank">Câmara Municipal de São Domingos do Prata</a><br />
<a href="http://saofelixdeminas.cam.mg.gov.br/" target="_blank">Câmara Municipal de São Félix de Minas</a><br />
<a href="http://www.camarasaofrancisco.mg.gov.br" target="_blank">Câmara Municipal de São Francisco</a><br />
<a href="http://www.camarasaofranciscodepaula.mg.gov.br/site/" target="_blank">Câmara Municipal de São Francisco de Paula</a><br />
<a href="http://camaramunicipalsfs.blogspot.com/" target="_blank">Câmara Municipal de São Francisco de Sales</a><br />
<a href="http://camarasaogoncalodopara.mg.gov.br/" target="_blank">Câmara Municipal de São Gonçalo do Pará</a><br />
<a href="http://www.camarasaogoncalo.mg.gov.br" target="_blank">Câmara Municipal de São Gonçalo do Rio Abaixo</a><br />
<a href="http://www.camarasgs.mg.gov.br/" target="_blank">Câmara Municipal de São Gonçalo do Sapucaí</a><br />
<a href="http://www.camarasaogotardo.mg.gov.br/" target="_blank">Câmara Municipal de São Gotardo</a><br />
<a href="http://www.camarasaojoaodelrei.com.br/" target="_blank">Câmara Municipal de São João del-Rei</a><br />
<a href="http://www.camarasjn.mg.gov.br/" target="_blank">Câmara Municipal de São João Nepomuceno</a><br />
<a href="http://camarasaojoaodamata.mg.gov.br/" target="_blank">Câmara Municipal de São João da Mata</a><br />
<a href="http://www.camarasaojoaquimdebicas.mg.gov.br/" target="_blank">Câmara Municipal de São Joaquim de Bicas</a><br />
<a href="http://camaradesaojosedabarra.webnode.com.br/" target="_blank">Câmara Municipal de São José da Barra</a><br />
<a href="http://www.camarasjl.mg.gov.br" target="_blank">Câmara Municipal de São José da Lapa</a><br />
<a href="http://saojosedavarginha.cam.mg.gov.br/site/" target="_blank">Câmara Municipal de São José da Varginha</a><br />
<a href="http://www.camarasl.mg.gov.br" target="_blank">Câmara Municipal de São Lourenço</a><br />
<a href="http://www.camarassbv.mg.gov.br" target="_blank">Câmara Municipal de São Sebastião da Bela Vista</a><br />
<a href="http://saosebastiaodooeste.cam.mg.gov.br/" target="_blank">Câmara Municipal de São Sebastião do Oeste</a><br />
<a href="http://www.camarassparaiso.mg.gov.br/.web3" target="_blank">Câmara Municipal de São Sebastião do Paraíso</a><br />
<a href="http://www.saosebastiaodorioverde.mg.leg.br/" target="_blank">Câmara Municipal de São Sebastião do Rio Verde</a><br />
<a href="http://camarasaotiago.mg.gov.br/" target="_blank">Câmara Municipal de São Tiago</a><br />
<a href="http://www.saothomedasletras.mg.leg.br/" target="_blank">Câmara Municipal de São Tomé das Letras</a><br />
<a href="http://www.camarasvm.mg.gov.br/" target="_blank">Câmara Municipal de São Vicente de Minas</a><br />
<a href="http://www.camarasapucaimirim.mg.gov.br/" target="_blank">Câmara Municipal de Sapucaí Mirim</a><br />
<a href="http://camarasardoa.mg.gov.br/" target="_blank">Câmara Municipal de Sardoá</a><br />
<a href="http://www.camarasarzedo.mg.gov.br" target="_blank">Câmara Municipal de Sarzedo</a><br />
<a href="http://www.senadorjosebento.mg.leg.br/" target="_blank">Câmara Municipal de Senador José Bento</a><br />
<a href="http://serraazuldeminas.cammg.com.br/" target="_blank">Câmara Municipal de Serra Azul de Minas</a><br />
<a href="http://www.camaraserranos.mg.gov.br/" target="_blank">Câmara Municipal de Serranos</a><br />
<a href="http://www.setelagoas.mg.leg.br/" target="_blank">Câmara Municipal de Sete Lagoas</a><br />
<a href="http://silveirania.cam.mg.gov.br/" target="_blank">Câmara Municipal de Silveirânia</a><br />
<a href="http://www.silvianopolis.mg.leg.br/" target="_blank">Câmara Municipal de Silvianópolis</a><br />
<a href="http://simaopereira.cam.mg.gov.br/" target="_blank">Câmara Municipal de Simão Pereira</a><br />
<a href="http://www.cmsoledadedeminas.com.br/" target="_blank">Câmara Municipal de Soledade de Minas</a><br />
<a href="http://www.taiobeiras.cam.mg.gov.br/" target="_blank">Câmara Municipal de Taiobeiras</a><br />
<a href="http://www.camarataparuba.mg.gov.br/" target="_blank">Câmara Municipal de Taparuba</a><br />
<a href="http://www.camaratapira.mg.gov.br/" target="_blank">Câmara Municipal de Tapira</a><br />
<a href="http://www.camaramunicipaldeteixeiras.org/" target="_blank">Câmara Municipal de Teixeiras</a><br />
<a href="http://www.cmto.mg.gov.br/" target="_blank">Câmara Municipal de Teófilo Otoni</a><br />
<a href="http://www.timoteo.cam.mg.gov.br/" target="_blank">Câmara Municipal de Timóteo</a><br />
<a href="http://www.camaratiradentes.mg.gov.br/" target="_blank">Câmara Municipal de Tiradentes</a><br />
<a href="http://www.cmtocantins.mg.gov.br/" target="_blank">Câmara Municipal de Tocantins</a><br />
<a href="http://www.tocosdomoji.mg.leg.br/" target="_blank">Câmara Municipal de Tocos do Moji</a><br />
<a href="http://www.camaratombos.mg.gov.br/" target="_blank">Câmara Municipal de Tombos</a><br />
<a href="http://www.camaratc.mg.gov.br/" target="_blank">Câmara Municipal de Três Corações</a><br />
<a href="http://www.tresmarias.cam.mg.gov.br/" target="_blank">Câmara Municipal de Três Marias</a><br />
<a href="http://www.camaratrespontas.mg.gov.br/" target="_blank">Câmara Municipal de Três Pontas</a><br />
<a href="http://www.tumiritinga.mg.leg.br/" target="_blank">Câmara Municipal de Tumiritinga</a><br />
<a href="http://www.camaratupaciguara.mg.gov.br" target="_blank">Câmara Municipal de Tupaciguara</a><br />
<a href="http://camaramunicipaldeturmalina-mg.blogspot.com/" target="_blank">Câmara Municipal de Turmalina</a><br />
<a href="http://camaraturvolandia.mg.gov.br/" target="_blank">Câmara Municipal de Turvolândia</a><br />
<a href="http://www.camarauba.mg.gov.br/" target="_blank">Câmara Municipal de Ubá</a><br />
<a href="http://www.cmubaporanga.mg.gov.br/" target="_blank">Câmara Municipal de Ubaporanga</a><br />
<a href="http://www.camarauberaba.mg.gov.br/" target="_blank">Câmara Municipal de Uberaba</a><br />
<a href="http://www.camarauberlandia.mg.gov.br/" target="_blank">Câmara Municipal de Uberlândia</a><br />
<a href="http://www.camaraunai.mg.gov.br/" target="_blank">Câmara Municipal de Unaí</a><br />
<a href="http://www.camarauniaodeminas.com.br/" target="_blank">Câmara Municipal de União de Minas</a><br />
<a href="http://www.camarauruana.mg.gov.br/" target="_blank">Câmara Municipal de Uruana de Minas</a><br />
<a href="http://camaravargembonita.mg.gov.br/" target="_blank">Câmara Municipal de Vargem Bonita</a><br />
<a href="http://www.camaravarginha.mg.gov.br" target="_blank">Câmara Municipal de Varginha</a><br />
<a href="http://www.varjaodeminas.mg.leg.br/" target="_blank">Câmara Municipal de Varjão de Minas</a><br />
<a href="http://www.camaradevarzeadapalma.mg.gov.br" target="_blank">Câmara Municipal de Várzea da Palma</a><br />
<a href="http://www.camaravarzelandia.mg.gov.br/" target="_blank">Câmara Municipal de Varzelândia</a><br />
<a href="http://www.camaravazante.mg.gov.br/" target="_blank">Câmara Municipal de Vazante</a><br />
<a href="http://www.camaraverissimo.mg.gov.br/index.htm" target="_blank">Câmara Municipal de Veríssimo</a><br />
<a href="http://www.vermelhonovo.cam.mg.gov.br/" target="_blank">Câmara Municipal de Vermelho Novo</a><br />
<a href="http://www.camaravespasiano.mg.gov.br/" target="_blank">Câmara Municipal de Vespasiano</a><br />
<a href="http://www.vicosa.mg.leg.br/" target="_blank">Câmara Municipal de Viçosa</a><br />
<a href="http://www.camaravgp.mg.gov.br/" target="_blank">Câmara Municipal de Virginópolis</a><br />
<a href="http://www.camaravirgolandia.mg.gov.br/site/" target="_blank">Câmara Municipal de Virgolândia</a><br />
<a href="http://www.camaravrb.mg.gov.br/" target="_blank">Câmara Municipal de Visconde do Rio Branco</a><br />
<a href="http://www.voltagrande.cam.mg.gov.br/" target="_blank">Câmara Municipal de Volta Grande</a></p>
"""

soup = BeautifulSoup(html, 'html.parser')

for link in soup.find_all('a'):
    print(link.text)

```

    Câmara Municipal de Aimorés
    Câmara Municipal de Aiuruoca
    Câmara Municipal de Albertina
    Câmara Municipal de Além Paraíba
    Câmara Municipal de Alfenas
    Câmara Municipal de Alfredo Vasconcelos
    Câmara Municipal de Almenara
    Câmara Municipal de Alterosa
    Câmara Municipal de Alto Caparaó
    Câmara Municipal de Alto Jequitibá
    Câmara Municipal de Alvarenga
    Câmara Municipal de Andradas
    Câmara Municipal de Andrelândia
    Câmara Municipal de Antônio Carlos
    Câmara Municipal de Araguari
    Câmara Municipal de Araporã
    Câmara Municipal de Araxá
    Câmara Municipal de Arceburgo
    Câmara Municipal de Arcos
    Câmara Municipal de Areado
    Câmara Municipal de Arinos
    Câmara Municipal de Ataleia
    Câmara Municipal de Baependi
    Câmara Municipal de Bambuí
    Câmara Municipal de Barão de Cocais
    Câmara Municipal de Barbacena
    Câmara Municipal de Barroso
    Câmara Municipal de Bela Vista de Minas
    Câmara Municipal de Belo Horizonte
    Câmara Municipal de Belo Vale
    Câmara Municipal de Bertópolis
    Câmara Municipal de Betim
    Câmara Municipal de Bicas
    Câmara Municipal de Boa Esperança
    Câmara Municipal de Bocaina de Minas
    Câmara Municipal de Bocaiúva
    Câmara Municipal de Bom Despacho
    Câmara Municipal de Bom Jardim de Minas
    Câmara Municipal de Bom Jesus da Penha
    Câmara Municipal de Bom Jesus do Amparo
    Câmara Municipal de Bonfinópolis de Minas
    Câmara Municipal de Botelhos
    Câmara Municipal de Brasilândia de Minas
    Câmara Municipal de Brasília de Minas
    Câmara Municipal de Brazópolis
    Câmara Municipal de Brumadinho
    Câmara Municipal de Buritis
    Câmara Municipal de Buritizeiro
    Câmara Municipal de Cabeceira Grande
    Câmara Municipal de Cachoeira de Minas
    Câmara Municipal de Caeté
    Câmara Municipal de Caiana
    Câmara Municipal de Caldas
    Câmara Municipal de Camacho
    Câmara Municipal de Camanducaia
    Câmara Municipal de Cambuí
    Câmara Municipal de Cambuquira
    Câmara Municipal de Campanário
    Câmara Municipal de Campanha
    Câmara Municipal de Campina Verde
    Câmara Municipal de Campo Belo
    Câmara Municipal de Campo do Meio
    Câmara Municipal de Campos Altos
    Câmara Municipal de Campos Gerais
    Câmara Municipal de Canápolis
    Câmara Municipal de Capelinha
    Câmara Municipal de Capetinga
    Câmara Municipal de Capitão Andrade
    Câmara Municipal de Capim Branco
    Câmara Municipal de Capinópolis
    Câmara Municipal de Caputira
    Câmara Municipal de Carandaí
    Câmara Municipal de Carangola
    Câmara Municipal de Caratinga
    Câmara Municipal de Carbonita
    Câmara Municipal de Careaçu
    Câmara Municipal de Carmésia
    Câmara Municipal de Carmo da Cachoeira
    Câmara Municipal de Carmo da Mata
    Câmara Municipal de Carmo de Minas
    Câmara Municipal de Carmo do Cajuru
    Câmara Municipal de Carmo do Paranaíba
    Câmara Municipal de Carmo do Rio Claro
    Câmara Municipal de Carmópolis de Minas
    Câmara Municipal de Carneirinho
    Câmara Municipal de Carrancas
    Câmara Municipal de Carvalhópolis
    Câmara Municipal de Casa Grande
    Câmara Municipal de Cássia
    Câmara Municipal de Cataguases
    Câmara Municipal de Caxambu
    Câmara Municipal de Chalé
    Câmara Municipal de Claraval
    Câmara Municipal de Cláudio
    Câmara Municipal de Conceição das Alagoas
    Câmara Municipal de Conceição de Ipanema
    Câmara Municipal de Conceição do Pará
    Câmara Municipal de Conceição dos Ouros
    Câmara Municipal de Confins
    Câmara Municipal de Congonhal
    Câmara Municipal de Congonhas
    Câmara Municipal de Conquista
    Câmara Municipal de Conselheiro Lafaiete
    Câmara Municipal de Conselheiro Pena
    Câmara Municipal de Consolação
    Câmara Municipal de Contagem
    Câmara Municipal de Cordislândia
    Câmara Municipal de Coromandel
    Câmara Municipal de Coronel Fabriciano
    Câmara Municipal de Coronel Pacheco
    Câmara Municipal de Coronel Xavier Chaves
    Câmara Municipal de Córrego Danta
    Câmara Municipal de Córrego do Bom Jesus
    Câmara Municipal de Couto de Magalhães de Minas
    Câmara Municipal de Cristiano Otoni
    Câmara Municipal de Crisólita
    Câmara Municipal de Cristina
    Câmara Municipal de Cruzília
    Câmara Municipal de Curvelo
    Câmara Municipal de Delfinópolis
    Câmara Municipal de Delta
    Câmara Municipal de Descoberto
    Câmara Municipal de Diamantina
    Câmara Municipal de Dionísio
    Câmara Municipal de Divinolândia de Minas
    Câmara Municipal de Divinópolis
    Câmara Municipal de Dom Bosco
    Câmara Municipal de Dom Silvério
    Câmara Municipal de Dona Euzébia
    Câmara Municipal de Dores de Campos
    Câmara Municipal de Dores do Indaiá
    Câmara Municipal de Entre Rios de Minas
    Câmara Municipal de Ervália
    Câmara Municipal de Esmeraldas
    Câmara Municipal de Espera Feliz
    Câmara Municipal de Estiva
    Câmara Municipal de Estrela do Indaiá
    Câmara Municipal de Estrela do Sul
    Câmara Municipal de Extrema
    Câmara Municipal de Fama
    Câmara Municipal de Faria Lemos
    Câmara Municipal de Ferros
    Câmara Municipal de Fervedouro
    Câmara Municipal de Florestal
    Câmara Municipal de Formiga
    Câmara Municipal de Formoso
    Câmara Municipal de Fortaleza de Minas
    Câmara Municipal de Fortuna de Minas
    Câmara Municipal de Fronteira
    Câmara Municipal de Frutal
    Câmara Municipal de Galileia
    Câmara Municipal de Gonçalves
    Câmara Municipal de Governador Valadares
    Câmara Municipal de Grão Mogol
    Câmara Municipal de Guanhães
    Câmara Municipal de Guaranésia
    Câmara Municipal de Guarani
    Câmara Municipal de Guarda-Mor
    Câmara Municipal de Guaxupé
    Câmara Municipal de Guimarânia
    Câmara Municipal de Heliodora
    Câmara Municipal de Ibiá
    Câmara Municipal de Ibiraci
    Câmara Municipal de Ibirité
    Câmara Municipal de Igarapé
    Câmara Municipal de Igaratinga
    Câmara Municipal de Iguatama
    Câmara Municipal de Inconfidentes
    Câmara Municipal de Indaiabira
    Câmara Municipal de Indianópolis
    Câmara Municipal de Inimutaba
    Câmara Municipal de Ipanema
    Câmara Municipal de Ipatinga
    Câmara Municipal de Ipiaçu
    Câmara Municipal de Iraí de Minas
    Câmara Municipal de Itabira
    Câmara Municipal de Itabirito
    Câmara Municipal de Itaguara
    Câmara Municipal de Itajubá
    Câmara Municipal de Itamogi
    Câmara Municipal de Itamonte
    Câmara Municipal de Itanhandu
    Câmara Municipal de Itanhomi
    Câmara Municipal de Itaobim
    Câmara Municipal de Itapagipe
    Câmara Municipal de Itapecerica
    Câmara Municipal de Itapeva
    Câmara Municipal de Itaú de Minas
    Câmara Municipal de Itaúna
    Câmara Municipal de Ituiutaba
    Câmara Municipal de Iturama
    Câmara Municipal de Jaboticatubas
    Câmara Municipal de Jacinto
    Câmara Municipal de Jacuí
    Câmara Municipal de Jacutinga
    Câmara Municipal de Jaguaraçu
    Câmara Municipal de Jaíba
    Câmara Municipal de Jampruca
    Câmara Municipal de Janaúba
    Câmara Municipal de Januária
    Câmara Municipal de Jequitinhonha
    Câmara Municipal de Jesuânia
    Câmara Municipal de Joaíma
    Câmara Municipal de Joaquim Felício
    Câmara Municipal de João Monlevade
    Câmara Municipal de João Pinheiro
    Câmara Municipal de Jordânia
    Câmara Municipal de Juatuba
    Câmara Municipal de Juiz de Fora
    Câmara Municipal de Juruaia
    Câmara Municipal de Juvenília
    Câmara Municipal de Lagamar
    Câmara Municipal de Lagoa da Prata
    Câmara Municipal de Lagoa Formosa
    Câmara Municipal de Lagoa Santa
    Câmara Municipal de Lajinha
    Câmara Municipal de Lambari
    Câmara Municipal de Lassance
    Câmara Municipal de Lavras
    Câmara Municipal de Leopoldina
    Câmara Municipal de Liberdade
    Câmara Municipal de Lima Duarte
    Câmara Municipal de Limeira do Oeste
    Câmara Municipal de Luislândia
    Câmara Municipal de Luminárias
    Câmara Municipal de Luz
    Câmara Municipal de Machacalis
    Câmara Municipal de Machado
    Câmara Municipal de Mamonas
    Câmara Municipal de Manhuaçu
    Câmara Municipal de Manhumirim
    Câmara Municipal de Mantena
    Câmara Municipal de Maria da Fé
    Câmara Municipal de Mariana
    Câmara Municipal de Mário Campos
    Câmara Municipal de Marmelópolis
    Câmara Municipal de Martinho Campos
    Câmara Municipal de Mateus Leme
    Câmara Municipal de Matias Barbosa
    Câmara Municipal de Matozinhos
    Câmara Municipal de Minas Novas
    Câmara Municipal de Miradouro
    Câmara Municipal de Miraí
    Câmara Municipal de Moeda
    Câmara Municipal de Moema
    Câmara Municipal de Monjolos
    Câmara Municipal de Monsenhor Paulo
    Câmara Municipal de Montalvânia
    Câmara Municipal de Monte Alegre de Minas
    Câmara Municipal de Monte Azul
    Câmara Municipal de Monte Belo
    Câmara Municipal de Monte Carmelo
    Câmara Municipal de Monte Santo de Minas
    Câmara Municipal de Monte Sião
    Câmara Municipal de Montes Claros
    Câmara Municipal de Morada Nova de Minas
    Câmara Municipal de Morro da Garça
    Câmara Municipal de Muriaé
    Câmara Municipal de Mutum
    Câmara Municipal de Muzambinho
    Câmara Municipal de Nanuque
    Câmara Municipal de Natalândia
    Câmara Municipal de Natércia
    Câmara Municipal de Nepomuceno
    Câmara Municipal de Nova Era
    Câmara Municipal de Nova Lima
    Câmara Municipal de Nova Serrana
    Câmara Municipal de Olímpio Noronha
    Câmara Municipal de Oliveira
    Câmara Municipal de Oratórios
    Câmara Municipal de Ouro Branco
    Câmara Municipal de Ouro Fino
    Câmara Municipal de Ouro Preto
    Câmara Municipal de Paineiras
    Câmara Municipal de Pains
    Câmara Municipal de Pará de Minas
    Câmara Municipal de Paracatu
    Câmara Municipal de Paraguaçu
    Câmara Municipal de Paraopeba
    Câmara Municipal de Passa Quatro
    Câmara Municipal de Passa Tempo
    Câmara Municipal de Passos
    Câmara Municipal de Patos de Minas
    Câmara Municipal de Patrocínio
    Câmara Municipal de Peçanha
    Câmara Municipal de Pedra Azul
    Câmara Municipal de Pedra Bonita
    Câmara Municipal de Pedra do Indaiá
    Câmara Municipal de Pedra Dourada
    Câmara Municipal de Pedralva
    Câmara Municipal de Pedrinópolis
    Câmara Municipal de Pedro Leopoldo
    Câmara Municipal de Pedro Teixeira
    Câmara Municipal de Pequi
    Câmara Municipal de Perdizes
    Câmara Municipal de Pescador
    Câmara Municipal de Piau
    Câmara Municipal de Piracema
    Câmara Municipal de Piranguçu
    Câmara Municipal de Piranguinho
    Câmara Municipal de Pirapetinga
    Câmara Municipal de Pirapora
    Câmara Municipal de Piraúba
    Câmara Municipal de Piumhi
    Câmara Municipal de Planura
    Câmara Municipal de Poços de Caldas
    Câmara Municipal de Pompéu
    Câmara Municipal de Ponte Nova
    Câmara Municipal de Ponto dos Volantes
    Câmara Municipal de Pouso Alegre
    Câmara Municipal de Pouso Alto
    Câmara Municipal de Prados
    Câmara Municipal de Prata
    Câmara Municipal de Presidente Olegário
    Câmara Municipal de Raposos
    Câmara Municipal de Raul Soares
    Câmara Municipal de Reduto
    Câmara Municipal de Resende Costa
    Câmara Municipal de Ressaquinha
    Câmara Municipal de Ribeirão das Neves
    Câmara Municipal de Rio Acima
    Câmara Municipal de Rio Casca
    Câmara Municipal de Rio Novo
    Câmara Municipal de Rio Paranaíba
    Câmara Municipal de Rio Piracicaba
    Câmara Municipal de Rio Pomba
    
    Câmara Municipal de Rio Preto
    Câmara Municipal de Ritápolis
    Câmara Municipal de Rodeiro
    Câmara Municipal de Rubim
    Câmara Municipal de Sabará
    Câmara Municipal de Sabinópolis
    Câmara Municipal de Sacramento
    Câmara Municipal de Salinas
    Câmara Municipal de Santa Bárbara
    Câmara Municipal de Santa Bárbara do Leste
    Câmara Municipal de Santa Bárbara do Tugúrio
    Câmara Municipal de Santa Cruz de Minas
    Câmara Municipal de Santa Efigênia de Minas
    Câmara Municipal de Santa Juliana
    Câmara Municipal de Santa Helena de Minas
    Câmara Municipal de Santa Luzia
    Câmara Municipal de Santa Rita de Caldas
    Câmara Municipal de Santa Rita de Ibitipoca
    Câmara Municipal de Santa Rita de Jacutinga
    Câmara Municipal de Santa Rita de Minas
    Câmara Municipal de Santa Rita do Sapucaí
    Câmara Municipal de Santa Rosa da Serra
    Câmara Municipal de Santa Vitória
    Câmara Municipal de Santana de Cataguases
    Câmara Municipal de Santana do Jacaré
    Câmara Municipal de Santana do Paraíso
    Câmara Municipal de Santo Antônio do Amparo
    Câmara Municipal de Santo Antônio do Aventureiro
    Câmara Municipal de Santo Antônio do Grama
    Câmara Municipal de Santo Antônio do Monte
    Câmara Municipal de Santos Dumont
    Câmara Municipal de São Bento Abade
    Câmara Municipal de São Brás do Suaçuí
    Câmara Municipal de São Domingos do Prata
    Câmara Municipal de São Félix de Minas
    Câmara Municipal de São Francisco
    Câmara Municipal de São Francisco de Paula
    Câmara Municipal de São Francisco de Sales
    Câmara Municipal de São Gonçalo do Pará
    Câmara Municipal de São Gonçalo do Rio Abaixo
    Câmara Municipal de São Gonçalo do Sapucaí
    Câmara Municipal de São Gotardo
    Câmara Municipal de São João del-Rei
    Câmara Municipal de São João Nepomuceno
    Câmara Municipal de São João da Mata
    Câmara Municipal de São Joaquim de Bicas
    Câmara Municipal de São José da Barra
    Câmara Municipal de São José da Lapa
    Câmara Municipal de São José da Varginha
    Câmara Municipal de São Lourenço
    Câmara Municipal de São Sebastião da Bela Vista
    Câmara Municipal de São Sebastião do Oeste
    Câmara Municipal de São Sebastião do Paraíso
    Câmara Municipal de São Sebastião do Rio Verde
    Câmara Municipal de São Tiago
    Câmara Municipal de São Tomé das Letras
    Câmara Municipal de São Vicente de Minas
    Câmara Municipal de Sapucaí Mirim
    Câmara Municipal de Sardoá
    Câmara Municipal de Sarzedo
    Câmara Municipal de Senador José Bento
    Câmara Municipal de Serra Azul de Minas
    Câmara Municipal de Serranos
    Câmara Municipal de Sete Lagoas
    Câmara Municipal de Silveirânia
    Câmara Municipal de Silvianópolis
    Câmara Municipal de Simão Pereira
    Câmara Municipal de Soledade de Minas
    Câmara Municipal de Taiobeiras
    Câmara Municipal de Taparuba
    Câmara Municipal de Tapira
    Câmara Municipal de Teixeiras
    Câmara Municipal de Teófilo Otoni
    Câmara Municipal de Timóteo
    Câmara Municipal de Tiradentes
    Câmara Municipal de Tocantins
    Câmara Municipal de Tocos do Moji
    Câmara Municipal de Tombos
    Câmara Municipal de Três Corações
    Câmara Municipal de Três Marias
    Câmara Municipal de Três Pontas
    Câmara Municipal de Tumiritinga
    Câmara Municipal de Tupaciguara
    Câmara Municipal de Turmalina
    Câmara Municipal de Turvolândia
    Câmara Municipal de Ubá
    Câmara Municipal de Ubaporanga
    Câmara Municipal de Uberaba
    Câmara Municipal de Uberlândia
    Câmara Municipal de Unaí
    Câmara Municipal de União de Minas
    Câmara Municipal de Uruana de Minas
    Câmara Municipal de Vargem Bonita
    Câmara Municipal de Varginha
    Câmara Municipal de Varjão de Minas
    Câmara Municipal de Várzea da Palma
    Câmara Municipal de Varzelândia
    Câmara Municipal de Vazante
    Câmara Municipal de Veríssimo
    Câmara Municipal de Vermelho Novo
    Câmara Municipal de Vespasiano
    Câmara Municipal de Viçosa
    Câmara Municipal de Virginópolis
    Câmara Municipal de Virgolândia
    Câmara Municipal de Visconde do Rio Branco
    Câmara Municipal de Volta Grande
    


```python
for link in soup.find_all('a'):
    nome_cidade = link.text.replace('Câmara Municipal de ', '')
    print(nome_cidade)
```

    Aimorés
    Aiuruoca
    Albertina
    Além Paraíba
    Alfenas
    Alfredo Vasconcelos
    Almenara
    Alterosa
    Alto Caparaó
    Alto Jequitibá
    Alvarenga
    Andradas
    Andrelândia
    Antônio Carlos
    Araguari
    Araporã
    Araxá
    Arceburgo
    Arcos
    Areado
    Arinos
    Ataleia
    Baependi
    Bambuí
    Barão de Cocais
    Barbacena
    Barroso
    Bela Vista de Minas
    Belo Horizonte
    Belo Vale
    Bertópolis
    Betim
    Bicas
    Boa Esperança
    Bocaina de Minas
    Bocaiúva
    Bom Despacho
    Bom Jardim de Minas
    Bom Jesus da Penha
    Bom Jesus do Amparo
    Bonfinópolis de Minas
    Botelhos
    Brasilândia de Minas
    Brasília de Minas
    Brazópolis
    Brumadinho
    Buritis
    Buritizeiro
    Cabeceira Grande
    Cachoeira de Minas
    Caeté
    Caiana
    Caldas
    Camacho
    Camanducaia
    Cambuí
    Cambuquira
    Campanário
    Campanha
    Campina Verde
    Campo Belo
    Campo do Meio
    Campos Altos
    Campos Gerais
    Canápolis
    Capelinha
    Capetinga
    Capitão Andrade
    Capim Branco
    Capinópolis
    Caputira
    Carandaí
    Carangola
    Caratinga
    Carbonita
    Careaçu
    Carmésia
    Carmo da Cachoeira
    Carmo da Mata
    Carmo de Minas
    Carmo do Cajuru
    Carmo do Paranaíba
    Carmo do Rio Claro
    Carmópolis de Minas
    Carneirinho
    Carrancas
    Carvalhópolis
    Casa Grande
    Cássia
    Cataguases
    Caxambu
    Chalé
    Claraval
    Cláudio
    Conceição das Alagoas
    Conceição de Ipanema
    Conceição do Pará
    Conceição dos Ouros
    Confins
    Congonhal
    Congonhas
    Conquista
    Conselheiro Lafaiete
    Conselheiro Pena
    Consolação
    Contagem
    Cordislândia
    Coromandel
    Coronel Fabriciano
    Coronel Pacheco
    Coronel Xavier Chaves
    Córrego Danta
    Córrego do Bom Jesus
    Couto de Magalhães de Minas
    Cristiano Otoni
    Crisólita
    Cristina
    Cruzília
    Curvelo
    Delfinópolis
    Delta
    Descoberto
    Diamantina
    Dionísio
    Divinolândia de Minas
    Divinópolis
    Dom Bosco
    Dom Silvério
    Dona Euzébia
    Dores de Campos
    Dores do Indaiá
    Entre Rios de Minas
    Ervália
    Esmeraldas
    Espera Feliz
    Estiva
    Estrela do Indaiá
    Estrela do Sul
    Extrema
    Fama
    Faria Lemos
    Ferros
    Fervedouro
    Florestal
    Formiga
    Formoso
    Fortaleza de Minas
    Fortuna de Minas
    Fronteira
    Frutal
    Galileia
    Gonçalves
    Governador Valadares
    Grão Mogol
    Guanhães
    Guaranésia
    Guarani
    Guarda-Mor
    Guaxupé
    Guimarânia
    Heliodora
    Ibiá
    Ibiraci
    Ibirité
    Igarapé
    Igaratinga
    Iguatama
    Inconfidentes
    Indaiabira
    Indianópolis
    Inimutaba
    Ipanema
    Ipatinga
    Ipiaçu
    Iraí de Minas
    Itabira
    Itabirito
    Itaguara
    Itajubá
    Itamogi
    Itamonte
    Itanhandu
    Itanhomi
    Itaobim
    Itapagipe
    Itapecerica
    Itapeva
    Itaú de Minas
    Itaúna
    Ituiutaba
    Iturama
    Jaboticatubas
    Jacinto
    Jacuí
    Jacutinga
    Jaguaraçu
    Jaíba
    Jampruca
    Janaúba
    Januária
    Jequitinhonha
    Jesuânia
    Joaíma
    Joaquim Felício
    João Monlevade
    João Pinheiro
    Jordânia
    Juatuba
    Juiz de Fora
    Juruaia
    Juvenília
    Lagamar
    Lagoa da Prata
    Lagoa Formosa
    Lagoa Santa
    Lajinha
    Lambari
    Lassance
    Lavras
    Leopoldina
    Liberdade
    Lima Duarte
    Limeira do Oeste
    Luislândia
    Luminárias
    Luz
    Machacalis
    Machado
    Mamonas
    Manhuaçu
    Manhumirim
    Mantena
    Maria da Fé
    Mariana
    Mário Campos
    Marmelópolis
    Martinho Campos
    Mateus Leme
    Matias Barbosa
    Matozinhos
    Minas Novas
    Miradouro
    Miraí
    Moeda
    Moema
    Monjolos
    Monsenhor Paulo
    Montalvânia
    Monte Alegre de Minas
    Monte Azul
    Monte Belo
    Monte Carmelo
    Monte Santo de Minas
    Monte Sião
    Montes Claros
    Morada Nova de Minas
    Morro da Garça
    Muriaé
    Mutum
    Muzambinho
    Nanuque
    Natalândia
    Natércia
    Nepomuceno
    Nova Era
    Nova Lima
    Nova Serrana
    Olímpio Noronha
    Oliveira
    Oratórios
    Ouro Branco
    Ouro Fino
    Ouro Preto
    Paineiras
    Pains
    Pará de Minas
    Paracatu
    Paraguaçu
    Paraopeba
    Passa Quatro
    Passa Tempo
    Passos
    Patos de Minas
    Patrocínio
    Peçanha
    Pedra Azul
    Pedra Bonita
    Pedra do Indaiá
    Pedra Dourada
    Pedralva
    Pedrinópolis
    Pedro Leopoldo
    Pedro Teixeira
    Pequi
    Perdizes
    Pescador
    Piau
    Piracema
    Piranguçu
    Piranguinho
    Pirapetinga
    Pirapora
    Piraúba
    Piumhi
    Planura
    Poços de Caldas
    Pompéu
    Ponte Nova
    Ponto dos Volantes
    Pouso Alegre
    Pouso Alto
    Prados
    Prata
    Presidente Olegário
    Raposos
    Raul Soares
    Reduto
    Resende Costa
    Ressaquinha
    Ribeirão das Neves
    Rio Acima
    Rio Casca
    Rio Novo
    Rio Paranaíba
    Rio Piracicaba
    Rio Pomba
    
    Rio Preto
    Ritápolis
    Rodeiro
    Rubim
    Sabará
    Sabinópolis
    Sacramento
    Salinas
    Santa Bárbara
    Santa Bárbara do Leste
    Santa Bárbara do Tugúrio
    Santa Cruz de Minas
    Santa Efigênia de Minas
    Santa Juliana
    Santa Helena de Minas
    Santa Luzia
    Santa Rita de Caldas
    Santa Rita de Ibitipoca
    Santa Rita de Jacutinga
    Santa Rita de Minas
    Santa Rita do Sapucaí
    Santa Rosa da Serra
    Santa Vitória
    Santana de Cataguases
    Santana do Jacaré
    Santana do Paraíso
    Santo Antônio do Amparo
    Santo Antônio do Aventureiro
    Santo Antônio do Grama
    Santo Antônio do Monte
    Santos Dumont
    São Bento Abade
    São Brás do Suaçuí
    São Domingos do Prata
    São Félix de Minas
    São Francisco
    São Francisco de Paula
    São Francisco de Sales
    São Gonçalo do Pará
    São Gonçalo do Rio Abaixo
    São Gonçalo do Sapucaí
    São Gotardo
    São João del-Rei
    São João Nepomuceno
    São João da Mata
    São Joaquim de Bicas
    São José da Barra
    São José da Lapa
    São José da Varginha
    São Lourenço
    São Sebastião da Bela Vista
    São Sebastião do Oeste
    São Sebastião do Paraíso
    São Sebastião do Rio Verde
    São Tiago
    São Tomé das Letras
    São Vicente de Minas
    Sapucaí Mirim
    Sardoá
    Sarzedo
    Senador José Bento
    Serra Azul de Minas
    Serranos
    Sete Lagoas
    Silveirânia
    Silvianópolis
    Simão Pereira
    Soledade de Minas
    Taiobeiras
    Taparuba
    Tapira
    Teixeiras
    Teófilo Otoni
    Timóteo
    Tiradentes
    Tocantins
    Tocos do Moji
    Tombos
    Três Corações
    Três Marias
    Três Pontas
    Tumiritinga
    Tupaciguara
    Turmalina
    Turvolândia
    Ubá
    Ubaporanga
    Uberaba
    Uberlândia
    Unaí
    União de Minas
    Uruana de Minas
    Vargem Bonita
    Varginha
    Varjão de Minas
    Várzea da Palma
    Varzelândia
    Vazante
    Veríssimo
    Vermelho Novo
    Vespasiano
    Viçosa
    Virginópolis
    Virgolândia
    Visconde do Rio Branco
    Volta Grande
    


```python
for link in soup.find_all('a'):
    nome_cidade = link.text.replace('Câmara Municipal de ', '')
    palavras = nome_cidade.split()
    nome_formatado = ' '.join([f'"{palavra}"' for palavra in palavras])
    print(nome_formatado, end=', ')


```

    "Aimorés", "Aiuruoca", "Albertina", "Além" "Paraíba", "Alfenas", "Alfredo" "Vasconcelos", "Almenara", "Alterosa", "Alto" "Caparaó", "Alto" "Jequitibá", "Alvarenga", "Andradas", "Andrelândia", "Antônio" "Carlos", "Araguari", "Araporã", "Araxá", "Arceburgo", "Arcos", "Areado", "Arinos", "Ataleia", "Baependi", "Bambuí", "Barão" "de" "Cocais", "Barbacena", "Barroso", "Bela" "Vista" "de" "Minas", "Belo" "Horizonte", "Belo" "Vale", "Bertópolis", "Betim", "Bicas", "Boa" "Esperança", "Bocaina" "de" "Minas", "Bocaiúva", "Bom" "Despacho", "Bom" "Jardim" "de" "Minas", "Bom" "Jesus" "da" "Penha", "Bom" "Jesus" "do" "Amparo", "Bonfinópolis" "de" "Minas", "Botelhos", "Brasilândia" "de" "Minas", "Brasília" "de" "Minas", "Brazópolis", "Brumadinho", "Buritis", "Buritizeiro", "Cabeceira" "Grande", "Cachoeira" "de" "Minas", "Caeté", "Caiana", "Caldas", "Camacho", "Camanducaia", "Cambuí", "Cambuquira", "Campanário", "Campanha", "Campina" "Verde", "Campo" "Belo", "Campo" "do" "Meio", "Campos" "Altos", "Campos" "Gerais", "Canápolis", "Capelinha", "Capetinga", "Capitão" "Andrade", "Capim" "Branco", "Capinópolis", "Caputira", "Carandaí", "Carangola", "Caratinga", "Carbonita", "Careaçu", "Carmésia", "Carmo" "da" "Cachoeira", "Carmo" "da" "Mata", "Carmo" "de" "Minas", "Carmo" "do" "Cajuru", "Carmo" "do" "Paranaíba", "Carmo" "do" "Rio" "Claro", "Carmópolis" "de" "Minas", "Carneirinho", "Carrancas", "Carvalhópolis", "Casa" "Grande", "Cássia", "Cataguases", "Caxambu", "Chalé", "Claraval", "Cláudio", "Conceição" "das" "Alagoas", "Conceição" "de" "Ipanema", "Conceição" "do" "Pará", "Conceição" "dos" "Ouros", "Confins", "Congonhal", "Congonhas", "Conquista", "Conselheiro" "Lafaiete", "Conselheiro" "Pena", "Consolação", "Contagem", "Cordislândia", "Coromandel", "Coronel" "Fabriciano", "Coronel" "Pacheco", "Coronel" "Xavier" "Chaves", "Córrego" "Danta", "Córrego" "do" "Bom" "Jesus", "Couto" "de" "Magalhães" "de" "Minas", "Cristiano" "Otoni", "Crisólita", "Cristina", "Cruzília", "Curvelo", "Delfinópolis", "Delta", "Descoberto", "Diamantina", "Dionísio", "Divinolândia" "de" "Minas", "Divinópolis", "Dom" "Bosco", "Dom" "Silvério", "Dona" "Euzébia", "Dores" "de" "Campos", "Dores" "do" "Indaiá", "Entre" "Rios" "de" "Minas", "Ervália", "Esmeraldas", "Espera" "Feliz", "Estiva", "Estrela" "do" "Indaiá", "Estrela" "do" "Sul", "Extrema", "Fama", "Faria" "Lemos", "Ferros", "Fervedouro", "Florestal", "Formiga", "Formoso", "Fortaleza" "de" "Minas", "Fortuna" "de" "Minas", "Fronteira", "Frutal", "Galileia", "Gonçalves", "Governador" "Valadares", "Grão" "Mogol", "Guanhães", "Guaranésia", "Guarani", "Guarda-Mor", "Guaxupé", "Guimarânia", "Heliodora", "Ibiá", "Ibiraci", "Ibirité", "Igarapé", "Igaratinga", "Iguatama", "Inconfidentes", "Indaiabira", "Indianópolis", "Inimutaba", "Ipanema", "Ipatinga", "Ipiaçu", "Iraí" "de" "Minas", "Itabira", "Itabirito", "Itaguara", "Itajubá", "Itamogi", "Itamonte", "Itanhandu", "Itanhomi", "Itaobim", "Itapagipe", "Itapecerica", "Itapeva", "Itaú" "de" "Minas", "Itaúna", "Ituiutaba", "Iturama", "Jaboticatubas", "Jacinto", "Jacuí", "Jacutinga", "Jaguaraçu", "Jaíba", "Jampruca", "Janaúba", "Januária", "Jequitinhonha", "Jesuânia", "Joaíma", "Joaquim" "Felício", "João" "Monlevade", "João" "Pinheiro", "Jordânia", "Juatuba", "Juiz" "de" "Fora", "Juruaia", "Juvenília", "Lagamar", "Lagoa" "da" "Prata", "Lagoa" "Formosa", "Lagoa" "Santa", "Lajinha", "Lambari", "Lassance", "Lavras", "Leopoldina", "Liberdade", "Lima" "Duarte", "Limeira" "do" "Oeste", "Luislândia", "Luminárias", "Luz", "Machacalis", "Machado", "Mamonas", "Manhuaçu", "Manhumirim", "Mantena", "Maria" "da" "Fé", "Mariana", "Mário" "Campos", "Marmelópolis", "Martinho" "Campos", "Mateus" "Leme", "Matias" "Barbosa", "Matozinhos", "Minas" "Novas", "Miradouro", "Miraí", "Moeda", "Moema", "Monjolos", "Monsenhor" "Paulo", "Montalvânia", "Monte" "Alegre" "de" "Minas", "Monte" "Azul", "Monte" "Belo", "Monte" "Carmelo", "Monte" "Santo" "de" "Minas", "Monte" "Sião", "Montes" "Claros", "Morada" "Nova" "de" "Minas", "Morro" "da" "Garça", "Muriaé", "Mutum", "Muzambinho", "Nanuque", "Natalândia", "Natércia", "Nepomuceno", "Nova" "Era", "Nova" "Lima", "Nova" "Serrana", "Olímpio" "Noronha", "Oliveira", "Oratórios", "Ouro" "Branco", "Ouro" "Fino", "Ouro" "Preto", "Paineiras", "Pains", "Pará" "de" "Minas", "Paracatu", "Paraguaçu", "Paraopeba", "Passa" "Quatro", "Passa" "Tempo", "Passos", "Patos" "de" "Minas", "Patrocínio", "Peçanha", "Pedra" "Azul", "Pedra" "Bonita", "Pedra" "do" "Indaiá", "Pedra" "Dourada", "Pedralva", "Pedrinópolis", "Pedro" "Leopoldo", "Pedro" "Teixeira", "Pequi", "Perdizes", "Pescador", "Piau", "Piracema", "Piranguçu", "Piranguinho", "Pirapetinga", "Pirapora", "Piraúba", "Piumhi", "Planura", "Poços" "de" "Caldas", "Pompéu", "Ponte" "Nova", "Ponto" "dos" "Volantes", "Pouso" "Alegre", "Pouso" "Alto", "Prados", "Prata", "Presidente" "Olegário", "Raposos", "Raul" "Soares", "Reduto", "Resende" "Costa", "Ressaquinha", "Ribeirão" "das" "Neves", "Rio" "Acima", "Rio" "Casca", "Rio" "Novo", "Rio" "Paranaíba", "Rio" "Piracicaba", "Rio" "Pomba", "Rio" "Preto", "Ritápolis", "Rodeiro", "Rubim", "Sabará", "Sabinópolis", "Sacramento", "Salinas", "Santa" "Bárbara", "Santa" "Bárbara" "do" "Leste", "Santa" "Bárbara" "do" "Tugúrio", "Santa" "Cruz" "de" "Minas", "Santa" "Efigênia" "de" "Minas", "Santa" "Juliana", "Santa" "Helena" "de" "Minas", "Santa" "Luzia", "Santa" "Rita" "de" "Caldas", "Santa" "Rita" "de" "Ibitipoca", "Santa" "Rita" "de" "Jacutinga", "Santa" "Rita" "de" "Minas", "Santa" "Rita" "do" "Sapucaí", "Santa" "Rosa" "da" "Serra", "Santa" "Vitória", "Santana" "de" "Cataguases", "Santana" "do" "Jacaré", "Santana" "do" "Paraíso", "Santo" "Antônio" "do" "Amparo", "Santo" "Antônio" "do" "Aventureiro", "Santo" "Antônio" "do" "Grama", "Santo" "Antônio" "do" "Monte", "Santos" "Dumont", "São" "Bento" "Abade", "São" "Brás" "do" "Suaçuí", "São" "Domingos" "do" "Prata", "São" "Félix" "de" "Minas", "São" "Francisco", "São" "Francisco" "de" "Paula", "São" "Francisco" "de" "Sales", "São" "Gonçalo" "do" "Pará", "São" "Gonçalo" "do" "Rio" "Abaixo", "São" "Gonçalo" "do" "Sapucaí", "São" "Gotardo", "São" "João" "del-Rei", "São" "João" "Nepomuceno", "São" "João" "da" "Mata", "São" "Joaquim" "de" "Bicas", "São" "José" "da" "Barra", "São" "José" "da" "Lapa", "São" "José" "da" "Varginha", "São" "Lourenço", "São" "Sebastião" "da" "Bela" "Vista", "São" "Sebastião" "do" "Oeste", "São" "Sebastião" "do" "Paraíso", "São" "Sebastião" "do" "Rio" "Verde", "São" "Tiago", "São" "Tomé" "das" "Letras", "São" "Vicente" "de" "Minas", "Sapucaí" "Mirim", "Sardoá", "Sarzedo", "Senador" "José" "Bento", "Serra" "Azul" "de" "Minas", "Serranos", "Sete" "Lagoas", "Silveirânia", "Silvianópolis", "Simão" "Pereira", "Soledade" "de" "Minas", "Taiobeiras", "Taparuba", "Tapira", "Teixeiras", "Teófilo" "Otoni", "Timóteo", "Tiradentes", "Tocantins", "Tocos" "do" "Moji", "Tombos", "Três" "Corações", "Três" "Marias", "Três" "Pontas", "Tumiritinga", "Tupaciguara", "Turmalina", "Turvolândia", "Ubá", "Ubaporanga", "Uberaba", "Uberlândia", "Unaí", "União" "de" "Minas", "Uruana" "de" "Minas", "Vargem" "Bonita", "Varginha", "Varjão" "de" "Minas", "Várzea" "da" "Palma", "Varzelândia", "Vazante", "Veríssimo", "Vermelho" "Novo", "Vespasiano", "Viçosa", "Virginópolis", "Virgolândia", "Visconde" "do" "Rio" "Branco", "Volta" "Grande", 


```python

```
