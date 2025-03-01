<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mapa Romântico e Lugares a Visitar</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #ffe6e6;
        }
        #mapa {
            width: 80%;
            height: 500px;
            margin: 20px auto;
            border: 2px solid #ff4d4d;
        }
        h1 {
            color: #e60000;
            font-size: 3em;
            margin-top: 20px;
        }
        h2 {
            color: #cc3333;
            font-size: 2em;
        }
        .content {
            max-width: 900px;
            margin: 30px auto;
            padding: 20px;
            background-color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
            text-align: justify;
        }
        .place {
            margin-top: 20px;
        }
        .place h3 {
            color: #ff4d4d;
            font-size: 1.8em;
        }
        .place p {
            font-size: 1.1em;
            line-height: 1.5;
        }
        .highlight {
            font-weight: bold;
            color: #e60000;
        }
    </style>
</head>
<body>

    <h1>Explora os Lugares Românticos da Europa</h1>
    
    <div class="content">
        <p>Descobre os destinos mais românticos da Europa com o nosso mapa interativo. Clica nos pontos do mapa para saber mais sobre cada lugar e planeia a tua próxima aventura romântica!</p>

        <!-- Portugal -->
        <div class="place">
            <h3>1. Portugal - A Terra do Romance</h3>
            <p>Portugal é um destino repleto de charme e beleza. Desde as <span class="highlight">ruas históricas de Lisboa</span> até os <span class="highlight">vignobles do Douro</span> e as praias deslumbrantes do Algarve, o país é um cenário perfeito para uma escapadela romântica. Explore a <span class="highlight">Baixa de Lisboa</span> e o <span class="highlight">Alfama</span>, com as suas vistas panorâmicas sobre o rio Tejo, ou descubra a tranquilidade das vilas costeiras do <span class="highlight">Algarve</span>.</p>
        </div>
    </div>

    <div id="mapa"></div>

    <script>
        function initMap() {
            var map = new google.maps.Map(document.getElementById('mapa'), {
                center: { lat: 38.7169, lng: -9.1399 }, // Lisboa (ou muda para outra cidade)
                zoom: 12
            });

            // Lugares românticos em Lisboa
            var locais = [
                { 
                    nome: "Miradouro de Santa Catarina", 
                    lat: 38.7114, 
                    lng: -9.1452, 
                    descricao: "Um dos melhores pontos para ver o pôr do sol em Lisboa!" 
                },
                { 
                    nome: "Jardim Botânico", 
                    lat: 38.7163, 
                    lng: -9.1449, 
                    descricao: "Um local encantador para um passeio romântico no centro de Lisboa." 
                },
                { 
                    nome: "Parque Eduardo VII", 
                    lat: 38.7273, 
                    lng: -9.1524, 
                    descricao: "Perfeito para relaxar e apreciar a vista panorâmica de Lisboa." 
                },
                { 
                    nome: "Alfama", 
                    lat: 38.7102, 
                    lng: -9.1332, 
                    descricao: "O bairro histórico de Lisboa, onde as ruas estreitas e as tradições se encontram." 
                },
                { 
                    nome: "Praia da Ursa", 
                    lat: 38.7452, 
                    lng: -9.4972, 
                    descricao: "Uma praia isolada, ideal para quem procura privacidade e beleza natural." 
                }
            ];

            locais.forEach(local => {
                var marker = new google.maps.Marker({
                    position: { lat: local.lat, lng: local.lng },
                    map: map,
                    title: local.nome
                });

                var infoWindow = new google.maps.InfoWindow({
                    content: `<h3>${local.nome}</h3><p>${local.descricao}</p>`
                });

                marker.addListener("click", () => {
                    infoWindow.open(map, marker);
                });
            });
        }
    </script>

    <!-- Google Maps Script (Replace YOUR_API_KEY with your actual API key) -->
    <script async defer
    src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap">
    </script>
</body>
</html>
