# primeiro_1d
html e css<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biotecnologia Sustentável no Campo</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <div class="container">
            <h1>BioAgro Tech</h1>
            <p>O Futuro Sustentável da Agricultura Através da Biotecnologia</p>
        </div>
    </header>

    <main class="container">
        <section class="intro">
            <h2>Inovação Verde para Alimentar o Mundo</h2>
            <p>A biotecnologia agrícola surge como o pilar fundamental para a sustentabilidade no campo, unindo a produtividade necessária com a preservação ambiental que o planeta exige.</p>
        </section>

        <section class="cards-section">
            <div class="card" onclick="mostrarDetalhes('edicao')">
                <div class="icon">🧬</div>
                <h3>Edição Genética (CRISPR)</h3>
                <p>Desenvolvimento de sementes altamente resistentes à seca e pragas sem a necessidade de defensivos químicos.</p>
            </div>

            <div class="card" onclick="mostrarDetalhes('bioinsumos')">
                <div class="icon">🍃</div>
                <h3>Bioinsumos</h3>
                <p>Uso de microrganismos vivos, bactérias e fungos benéficos para fertilizar o solo e proteger as plantas de forma natural.</p>
            </div>

            <div class="card" onclick="mostrarDetalhes('verticais')">
                <div class="icon">🏢</div>
                <h3>Fazendas Verticais</h3>
                <p>Cultivos urbanos controlados hidroponicamente que reduzem o uso de água em até 95% e eliminam o desmatamento.</p>
            </div>
        </section>

        <section id="detalhe-painel" class="detalhe-painel escondido">
            <div class="detalhe-conteudo">
                <h3 id="detalhe-titulo">Título do Painel</h3>
                <p id="detalhe-texto">Texto detalhado sobre a tecnologia selecionada.</p>
                <button onclick="fecharDetalhes()">Fechar Informações</button>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 BioAgro Tech. Tecnologia a serviço da natureza.</p>
    </footer>

    <script src="script.js"></script>
</body>// Banco de dados simulado para alimentar a interatividade da página
const informacoesTecnologicas = {
    edicao: {
        titulo: "Edição Genética (CRISPR-Cas9)",
        texto: "Diferente dos transgênicos tradicionais que recebem genes de outras espécies, a edição via CRISPR modifica o próprio DNA da planta de forma ultra precisa. Isso permite acelerar processos de seleção natural, criando culturas idênticas às originais, porém capazes de sobreviver com muito menos água e resistir a pragas severas de forma nativa, diminuindo drasticamente a necessidade de agroquímicos."
    },
    bioinsumos: {
        titulo: "Revolução dos Bioinsumos",
        texto: "Os bioinsumos utilizam a própria biologia da natureza para protegê-la. Coquetéis de bactérias fixadoras de nitrogênio eliminam a dependência de fertilizantes químicos derivados do petróleo. Além disso, fungos específicos atuam no combate a insetos nocivos sem desequilibrar o ecossistema ou contaminar os lençóis freáticos, garantindo um solo regenerado e saudável a longo prazo."
    },
    verticais: {
        titulo: "Fazendas Verticais e Agricultura Urbana",
        texto: "Ao trazer a lavoura para dentro de galpões e estruturas verticais nas cidades, a biotecnologia aplicada ao manejo de luzes de LED ajustadas e nutrição hidropônica gera alimentos o ano todo, independente do clima externo. O consumo de água é reduzido em até 95%, o desperdício com transporte logístico cai a zero e preservam-se florestas inteiras que seriam desmatadas para expansão agrícola tradicional."
    }
};

/**
 * Exibe o painel de informações com os dados da biotecnologia clicada
 * @param {string} chave - A chave correspondente ao item do banco de dados (edicao, bioinsumos, verticais)
 */
function mostrarDetalhes(chave) {
    const painel = document.getElementById('detalhe-painel');
    const titulo = document.getElementById('detalhe-titulo');
    const texto = document.getElementById('detalhe-texto');

    // Atualiza os textos dinamicamente com base no objeto de dados
    titulo.innerText = informacoesTecnologicas[chave].titulo;
    texto.innerText = informacoesTecnologicas[chave].texto;

    // Remove a classe que esconde o painel
    painel.classList.remove('escondido');
    
    // Rola a tela suavemente até o painel de detalhes para melhor usabilidade
    painel.scrollIntoView({ behavior: 'smooth' });
}

/**
 * Esconde o painel de detalhes novamente
 */
function fecharDetalhes() {
    const painel = document.getElementById('detalhe-painel');
    painel.classList.add('escondido');
}
</html> 
