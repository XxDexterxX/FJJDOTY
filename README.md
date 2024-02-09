<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FJJDOTY</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-image: url('img/background2.jpg');
            background-size: cover;
            background-repeat: no-repeat;
            background-attachment: fixed;
            color: white; /* Cor do texto principal */
        }
        h2 {
            color: rgb(255, 255, 255); /* Cor do título principal */
        }
        label {
            color: rgb(255, 255, 255); /* Cor dos rótulos */
        }
        #resultado {
            color: rgb(234, 255, 0); /* Cor do resultado */
        }
        #banner {
            margin-top: 20px;
            border: 1px solid #ccc;
            padding: 10px;
        }
    </style>
</head>
<body>
    <img src="img/ffj.png" alt="Logo da Empresa" width="200"><br><br>
    <h2>Apostas</h2>
    <label for="time">Escolha o time:</label>
    <select id="time">
        <option value="Real Madrid">Real Madrid</option>
        <option value="Barcelona">Barcelona</option>
        <option value="Manchester United">Manchester United</option>
        <option value="Liverpool">Liverpool</option>
        <!-- Adicione mais opções de times conforme necessário -->
    </select><br><br>
    <label for="aposta">Valor da Aposta:</label>
    <input type="number" id="aposta" min="0"><br><br>
    <button onclick="calcularGanhos()">Calcular Ganhos</button><br><br>
    <div id="resultado"></div>

    <div id="banner">
        <img src="banner/2.png" alt="Banner Publicitário" width="400">
        <img src="banner/Gif.gif" alt="Banner Publicitário" width="400">
        <img src="banner/3.png" alt="Banner Publicitário" width="400">
    </div>

    <script>
        function calcularGanhos() {
            var timeSelecionado = document.getElementById("time").value;
            var valorAposta = parseFloat(document.getElementById("aposta").value);

            // Odds (probabilidades) fixas para os times (apenas um exemplo)
            var oddsRealMadrid = 1.5;
            var oddsBarcelona = 2.0;
            var oddsManchesterUnited = 2.5;
            var oddsLiverpool = 3.0;

            var ganhos;

            // Calcula os ganhos com base nas odds e no valor da aposta
            switch (timeSelecionado) {
                case "Real Madrid":
                    ganhos = valorAposta * oddsRealMadrid;
                    break;
                case "Barcelona":
                    ganhos = valorAposta * oddsBarcelona;
                    break;
                case "Manchester United":
                    ganhos = valorAposta * oddsManchesterUnited;
                    break;
                case "Liverpool":
                    ganhos = valorAposta * oddsLiverpool;
                    break;
                default:
                    ganhos = 0;
                    break;
            }

            document.getElementById("resultado").innerHTML = "Se você apostar $" + valorAposta.toFixed(2) + " no " + timeSelecionado + ", seus ganhos serão de $" + ganhos.toFixed(2) + ".";
        }
    </script>
</body>
</html>
