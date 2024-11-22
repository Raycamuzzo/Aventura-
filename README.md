# Aventura-
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aventura: Rumo à Cidade Perdida</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div id="game-container">
        <h1>Aventura: Rumo à Cidade Perdida</h1>
        <p>Siga as pistas e desvende os mistérios!</p>
        <div id="story">
            <p>Escolha o caminho inicial: </p>
            <button onclick="escolherCaminho('rio')">Rio de Janeiro</button>
            <button onclick="escolherCaminho('amazonas')">Amazonas</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    text-align: center;
    background-color: #f4f4f4;
    margin: 0;
    padding: 20px;
}

#game-container {
    max-width: 800px;
    margin: auto;
    padding: 20px;
    background: white;
    border: 1px solid #ddd;
    border-radius: 10px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

h1 {
    color: #333;
}

button {
    margin: 5px;
    padding: 10px 20px;
    background: #0066cc;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background: #004999;
}

img {
    max-width: 100%;
    border-radius: 10px;
}
function escolherCaminho(caminho) {
    const story = document.getElementById('story');

    if (caminho === 'rio') {
        story.innerHTML = `
            <p>Você está no Rio de Janeiro! Deseja procurar pistas no topo do pico?</p>
            <button onclick="escolherCaminho('pico')">Procurar no topo do pico</button>
            <button onclick="escolherCaminho('desistir')">Desistir</button>
        `;
    } else if (caminho === 'amazonas') {
        story.innerHTML = `
            <p>Você está no Amazonas! Seguir pelo rio à esquerda?</p>
            <button onclick="escolherCaminho('cidade')">Explorar cidade perdida</button>
            <button onclick="escolherCaminho('voltar')">Voltar</button>
        `;
    } else if (caminho === 'pico') {
        story.innerHTML = `
            <p>Você encontrou uma pista que leva ao Amazonas. Deseja continuar?</p>
            <button onclick="escolherCaminho('amazonas')">Ir para o Amazonas</button>
        `;
    } else if (caminho === 'cidade') {
        story.innerHTML = `
            <p>Parabéns! Você encontrou a cidade perdida!</p>
            <img src="img/cenario-passo11-cidade-perdida.png" alt="Cidade Perdida">
            <button onclick="reiniciar()">Recomeçar</button>
        `;
    } else if (caminho === 'desistir' || caminho === 'voltar') {
        story.innerHTML = `
            <p>Você desistiu da aventura. Fim de jogo.</p>
            <button onclick="reiniciar()">Recomeçar</button>
        `;
    }
}

function reiniciar() {
    location.reload();
}
