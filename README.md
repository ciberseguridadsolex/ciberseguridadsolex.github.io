<title>Has mordido el anzuelo3</title> <style> body { background-color: black; color: white; } </style>
Has mordido el anzuelo
<main>
    <section>
        <p>Lamentamos informarte que has sido víctima de un intento de phishing. Tu información ha sido comprometida <a href="https://rb.gy/799bl">
          <img src="https://drive.google.com/uc?id=1wchi4XR7w5Tuh2Qx-54_RuSbFhfltr4R" alt="Imagen de phishing" />
        </a> </p>
    </section>
    <section>
        <p>Número de visitante: <span id="visitorNumber"></span></p>
        <p>Dirección IP del visitante: <span id="visitorIP"></span></p>
        <p>Hora de la visita: <span id="visitTime"></span></p>
        <p>Ubicación de la IP: <span id="ipLocation"></span></p>
    </section>
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
