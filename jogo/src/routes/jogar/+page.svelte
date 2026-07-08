<script>
    
    let selecionando = false;
    let selecao = [];
    let palavrasEncontradas = [];
    let direcaoAtual = null;
    const tamanho = 15;

    const palavras = [
        "JAVA",
        "PHP",
        "PYTHON",
        "JAVASCRIPT",
        "CPP",
        "CSHARP",
        "GO",
        "RUST",
        "SWIFT",
        "KOTLIN",
        "DART",
        "RUBY",
        "SQL"
    ];

    // cores para cada palavra (index correspondendo ao índice em `palavras`)
    const cores = [
        '#E53935', '#8E24AA', '#3949AB', '#1E88E5', '#00ACC1', '#00897B', '#43A047', '#7CB342', '#C0CA33', '#FDD835', '#FB8C00', '#6D4C41', '#78909C'
    ];

    function getCor(palavra) {
        if (!palavra) return '';
        const idx = palavras.indexOf(palavra);
        if (idx === -1) return '';
        return cores[idx % cores.length];
    }

    const direcoes = [
        { x: 1, y: 0 },   // Horizontal →
        { x: 0, y: 1 },   // Vertical ↓
        { x: 1, y: 1 },   // Diagonal ↘
        { x: -1, y: 1 }   // Diagonal ↙
    ];


    let grade = [];

    function criarGrade() {
        grade = [];

        for (let y = 0; y < tamanho; y++) {
            let linha = [];

            for (let x = 0; x < tamanho; x++) {
                linha.push({
                    letra: "",
                    selecionada: false,
                    encontrada: false,
                    palavra: null
                });
            }

            grade.push(linha);
        }
    }

    function cabePalavra(palavra, x, y, dx, dy) {

        for (let i = 0; i < palavra.length; i++) {

            const nx = x + dx * i;
            const ny = y + dy * i;

            if (
                nx < 0 ||
                ny < 0 ||
                nx >= tamanho ||
                ny >= tamanho
            ) {
                return false;
            }

            const letraAtual = grade[ny][nx].letra;

            if (
                letraAtual !== "" &&
                letraAtual !== palavra[i]
            ) {
                return false;
            }

        }

        return true;
    }

    function colocarPalavra(palavra) {

        let colocada = false;
        let tentativas = 0;

        while (!colocada && tentativas < 300) {

            tentativas++;

            const direcao =
                direcoes[Math.floor(Math.random() * direcoes.length)];

            const x = Math.floor(Math.random() * tamanho);
            const y = Math.floor(Math.random() * tamanho);

            if (
                cabePalavra(
                    palavra,
                    x,
                    y,
                    direcao.x,
                    direcao.y
                )
            ) {

                for (let i = 0; i < palavra.length; i++) {

                    const nx = x + direcao.x * i;
                    const ny = y + direcao.y * i;

                    grade[ny][nx].letra = palavra[i];
                    grade[ny][nx].palavra = palavra;

                }

                colocada = true;
            }

        }

    }


    function preencherLetras() {

        const alfabeto = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";

        for (let y = 0; y < tamanho; y++) {

            for (let x = 0; x < tamanho; x++) {

                if (grade[y][x].letra === "") {

                    grade[y][x].letra =
                        alfabeto[
                            Math.floor(Math.random() * alfabeto.length)
                        ];

                }

            }

        }

    }
    function iniciar(){criarGrade();
    palavras.forEach(p => colocarPalavra(p));
    preencherLetras();}

    iniciar();
    

function iniciarSelecao(x, y) {
    console.log("clicou")
    limparSelecao();

    selecionando = true;
    direcaoAtual = null;

    grade[y][x].selecionada = true;
    grade = [...grade];

    selecao.push({
        x,
        y,
        letra: grade[y][x].letra
    });

}
function obterDirecao(x1, y1, x2, y2) {

    let dx = x2 - x1;
    let dy = y2 - y1;

    dx = Math.sign(dx);
    dy = Math.sign(dy);

    return { dx, dy };

}
function arrastarSelecao(x, y) {
    console.log("arrastou")
    if (!selecionando) return;

    if (grade[y][x].encontrada) return;

    const existe = selecao.some(
        l => l.x === x && l.y === y
    );

    if (existe) return;

    

    if (selecao.length === 1) {

        const primeira = selecao[0];

        direcaoAtual = obterDirecao(
            primeira.x,
            primeira.y,
            x,
            y
        );

    }


    if (selecao.length >= 2) {

        const ultima = selecao[selecao.length - 1];

        const dx = x - ultima.x;
        const dy = y - ultima.y;

        if (
            Math.sign(dx) !== direcaoAtual.dx ||
            Math.sign(dy) !== direcaoAtual.dy
        ) {
            return;
        }

    }

    grade[y][x].selecionada = true;

    selecao.push({
        x,
        y,
        letra: grade[y][x].letra
    });
    grade = [...grade];

}
function finalizarSelecao() {

    if (!selecionando) return;

    selecionando = false;

    verificarSelecao();

}
function limparSelecao() {

    selecao.forEach(l => {
        grade[l.y][l.x].selecionada = false;
    });
    grade = [...grade];

    selecao = [];

}
function verificarSelecao() {

    const palavra =
        selecao.map(l => l.letra).join("");

    const invertida =
        palavra.split("").reverse().join("");

    if (palavras.includes(palavra)) {

        marcarEncontrada(palavra);

    }
    else if (palavras.includes(invertida)) {

        marcarEncontrada(invertida);

    }
    else {

        limparSelecao();

    }
    

}
function marcarEncontrada(nome) {

    // garantir reatividade em Svelte ao atualizar o array
    palavrasEncontradas = [...palavrasEncontradas, nome];

    selecao.forEach(l => {
        grade[l.y][l.x].encontrada = true;
        grade[l.y][l.x].selecionada = false;
    });

    selecao = [];
    grade = [...grade];

}
    </script>
<div class="container">
    <a class="back-button" href="/">BACK</a>    

    <h1>Caça-Palavras</h1>

    <div class="painel">

        <div class="tabuleiro">

            {#each grade as linha, y}

                <div class="linha">

                    {#each linha as celula, x}

                        <div
                            class="letra"
                            class:selecionada={celula.selecionada}
                            class:encontrada={celula.encontrada}
                            style={celula.encontrada ? `background: ${getCor(celula.palavra)}; color: white;` : ''}

                            on:mousedown={() => iniciarSelecao(x,y)}
                            on:mouseenter={() => arrastarSelecao(x,y)}
                        >
                            {celula.letra}
                        </div>

                    {/each}

                </div>

            {/each}

        </div>

        <div class="lista">

            <h2>Palavras</h2>

            <ul>

                {#each palavras as palavra}

                    <li
                        class:encontrada={palavrasEncontradas.includes(palavra)}
                        style={palavrasEncontradas.includes(palavra) ? `color: ${getCor(palavra)}; text-decoration: line-through;` : ''}
                    >
                        {palavra}
                    </li>

                {/each}

            </ul>

        </div>

    </div>

</div>

<svelte:window on:mouseup={finalizarSelecao}/>