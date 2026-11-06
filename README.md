# Aferidor de Entonação — Estúdio Pedagógico Vocal

O **Aferidor de Entonação** é uma aplicação web interativa desenvolvida para apoiar cantores, estudantes de música, coralistas e instrumentistas no desenvolvimento da **afinação vocal**, **percepção auditiva** e **controle sensório-motor laríngeo**. O sistema sintetiza notas, intervalos e arpejos de referência e utiliza o microfone do dispositivo para analisar, em tempo real, a precisão da altura entoada.

---

## Funcionalidades Pedagógicas e Técnicas

### 1. Seis Caminhos (Trilhas) de Estudo Musical
1. **Trilha 1 — Uníssono Guiado:** Percepção e reprodução de notas isoladas sorteadas dentro do repertório escolhido.
2. **Trilha 2 — Escada Vocal (Graus Conjuntos):** Subida e descida sequencial pelos graus da escala (`Dó → Ré → Mi...`) para calibrar microajustes musculares da laringe.
3. **Trilha 3 — Saltos & Intervalos Melódicos:** Reproduz uma nota base seguida de um intervalo melódico (*2ª Maior, 3ª Menor, 3ª Maior, 4ª Justa ou 5ª Justa*) para o estudante entoar a segunda nota alvo.
4. **Trilha 4 — Memória Tonal & *Audiation* (Gordon):** Toca a referência, realiza uma contagem silenciosa de **3 segundos de *Audiation*** (retenção mental da altura) e abre a captação para o ataque vocal.
5. **Trilha 5 — Arpejos & Tríades (Sentido Harmônico):** Percorre os graus de tríades maiores e menores (*1º, 3º e 5º graus*) para consolidar a afinação harmônica e coral.
6. **Trilha 6 — Laboratório Livre:** Afinador contínuo integrado ao gráfico de contorno vocal e ao **Diapasão Interativo** de 12 notas, sem contagem de erros.

### 2. Biofeedback Visual Contínuo e Repetição Pedagógica
- **Régua Direcional de Cents (`-100` a `+100 cents`):** Mostra instantaneamente a nota detectada, o desvio numérico em *cents* e a orientação motora (*"Suba um pouco — está Grave ♭"* ou *"Relaxe/desça um pouco — está Agudo ♯"*).
- **Gráfico de Contorno Vocal no Tempo (`Canvas`):** Traça a curva da voz do estudante em relação à linha central da nota alvo (inspirado nos sistemas *SINGAD* e *Sing & See*), permitindo analisar o ataque vocal (*onset*) e a estabilidade de sustentação.
- **Repetição Pedagógica Inteligente (Até 3 Vezes):** Quando o estudante erra uma nota, o aplicativo repete a **mesma nota** por no máximo **3 vezes consecutivas** para permitir a correção sensório-motora antes de sortear uma nova nota.
- **Diagnóstico Vocal Automático da Sessão:** Calcula o erro médio absoluto em *cents* e identifica se o estudante possui tendência **calante (grave ♭)**, **sustenida (aguda ♯)** ou **centro equilibrado**, gerando recomendações fisiológicas personalizadas.

### 3. Configurações Adaptáveis à Fisiologia Vocal
- **Repertórios de Escala:** *Pentatônica (5 notas)*, *Diatônica em Dó Maior (7 notas)* e *Cromática (12 semitons)*.
- **Região Vocal (Tessitura):** *Oitava 3 (`C3–B3`)* ou *Oitava 4 (`C4–B4`)*, com opção de **Oitava Flexível** ou **Oitava Exata**.
- **Níveis de Rigor (Tolerância):** *Iniciante (`±65 cents`)*, *Intermediário (`±38 cents`)* e *Avançado / Coral (`±20 cents`)*.
- **Timbres de Referência e Pedal Tônico (*Drone*):** *Voz Suave (Triangular)*, *Piano Harmônico (FM)* e *Senoidal Pura*, além de botão **Pedal Dó (ON/OFF)** para ancoragem harmônica.

### 4. Gamificação Simples Sem Backend (`localStorage`)
- **Níveis e XP:** 5 níveis de evolução (*Ouvinte Curioso* a *Mestre da Entonação*).
- **Sequência (*Streak*) e Recorde Pessoal:** Contabilização de acertos seguidos e bônus de precisão máxima (`≤ 12 cents`).
- **Missões Pedagógicas e 6 Conquistas (*Badges*):** Desbloqueio salvo automaticamente no navegador sem necessidade de servidor externo.

### 5. Guia de Aquecimento Vocal e Fundamentação Científica Integrados
- **Aba "Como Afinar a Voz & Aquecimento":** Inclui 3 exercícios de aquecimento vocal com áudio sintetizado (*Sirene Vocal / TVSO*, *Humming de 3 Graus* e *Arpejo de Tríade Maior*) e 6 pilares práticos de fisiologia e percepção vocal.
- **Aba "Ciência & Pedagogia":** Síntese conceitual baseada em pesquisas de cognição musical e acústica vocal:
  - *Tradução Sensório-Motora* (Pfordresher & Brown, 2007; Hutchins & Peretz, 2012)
  - *Teoria de Aprendizagem Musical e Audiation* (Edwin Gordon, 1997; Deutsch, 1970)
  - *Biofeedback Visual em Tempo Real* (Welch, Howard & Rush, 1989; Wilson et al., 2008)
  - *Continuum Desenvolvimental Vocal e Timbre* (Graham Welch, 1986, 2006; Watts et al., 2003)
  - *Biomecânica Laríngea: Equilíbrio CT/TA e Pressão Subglótica* (Sundberg, 1987; Titze, 1994)

---

## Tecnologias Utilizadas

- **HTML5 & Canvas 2D** – estrutura semântica e gráfico de contorno melódico em tempo real
- **Tailwind CSS** – estilização responsiva e *glassmorphism*
- **JavaScript (ES6+)** – motor de autocorrelação, trilhas pedagógicas, diagnóstico e gamificação via `localStorage`
- **Tone.js & Web Audio API** – síntese sonora multi-timbral e análise de frequência em tempo real

---

## Créditos e Apoio

Desenvolvido pelo professor **Glauber Santiago** — DAC/UFSCar  
- [aprenda-musica-comigo.web.app](https://aprenda-musica-comigo.web.app/) • [servidores.ufscar.br/glauber/](https://servidores.ufscar.br/glauber/) • [https://glauberia.web.app/](https://glauberia.web.app/)  
- **Apoio:** Grupo de Estudos e Pesquisas sobre Inovação em Educação, Tecnologias e Linguagens (Grupo Horizonte-UFSCar) — [grupohorizonte.ufscar.br](https://grupohorizonte.ufscar.br/)
