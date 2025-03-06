<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seleziona un numero</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
        }
        .container {
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        input {
            margin: 10px;
            padding: 5px;
            font-size: 1em;
        }
        button {
            margin-top: 10px;
            padding: 10px 20px;
            font-size: 1em;
            border: none;
            background-color: #4CAF50;
            color: white;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        .message {
            margin-top: 15px;
            font-weight: bold;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Inserisci un numero tra A e B</h1>
    <label for="numA">Numero A:</label>
    <input type="number" id="numA" placeholder="Inserisci A"><br>

    <label for="numB">Numero B:</label>
    <input type="number" id="numB" placeholder="Inserisci B"><br>

    <label for="numScelto">Numero Scelto:</label>
    <input type="number" id="numScelto" placeholder="Inserisci il numero scelto"><br>

    <button onclick="verificaNumero()">Verifica Numero</button>

    <div id="result" class="message"></div>
</div>

<script>
    function verificaNumero() {
        const numA = parseInt(document.getElementById('numA').value);
        const numB = parseInt(document.getElementById('numB').value);
        const numScelto = parseInt(document.getElementById('numScelto').value);
        const resultDiv = document.getElementById('result');

        // Controllo che i valori di A e B siano validi
        if (isNaN(numA) || isNaN(numB)) {
            resultDiv.textContent = "Per favore, inserisci valori validi per A e B.";
            resultDiv.style.color = "red";
            return;
        }

        // Verifica se A è maggiore di B, in tal caso li scambiamo
        let min = Math.min(numA, numB);
        let max = Math.max(numA, numB);

        // Controllo se il numero scelto è tra A e B
        if (numScelto >= min && numScelto <= max) {
            resultDiv.textContent = "Hai scelto il numero: " + numScelto;
            resultDiv.style.color = "green";
        } else {
            resultDiv.textContent = "Il numero scelto non è tra " + min + " e " + max + ". Riprova.";
            resultDiv.style.color = "red";
        }
    }
</script>

</body>
</html>
