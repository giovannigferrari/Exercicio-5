<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>4Cálculo de Custo para Assentar Piso</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        input, button {
            padding: 10px;
            margin: 5px;
        }
        .result {
            margin-top: 20px;
        }
        .container{
            align-items: center;
            align-content: center;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
    <h1>Calculadora de Custo para Assentar Piso</h1>
    <label for="comprimento">Informe o comprimento do cômodo (em metros):</label>
    <input type="number" id="comprimento" placeholder="Comprimento (m)" step="0.01" />
    <label for="largura">Informe a largura do cômodo (em metros):</label>
    <input type="number" id="largura" placeholder="Largura (m)" step="0.01" />
    <button onclick="calcularCusto()">Calcular Custo</button>
    <div class="result">
        <p>Área total: <span id="areaTotal"></span> m²</p>
        <p>Custo total: R$ <span id="custoTotal"></span></p>
    </div>
    </div>
    <script>
        function calcularCusto() {
            const comprimento = parseFloat(document.getElementById('comprimento').value);
            const largura = parseFloat(document.getElementById('largura').value);
            if (isNaN(comprimento) || isNaN(largura) || comprimento <= 0 || largura <= 0) {
                alert("Por favor, insira valores válidos para o comprimento e a largura.");
                return;
            }
            const areaTotal = comprimento * largura;
            document.getElementById('areaTotal').textContent = areaTotal.toFixed(2);
            const precoPorMetroQuadrado = 36;
            const custoTotal = areaTotal * precoPorMetroQuadrado;
            document.getElementById('custoTotal').textContent = custoTotal.toFixed(2);
        }
    </script>
</body>
</html>
 
