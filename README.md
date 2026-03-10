# 🎵 Aferidor de Entonação

O **Aferidor de Entonação** é uma aplicação web interativa desenvolvida para ajudar cantores e instrumentistas a melhorar a afinação e a percepção auditiva. O sistema reproduz uma nota de referência e utiliza o microfone do usuário para analisar, em tempo real, se a nota executada está afinada.

A ferramenta oferece feedback imediato sobre a entonação, permitindo ajustes progressivos e treinamento auditivo de forma simples e acessível diretamente no navegador.

## ✨ Funcionalidades

- Geração de **nota de referência aleatória** da escala cromática
- Captura de áudio pelo **microfone do usuário**
- **Análise de frequência em tempo real**
- Algoritmo de **detecção de pitch por autocorrelação**
- Feedback imediato sobre a afinação:
  - afinado
  - quase afinado
  - fora da afinação
- **Tolerância ajustável** para avaliação da entonação
- Sistema de **repetição automática da nota** para nova tentativa
- Apresentação de nova nota após duas tentativas incorretas
- Reconhecimento da nota **independente da oitava**
- Interface simples e intuitiva para prática musical

## 🛠️ Tecnologias Utilizadas

- **HTML5** – estrutura da aplicação
- **Tailwind CSS** – estilização da interface
- **JavaScript (ES6+)** – lógica do aplicativo
- **Tone.js** – geração e análise de áudio
- **Web Audio API** – processamento de áudio em tempo real

## 🎯 Objetivo do Projeto

O projeto foi desenvolvido para oferecer uma ferramenta prática de treino de entonação, permitindo que músicos desenvolvam:

- percepção auditiva
- controle vocal
- precisão na execução de notas
- consciência da afinação

A aplicação pode ser utilizada tanto por iniciantes quanto por músicos em treinamento mais avançado.

## ▶️ Como Usar

1. Clone ou baixe o repositório para o seu computador.
2. Abra o arquivo **index.html** em um navegador moderno.
3. Clique no botão **INICIAR**.
4. Permita o acesso ao **microfone** quando solicitado.
5. Clique em **Próxima Nota** para ouvir a nota de referência.
6. Cante ou toque a nota ouvida.
7. Observe o **feedback na tela** para ajustar a afinação.
8. Continue o treino com novas notas.

### Dica

Comece a cantar **durante a emissão da nota de referência** para facilitar o alinhamento da afinação.

## 🔍 Como Funciona

O sistema utiliza um algoritmo de **autocorrelação de frequência** para identificar o pitch do áudio captado pelo microfone. A frequência detectada é comparada com a nota de referência e classificada de acordo com uma margem de tolerância.

Mesmo que a nota seja executada em outra oitava, o sistema reconhece corretamente a **classe de altura**, garantindo maior flexibilidade no treino.

## 🎓 Aplicações Educacionais

Esta ferramenta pode ser utilizada em:

- aulas de canto
- treinamento vocal
- educação musical
- prática de percepção auditiva
- estudo de afinação instrumental

## 🌐 Compatibilidade

Recomenda-se utilizar navegadores modernos com suporte a **Web Audio API**, como:

- Google Chrome
- Microsoft Edge
- Firefox
- Opera

## ⚠️ Permissões

Para funcionar corretamente, o aplicativo precisa de acesso ao **microfone do dispositivo**.

## 📄 Licença

Este projeto pode ser utilizado para fins educacionais e de estudo.

## 👨‍🏫 Créditos

Desenvolvido por **Glauber Santiago — UFSCar**  
com apoio do **Gemini 2.5 Pro**
