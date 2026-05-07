<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Huerto Inteligente</title>
    <!-- Cargamos la librería MQTT -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/paho-mqtt/1.0.1/mqttws31.min.js" type="text/javascript"></script>
    
    <style>
        body { font-family: sans-serif; text-align: center; padding: 20px; background-color: #f0f2f5; }
        .card { background: white; padding: 20px; border-radius: 15px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); display: inline-block; }
        .btn { padding: 15px 25px; margin: 10px; border: none; border-radius: 8px; cursor: pointer; font-weight: bold; color: white; }
        .on { background-color: #28a745; }
        .off { background-color: #dc3545; }
        #status { font-weight: bold; margin-bottom: 20px; }
        .temp-val { font-size: 2em; color: #007bff; }
    </style>
</head>
<body>

    <div class="card">
        <h1>🌱 Mi Huerto</h1>
        <div id="status">⏳ Conectando...</div>
        
        <hr>
        
        <h3>Temperatura</h3>
        <div class="temp-val" id="temp">--°C</div>
        
        <hr>
        
        <h3>Controles</h3>
        <button id="btn0" class="btn off" onclick="toggle(0)">BOMBA 1</button>
        <button id="btn1" class="btn off" onclick="toggle(1)">BOMBA 2</button>
        <button id="btn2" class="btn off" onclick="toggle(2)">LUCES</button>
    </div>

    <script>
        const TOPIC_PREFIX = "CVH_HUERTO";
        let estados = [false, false, false];

        // 1. CONFIGURACIÓN DEL CLIENTE (Puerto 8884 y Path /mqtt para seguridad)
        const client = new Paho.MQTT.Client("broker.hivemq.com", 8884, "/mqtt", "web_user_" + Math.random());

        // Manejo de desconexión
        client.onConnectionLost = (resp) => { 
            document.getElementById('status').innerHTML = "❌ Desconectado: " + resp.errorMessage; 
            document.getElementById('status').style.color = "red";
        };
        
        // Manejo de mensajes entrantes (Temperatura)
        client.onMessageArrived = (msg) => {
            if(msg.destinationName === TOPIC_PREFIX + "/telemetria/temp") {
                document.getElementById('temp').innerHTML = msg.payloadString + "°C";
            }
        };

        // 2. OPCIONES DE CONEXIÓN CON SSL (Obligatorio para GitHub Pages)
        const options = {
            useSSL: true, 
            timeout: 3,
            onSuccess: () => {
                document.getElementById('status').innerHTML = "🟢 Conectado (Seguro)";
                document.getElementById('status').style.color = "green";
                // Nos suscribimos al tópico de temperatura
                client.subscribe(TOPIC_PREFIX + "/telemetria/temp");
            },
            onFailure: (err) => {
                document.getElementById('status').innerHTML = "❌ Error de conexión: " + err.errorMessage;
                document.getElementById('status').style.color = "red";
            }
        };

        // 3. CONECTAR
        client.connect(options);

        // Función para los botones
        function toggle(id) {
            estados[id] = !estados[id];
            const val = estados[id] ? "1" : "0";
            const btn = document.getElementById('btn' + id);
            
            const message = new Paho.MQTT.Message(val);
            message.destinationName = TOPIC_PREFIX + "/control/" + id;
            client.send(message);

            btn.className = estados[id] ? "btn on" : "btn off";
        }
    </script>
</body>
</html>
