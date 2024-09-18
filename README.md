# Municipis_Comarques_Catalunya

# Complete list of municipis by comarca by provìncia de Catalunya.

# Script to Select a municipi and comarca of Catalonia. 

Dades recollides de diverses fonts estadístiques de diversos organismes de la Generalitat de Catalunya i Diputacions. 

          <div class="field">
            <p class='mb-1 font-bold mr-3'>Provìncia:</p>
            <%= f.select :provincia, options_for_select(['Select', 'Barcelona', 'Girona', 'Lleida', 'Tarragona']), {}, { id: 'provincia-select' } %>
          </div>
          <div class="field">
            <p class='mb-1 font-bold mr-3'>Comarca:</p>
            <%= f.select :comarca, [], {}, { id: 'comarca-select' } %>
          </div>
          <div class="field">
            <p class='mb-1 font-bold mr-3'>Municipi:</p>
            <%= f.select :municipi, [], {}, { id: 'municipi-select' } %>
          </div>
          <script>
            const comarques = {
              'Barcelona': ['Alt Penedès', 'Anoia', 'Bages', 'Baix Llobregat', 'Barcelonès', 'Berguedà', 'Garraf', 'Maresme', 'Moianès', 'Osona', 'Vallès Occidental', 'Vallès Oriental'],
              'Girona': ['Alt Empordà', 'Baix Empordà', 'Cerdanya', 'Garrotxa', 'Gironès', 'Pla de l\'Estany', 'Ripollès', 'Selva'],
              'Lleida': ['Alt Urgell', 'Alta Ribagorça', 'Garrigues', 'Noguera', 'Pallars Jussà', 'Pallars Sobirà', 'Pla d\'Urgell', 'Segarra', 'Segrià', 'Solsonès', 'Urgell', 'Vall d\'Aran'],
              'Tarragona': ['Alt Camp', 'Baix Camp', 'Baix Ebre', 'Baix Penedès', 'Conca de Barberà', 'Montsià', 'Priorat', 'Ribera d\'Ebre', 'Tarragonès', 'Terra Alta']
            };

            const municipis = {
              'Alt Penedès': [
                'Vilafranca del Penedès', 'Sant Sadurní d\'Anoia', 'Avinyonet del Penedès', 'Les Cabanyes', 'Castellet i la Gornal',
                'Castellví de la Marca', 'Font-rubí', 'Gelida', 'Granada, la', 'Mediona', 'Olèrdola', 'Olesa de Bonesvalls',
                'Pacs del Penedès', 'Pla del Penedès, el', 'Pontons', 'Puigdàlber', 'Sant Cugat Sesgarrigues', 'Sant Llorenç d’Hortons',
                'Sant Martí Sarroca', 'Sant Pere de Riudebitlles', 'Sant Quintí de Mediona', 'Santa Fe del Penedès',
                'Santa Margarida i els Monjos', 'Subirats', 'Torrelavit', 'Torrelles de Foix', 'Vilobí del Penedès'
              ],
              'Anoia': [
                'Argençola', 'Bellprat', 'Bruc, el', 'Cabrera d’Anoia', 'Calaf', 'Calonge de Segarra', 'Capellades', 'Carme',
                'Castellfollit de Riubregós', 'Castellolí', 'Copons', 'Hostalets de Pierola, els', 'Igualada', 'Jorba', 'Llacuna, la',
                'Masquefa', 'Montmaneu', 'Òdena', 'Orpí', 'Piera', 'Pobla de Claramunt, la', 'Prats de Rei, els', 'Pujalt', 'Rubió',
                'Sant Martí de Tous', 'Sant Martí Sesgueioles', 'Sant Pere Sallavinera', 'Santa Margarida de Montbui',
                'Santa Maria de Miralles', 'Torre de Claramunt, la', 'Vallbona d’Anoia', 'Veciana', 'Vilanova del Camí'
              ],
              'Bages': [
                'Aguilar de Segarra', 'Artés', 'Avinyó', 'Balsareny', 'Callús', 'Cardona', 'Castellbell i el Vilar',
                'Castellfollit del Boix', 'Castellgalí', 'Castellnou de Bages', 'Fonollosa', 'Gaià', 'Manresa', 'Marganell',
                'Monistrol de Montserrat', 'Mura', 'Navarcles', 'Navàs', 'Pont de Vilomara i Rocafort, el', 'Rajadell', 'Sallent',
                'Sant Feliu Sasserra', 'Sant Fruitós de Bages', 'Sant Joan de Vilatorrada', 'Sant Mateu de Bages',
                'Sant Salvador de Guardiola', 'Sant Vicenç de Castellet', 'Santpedor', 'Súria', 'Talamanca'
              ],
              'Baix Llobregat': [
                'Abrera', 'Begues', 'Castelldefels', 'Castellví de Rosanes', 'Cervelló', 'Collbató', 'Corbera de Llobregat',
                'Cornellà de Llobregat', 'Esparreguera', 'Esplugues de Llobregat', 'Gavà', 'Martorell', 'Molins de Rei',
                'Olesa de Montserrat', 'Pallejà', 'Palma de Cervelló, la', 'Papiol, el', 'Prat de Llobregat, el', 'Sant Andreu de la Barca',
                'Sant Boi de Llobregat', 'Sant Climent de Llobregat', 'Sant Esteve Sesrovires', 'Sant Feliu de Llobregat',
                'Sant Joan Despí', 'Sant Just Desvern', 'Sant Vicenç dels Horts', 'Santa Coloma de Cervelló', 'Torrelles de Llobregat',
                'Vallirana', 'Viladecans'
              ],
              'Barcelonès': [
                'Badalona', 'Barcelona', 'Hospitalet de Llobregat, l\'', 'Sant Adrià de Besòs', 'Santa Coloma de Gramenet'
              ],
              'Berguedà': [
                'Avià', 'Bagà', 'Berga', 'Borredà', 'Capolat', 'Casserres', 'Castell de l’Areny', 'Castellar de n’Hug',
                'Castellar del Riu', 'Cercs', 'Espunyola, l\'', 'Fígols', 'Gironella', 'Gisclareny', 'Guardiola de Berguedà',
                'Montclar', 'Montmajor', 'Nou de Berguedà, la', 'Olvan', 'Pobla de Lillet, la', 'Puig-reig', 'Quar, la', 'Sagàs',
                'Saldes', 'Sant Jaume de Frontanyà', 'Sant Julià de Cerdanyola', 'Santa Maria de Merlès', 'Vallcebre', 'Vilada',
                'Viver i Serrateix'
              ],
              'Garraf': [
                'Canyelles', 'Cubelles', 'Olivella', 'Sant Pere de Ribes', 'Sitges', 'Vilanova i la Geltrú'
              ],
              'Lluçanès': [
                'Alpens', 'Lluçà', 'Olost', 'Oristà', 'Perafita', 'Prats de Lluçanès', 'Sant Martí d’Albars', 'Sobremunt'
              ],
              'Maresme': [
                'Alella', 'Arenys de Mar', 'Arenys de Munt', 'Argentona', 'Cabrera de Mar', 'Cabrils', 'Caldes d’Estrac', 'Calella',
                'Canet de Mar', 'Dosrius', 'Malgrat de Mar', 'Masnou, el', 'Mataró', 'Montgat', 'Òrrius', 'Palafolls', 'Pineda de Mar',
                'Premià de Dalt', 'Premià de Mar', 'Sant Andreu de Llavaneres', 'Sant Cebrià de Vallalta', 'Sant Iscle de Vallalta',
                'Sant Pol de Mar', 'Sant Vicenç de Montalt', 'Santa Susanna', 'Teià', 'Tiana', 'Tordera', 'Vilassar de Dalt',
                'Vilassar de Mar'
              ],
              'Moianès': [
                'Calders', 'Castellcir', 'Castellterçol', 'Collsuspina', 'Estany, l\'', 'Granera', 'Moià', 'Monistrol de Calders',
                'Sant Quirze Safaja', 'Santa Maria d’Oló'
              ],
              'Osona': [
                'Balenyà', 'Brull, el', 'Calldetenes', 'Centelles', 'Esquirol, l\'', 'Folgueroles', 'Gurb', 'Malla', 'Manlleu',
                'Masies de Roda, les', 'Masies de Voltregà, les', 'Montesquiu', 'Muntanyola', 'Orís', 'Roda de Ter', 'Rupit i Pruit',
                'Sant Agustí de Lluçanès', 'Sant Bartomeu del Grau', 'Sant Boi de Lluçanès', 'Sant Hipòlit de Voltregà',
                'Sant Julià de Vilatorta', 'Sant Martí de Centelles', 'Sant Pere de Torelló', 'Sant Quirze de Besora',
                'Sant Sadurní d’Osormort', 'Sant Vicenç de Torelló', 'Santa Cecília de Voltregà', 'Santa Eugènia de Berga',
                'Santa Eulàlia de Riuprimer', 'Santa Maria de Besora', 'Seva', 'Sora', 'Taradell', 'Tavèrnoles', 'Tavertet', 'Tona',
                'Torelló', 'Vic', 'Vilanova de Sau'
              ],
              'Vallès Occidental': [
                'Badia del Vallès', 'Barberà del Vallès', 'Castellar del Vallès', 'Castellbisbal', 'Cerdanyola del Vallès', 'Gallifa',
                'Matadepera', 'Montcada i Reixac', 'Palau-solità i Plegamans', 'Polinyà', 'Rellinars', 'Ripollet', 'Rubí', 'Sabadell',
                'Sant Cugat del Vallès', 'Sant Llorenç Savall', 'Sant Quirze del Vallès', 'Santa Perpètua de Mogoda', 'Sentmenat',
                'Terrassa', 'Ullastrell', 'Vacarisses', 'Viladecavalls'
              ],
              'Vallès Oriental': [
                'Aiguafreda', 'Ametlla del Vallès, l\'', 'Bigues i Riells del Fai', 'Caldes de Montbui', 'Campins', 'Canovelles',
                'Cànoves i Samalús', 'Cardedeu', 'Figaró-Montmany', 'Fogars de Montclús', 'Franqueses del Vallès, les', 'Garriga, la',
                'Granollers', 'Gualba', 'Llagosta, la', 'Lliçà d’Amunt', 'Lliçà de Vall', 'Llinars del Vallès', 'Martorelles',
                'Mollet del Vallès', 'Montmeló', 'Montornès del Vallès', 'Montseny', 'Parets del Vallès', 'Roca del Vallès',
                'Sant Antoni de Vilamajor', 'Sant Celoni', 'Sant Esteve de Palautordera', 'Sant Feliu de Codines',
                'Sant Fost de Campsentelles', 'Sant Pere de Vilamajor', 'Santa Eulàlia de Ronçana', 'Santa Maria de Martorelles',
                'Santa Maria de Palautordera', 'Tagamanent', 'Vallgorguina', 'Vallromanes', 'Vilalba Sasserra', 'Vilanova del Vallès'
              ],
              'Alt Empordà': ['Figueres', 'Roses', 'Agullana', 'Aiguamúrcia', 'Albanyà', 'Albons', 'Avinyonet de Puigventós', 'Bàscara', 'Biure', 'Boadella i les Escaules', 'Borrassà', 'Cabanelles', 'Cabanes', 'Cadaqués', 'Cantallops', 'Capmany', 'Castelló d\'Empúries', 'Cistella', 'Colera', 'Darnius', 'Espolla', 'Far d\'Empordà, el', 'Garriguella', 'Jonquera, la', 'Lladó', 'Llançà', 'Llers', 'Maçanet de Cabrenys', 'Masarac', 'Mollet de Peralada', 'Navata', 'Ordis', 'Palau de Santa Eulàlia', 'Palau-saverdera', 'Pau', 'Pedret i Marzà', 'Peralada', 'Pont de Molins', 'Pontós', 'Portbou', 'Rabós', 'Riumors', 'Sant Climent Sescebes', 'Sant Llorenç de la Muga', 'Sant Miquel de Fluvià', 'Sant Mori', 'Sant Pere Pescador', 'Santa Llogaia d\'Àlguema', 'Saus, Camallera i Llampaies', 'Selva de Mar, la', 'Siurana', 'Terrades', 'Torroella de Fluvià', 'Vajol, la', 'Ventalló', 'Vila-sacra', 'Vilabertran', 'Viladamat', 'Vilafant', 'Vilajuïga', 'Vilamacolum', 'Vilamalla', 'Vilamaniscle', 'Vilanant'
              ],
              'Baix Empordà': ['Palafrugell', 'Sant Feliu de Guíxols', 'Begur', 'Bellcaire d\'Empordà', 'Bisbal d\'Empordà, la', 'Calonge i Sant Antoni', 'Colomers', 'Corçà', 'Cruïlles, Monells i Sant Sadurní de l\'Heura', 'Foixà', 'Fontanilles', 'Forallac', 'Garrigoles', 'Gualta', 'Jafre', 'Mont-ras', 'Palamós', 'Palau-sator', 'Parlavà', 'Pals', 'Regencós', 'Rupià', 'Serra de Daró', 'Tallada d\'Empordà, la', 'Torrent', 'Torroella de Montgrí', 'Ullà', 'Ullastret', 'Vall-llobrega', 'Verges', 'Vilopriu'
              ],
              'Cerdanya': ['Puigcerdà', 'Bellver de Cerdanya', 'Alp', 'Bolvir', 'Das', 'Fontanals de Cerdanya', 'Ger', 'Guils de Cerdanya', 'Isòvol', 'Lles de Cerdanya', 'Llívia', 'Meranges', 'Montellà i Martinet', 'Prats i Sansor', 'Prullans', 'Riu de Cerdanya', 'Urús'
              ],
              'Garrotxa': ['Olot', 'Besalú', 'Argelaguer', 'Beuda', 'Castellfollit de la Roca', 'Maià de Montcal', 'Mieres', 'Montagut i Oix', 'Sales de Llierca', 'Sant Aniol de Finestres', 'Sant Feliu de Pallerols', 'Sant Ferriol', 'Sant Jaume de Llierca', 'Sant Joan les Fonts', 'Santa Pau', 'Tortellà', 'Vall de Bianya, la', 'Vall d\'en Bas, la'
              ],
              'Gironès': ['Girona', 'Salt', 'Aiguaviva', 'Bescanó', 'Bordils', 'Campllong', 'Canet d\'Adri', 'Cassà de la Selva', 'Celrà', 'Flaçà', 'Fornells de la Selva', 'Juià', 'Llagostera', 'Llambilles', 'Madremanya', 'Quart', 'Sant Andreu Salou', 'Sant Gregori', 'Sant Julià de Ramis', 'Sant Martí Vell', 'Sant Martí de Llémena', 'Sarrià de Ter', 'Vilablareix'
              ],
              'Pla de l\'Estany': ['Banyoles', 'Porqueres', 'Camós', 'Cornellà del Terri', 'Crespià', 'Esponellà', 'Fontcoberta', 'Palol de Revardit', 'Sant Miquel de Campmajor', 'Serinyà', 'Vilademuls'
              ],
              'Ripollès': ['Ripoll', 'Sant Joan de les Abadesses', 'Campdevànol', 'Camprodon', 'Gombrèn', 'Llanars', 'Molló', 'Ogassa', 'Pardines', 'Planoles', 'Queralbs', 'Ribes de Freser', 'Sant Pau de Segúries', 'Setcases', 'Toses', 'Vallfogona de Ripollès', 'Vilallonga de Ter'
              ],
              'Selva': ['Amer', 'Anglès', 'Arbúcies', 'Blanes', 'Breda', 'Brunyola i Sant Martí Sapresa', 'Caldes de Malavella', 'Cellera de Ter, la', 'Fogars de la Selva', 'Hostalric', 'Lloret de Mar', 'Maçanet de la Selva', 'Massanes', 'Osor', 'Riells i Viabrea', 'Riudarenes', 'Riudellots de la Selva', 'Sant Feliu de Buixalleu', 'Sant Hilari Sacalm', 'Sant Julià del Llor i Bonmatí', 'Santa Coloma de Farners', 'Sils', 'Susqueda', 'Tossa de Mar', 'Vidreres', 'Vilobí d\'Onyar'
              ],
              'Alt Urgell': ['La Seu d\'Urgell', 'Oliana', 'Arsèguel', 'Bassella', 'Cabó', 'Cava', 'Coll de Nargó', 'Estamariu', 'Fígols i Alinyà', 'Josa i Tuixén', 'Montferrer i Castellbò', 'Organyà', 'Peramola', 'Ribera d\'Urgellet', 'Valls d\'Aguilar, les', 'Valls de Valira, les', 'Vansa i Fórnols, la'
              ],
              'Alta Ribagorça': ['El Pont de Suert', 'Vilaller', 'Vall de Boí, la'
              ],
              'Garrigues': ['Les Borges Blanques', 'Juneda', 'Arbeca', 'Bellaguarda', 'Bovera', 'Cervià de les Garrigues', 'Castelldans', 'Cogul, el', 'Espluga Calba, l\'', 'Floresta, la', 'Fulleda', 'Granyena de les Garrigues', 'Juncosa', 'L\'Albagés', 'L\'Albi', 'L\'Espluga de Francolí', 'L\'Espluga de Serra'
              ],
              'Noguera': ['Balaguer', 'Àger', 'Albesa', 'Algerri', 'Alòs de Balaguer', 'Artesa de Segre', 'Baronia de Rialb, la', 'Bellcaire d\'Urgell', 'Bellmunt d\'Urgell', 'Cabanabona', 'Castelló de Farfanya', 'Cubells', 'Foradada', 'Ivars de Noguera', 'Menàrguens', 'Montgai', 'Os de Balaguer', 'Penelles', 'Ponts', 'Preixens', 'Térmens', 'Tiurana', 'Torrelameu', 'Vallfogona de Balaguer', 'Vilanova de Meià', 'Vilanova de l\'Aguda'
              ],
              'Pallars Jussà': ['Tremp', 'La Pobla de Segur', 'Abella de la Conca', 'Conca de Dalt', 'Gavet de la Conca', 'Isona i Conca Dellà', 'Llimiana', 'Salàs de Pallars', 'Sant Esteve de la Sarga', 'Sarroca de Bellera', 'Senterada', 'Talarn', 'Torre de Capdella, la'
              ],
              'Pallars Sobirà': ['Sort', 'Rialp', 'Alins', 'Alt Àneu', 'Baix Pallars', 'Espot', 'Esterri d\'Àneu', 'Esterri de Cardós', 'Farrera', 'Guingueta d\'Àneu, la', 'Llavorsí', 'Soriguera', 'Tírvia', 'Vall de Cardós'
              ],
              'Pla d\'Urgell': ['Mollerussa', 'Bell-lloc d\'Urgell', 'Barbens', 'Castellnou de Seana', 'Fondarella', 'Golmés', 'Ivars d\'Urgell', 'Linyola', 'Miralcamp', 'Palau d\'Anglesola, el', 'Poal, el', 'Sidamon', 'Torregrossa', 'Vilanova de Bellpuig', 'Vila-sana'
              ],
              'Segarra': ['Cervera', 'Guissona', 'Biosca', 'Estaràs', 'Granyanella', 'Granyena de Segarra', 'Massoteres', 'Montoliu de Segarra', 'Montornès de Segarra', 'Oluges, les', 'Plans de Sió, els', 'Ribera d\'Ondara', 'Sant Guim de Freixenet', 'Sant Ramon', 'Sanaüja', 'Talavera', 'Tarroja de Segarra', 'Torà'
              ],
              'Segrià': ['Lleida', 'Alcarràs', 'Aitona', 'Albatàrrec', 'Alcanó', 'Alfarràs', 'Alfés', 'Alguaire', 'Almacelles', 'Almatret', 'Almenar', 'Alpicat', 'Artesa de Lleida', 'Aspa', 'Benavent de Segrià', 'Corbins', 'Gimenells i el Pla de la Font', 'Llardecans', 'Maials', 'Massalcoreig', 'Montoliu de Lleida', 'Puigverd de Lleida', 'Sarroca de Lleida', 'Seròs', 'Soses', 'Sudanell', 'Sunyer', 'Torrebesses', 'Torrefarrera', 'Torres de Segre', 'Vilanova de Segrià', 'Vila-sana'
              ],
              'Solsonès': ['Solsona', 'Sant Llorenç de Morunys', 'Castellar de la Ribera', 'Clariana de Cardener', 'Lladurs', 'Llobera', 'La Molsosa', 'Navès', 'Odèn', 'Olius', 'Pinell de Solsonès', 'Pinós', 'Riner', 'La Coma i la Pedra'
              ],
              'Urgell': ['Tàrrega', 'Agramunt', 'Anglesola', 'Bellpuig', 'Castellserà', 'Ciutadilla', 'Guimerà', 'Maldà', 'Belianes', 'Preixana', 'Sant Martí de Riucorb', 'Verdú', 'Vila-sana'
              ],
              'Vall d\'Aran': ['Vielha e Mijaran', 'Naut Aran', 'Arres', 'Bausen', 'Bossòst', 'Es Bòrdes', 'Les', 'Vilamòs', 'Vilac'
              ],
              'Alt Camp': ['Aiguamúrcia','Alcover','Alió','Bràfim','Cabra del Camp','Figuerola del Camp','Garidells, els','Masó, la','Milà, el','Montferri','Mont-ral','Nulles','Pla de Santa Maria, el','Pont d\'Armentera, el','Puigpelat','Querol','Riba, la','Rodonyà','Rourell, el','Vallmoll','Valls','Vilabella','Vila-rodona'
              ],
              'Baix Camp': ['Reus', 'Cambrils', 'Mont-roig del Camp', 'Vandellòs i l\'Hospitalet de l\'Infant', 'Riudoms', 'Vinyols i els Arcs', 'Les Borges del Camp', 'Alforja', 'Botarell', 'Castellvell del Camp', 'Duesaigües', 'L\'Aleixar', 'L\'Argentera', 'L\'Espluga de Francolí', 'La Febró', 'La Selva del Camp', 'L\'Aleixar', 'Maspujols', 'Montbrió del Camp', 'Prades', 'Riudecanyes', 'Riudecols', 'Vilanova d\'Escornalbou'
              ],
              'Baix Ebre': ['Tortosa', 'L\'Aldea', 'L\'Ampolla', 'Camarles', 'Deltebre', 'Paüls', 'Roquetes', 'Tivenys', 'Xerta', 'Benifallet', 'El Perelló', 'Freginals', 'Godall', 'Masdenverge', 'Santa Bàrbara'
              ],
              'Baix Penedès': ['El Vendrell', 'Calafell', 'Cunit', 'L\'Arboç', 'Bellvei', 'Banyeres del Penedès', 'Llorenç del Penedès', 'Sant Jaume dels Domenys', 'Santa Oliva', 'La Bisbal del Penedès', 'Albinyana', 'Bonastre', 'Masllorenç'
              ],
              'Conca de Barberà': ['Montblanc', 'Santa Coloma de Queralt', 'Barberà de la Conca', 'Blancafort', 'Conesa', 'L\'Espluga de Francolí', 'Forès', 'Llorac', 'Passanant i Belltall', 'Pira', 'Pontils', 'Rocafort de Queralt', 'Sarral', 'Savallà del Comtat', 'Senan', 'Solivella', 'Vallclara', 'Vallfogona de Riucorb', 'Vilanova de Prades', 'Vilaverd'
              ],
              'Montsià': [ 'Amposta', 'Alcanar', 'Freginals', 'Godall', 'La Galera', 'Masdenverge', 'Mas de Barberans', 'Santa Bàrbara','Sant Carles de la Ràpita','Ulldecona'
              ],
              'Priorat': ['Falset', 'Gratallops', 'Bellmunt del Priorat', 'Bisbal de Falset', 'Cabacés', 'Capçanes', 'Cornudella de Montsant', 'La Figuera', 'La Morera de Montsant', 'La Vilella Alta', 'La Vilella Baixa', 'Lloar', 'Margalef', 'Marçà', 'Poboleda', 'Porrera', 'Pradell de la Teixeta', 'Torroja del Priorat', 'Ulldemolins'
              ],
              'Ribera d\'Ebre': ['Móra d\'Ebre', 'Flix', 'Ascó', 'Benissanet', 'Ginestar', 'Miravet', 'Móra la Nova', 'Rasquera', 'Riba-roja d\'Ebre', 'Tivissa', 'La Torre de l\'Espanyol', 'Vinebre'
              ],
              'Tarragonès': ['Tarragona', 'Salou', 'Altafulla', 'Constantí', 'Creixell', 'El Catllar', 'La Canonja', 'La Nou de Gaià', 'La Pobla de Mafumet', 'La Pobla de Montornès', 'Perafort', 'Els Pallaresos', 'Roda de Berà', 'Salomó', 'Torredembarra', 'Vespella de Gaià', 'Vila-seca', 'Vilallonga del Camp'
              ],
              'Terra Alta': ['Gandesa', 'Batea', 'Arnes', 'Bot', 'Caseres', 'Corbera d\'Ebre', 'La Fatarella', 'Horta de Sant Joan', 'Pinell de Brai', 'Prat de Comte', 'Vilalba dels Arcs'
              ],
            };

            document.getElementById('provincia-select').addEventListener('change', function() {
              const provincia = this.value;
              const comarcaSelect = document.getElementById('comarca-select');
              const municipiSelect = document.getElementById('municipi-select');

              // Clear previous options
              comarcaSelect.innerHTML = '';
              municipiSelect.innerHTML = '';

            // Populate comarca options
            if (comarques[provincia]) {
              const defaultOption = document.createElement('option');
              defaultOption.value = '';
              defaultOption.text = 'Select Comarca';
              comarcaSelect.appendChild(defaultOption);

              comarques[provincia].forEach(function(comarca) {
                const option = document.createElement('option');
                option.value = comarca;
                option.text = comarca;
                comarcaSelect.appendChild(option);
              });
            }

            // Add initial blank value for municipi
            const defaultMunicipiOption = document.createElement('option');
            defaultMunicipiOption.value = '';
            defaultMunicipiOption.text = 'Select Municipi';
            municipiSelect.appendChild(defaultMunicipiOption);
                      });

                      document.getElementById('comarca-select').addEventListener('change', function() {
            const comarca = this.value;
            const municipiSelect = document.getElementById('municipi-select');

            // Clear previous options
            municipiSelect.innerHTML = '';

            // Populate municipi options
            if (municipis[comarca]) {
              const defaultOption = document.createElement('option');
              defaultOption.value = '';
              defaultOption.text = 'Select Municipi';
              municipiSelect.appendChild(defaultOption);

              municipis[comarca].forEach(function(municipi) {
                const option = document.createElement('option');
                option.value = municipi;
                option.text = municipi;
                municipiSelect.appendChild(option);
              });
            }
                      });
          </script>
