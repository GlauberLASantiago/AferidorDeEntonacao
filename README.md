Aferidor de Entonação

Descrição
O Aferidor de Entonação é uma ferramenta web interativa desenvolvida para auxiliar cantores e instrumentistas a aprimorar a sua afinação e percepção musical. O aplicativo apresenta uma nota de referência e utiliza o microfone do usuário para analisar, em tempo real, se a nota cantada ou tocada está afinada.

O projeto foi construído com tecnologias web padrão (HTML, CSS e JavaScript), sem a necessidade de frameworks complexos, e utiliza a biblioteca Tone.js para a geração e análise de áudio.

Principais Funcionalidades

Nota de Referência: O aplicativo toca uma nota aleatória da escala cromática para que o usuário a utilize como referência.

Análise em Tempo Real: Captura o áudio do microfone e utiliza um algoritmo de autocorrelação para detectar a frequência da nota entoada pelo usuário.

Feedback Instantâneo:

Informa se o usuário acertou a afinação com uma margem de tolerância ajustável.

Caso a nota esteja fora, indica que a entonação precisa ser corrigida.

Oferece um feedback de "Quase Lá" para ajudar no ajuste fino da afinação.

Repetição Inteligente: Se o usuário errar a nota, o aplicativo a repete para uma segunda tentativa. Caso erre duas vezes seguidas, uma nova nota é apresentada para manter o dinamismo do treino.

Independência de Oitava: O sistema reconhece a nota entoada independentemente da oitava em que é cantada, focando apenas na qualidade da afinação.

Tecnologias Utilizadas

HTML5: Estrutura base da página.

Tailwind CSS: Framework CSS para uma estilização rápida e moderna.

JavaScript (ES6+): Lógica principal do aplicativo.

Tone.js: Web Audio framework para geração de som e análise de frequência.

Como Usar

Clone este repositório para a sua máquina local.

Abra o arquivo index.html em qualquer navegador moderno (Chrome, Firefox, Edge, etc.).

Clique no botão "INICIAR".

O navegador irá solicitar permissão para usar o seu microfone. Permita o acesso.

Clique em "Próxima Nota" para ouvir o som de referência.

Cante a nota que ouviu. A dica é começar a cantar ainda durante a emissão da nota de referência para uma melhor entonação.

Observe o feedback na tela para ajustar a sua afinação.

O aplicativo irá avançar ou repetir a nota automaticamente. Você pode clicar em "Próxima Nota" a qualquer momento para pular para um novo desafio.

Créditos

Este aplicativo foi desenvolvido por Glauber Santiago - UFSCar por meio do Gemini 2.5 pro.
