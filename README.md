<html>
<head>
    <meta charset="UTF-8">
    <title>Has mordido el anzuelo </title>
    <style>
        body {
            background-color: black;
            color: white;
        }

        #banner {
            background-color: red; /* Color de fondo del banner */
            text-align: center;
            padding: 10px; /* Espaciado interior del banner */
            font-size: 24px; /* Tamaño del texto del banner */
        }
    </style>
</head>
<body>
<div id="banner">Has mordido el anzuelo</div>
<main>
    <!-- El contenido principal de tu página va aquí -->
</main>
<footer>
    <p>&copy; Ciberseguridad 2023</p>
</footer>
<script>
    // JavaScript para obtener y mostrar el número de visitante, dirección IP, hora de la visita y geolocalización
    var visitorNumber = localStorage.getItem('visitorNumber');
    var visitorIP = "";

    // Incrementa el número de visitante
    if (!visitorNumber) {
        visitorNumber = 1;
    } else {
        visitorNumber = parseInt(visitorNumber) + 1;
    }

    // Obtiene la dirección IP del visitante utilizando un servicio externo (ipify.org)
    fetch('https://api.ipify.org?format=json')
        .then(response => response.json())
        .then(data => {
            visitorIP = data.ip;
            // Muestra la dirección IP en el HTML
            document.getElementById('visitorIP').textContent = visitorIP;

            // Obtiene la geolocalización de la dirección IP
            fetch('http://ip-api.com/json/' + visitorIP)
                .then(response => response.json())
                .then(data => {
                    // Muestra la ubicación en el HTML
                    var location = data.country + ', ' + data.regionName + ', ' + data.city;
                    document.getElementById('ipLocation').textContent = location;
                })
                .catch(error => console.error(error));
        })
        .catch(error => console.error(error));

    // Obtiene la hora actual
    var visitTime = new Date();
    var visitTimeString = visitTime.toLocaleString();

    // Almacena el número de visitante y la hora de la visita en el almacenamiento local
    localStorage.setItem('visitorNumber', visitorNumber);

    // Muestra el número de visitante y la hora de la visita en el HTML
    document.getElementById('visitorNumber').textContent = visitorNumber;
    document.getElementById('visitTime').textContent = visitTimeString;
</script>
</body>
</html>

