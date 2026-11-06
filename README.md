# Aferidor de Entonação — Estúdio Pedagógico Vocal

O **Aferidor de Entonação** é uma aplicação web interativa desenvolvida para apoiar cantores, estudantes de música, coralistas e instrumentistas no desenvolvimento da **afinação vocal**, **percepção auditiva** e **controle sensório-motor laríngeo**. O sistema reproduz notas, intervalos e arpejos de referência com timbres baseados em amostras **General MIDI (`FluidR3_GM`)** — iniciando com **Coro Vocal (`choir_aahs`)** — e analisa pelo microfone, em tempo real, a precisão da altura entoada.

---

## Funcionalidades Pedagógicas e Técnicas

### 1. Oito Caminhos (Trilhas) de Estudo Musical
1. **Trilha 1 — Uníssono Guiado:** Percepção e reprodução de notas isoladas sorteadas dentro do repertório escolhido.
2. **Trilha 2 — Escada Vocal (Graus Conjuntos):** Subida e descida sequencial pelos graus da escala (`Sol a Sol` ou `Dó a Dó`) para calibrar microajustes musculares da laringe.
3. **Trilha 3 — Saltos & Intervalos Melódicos:** Reproduz uma nota base seguida de um intervalo melódico (*2ª Maior, 3ª Menor, 3ª Maior, 4ª Justa ou 5ª Justa*) para o estudante entoar a segunda nota alvo.
4. **Trilha 4 — Memória Tonal & *Audiation* (Gordon):** Toca a referência, realiza uma contagem silenciosa de **3 segundos de *Audiation*** (retenção mental da altura) e abre a captação para o ataque vocal.
5. **Trilha 5 — Arpejos & Tríades (Sentido Harmônico):** Percorre os graus de tríades maiores e menores (*1º, 3º e 5º graus*) para consolidar a afinação harmônica e coral.
6. **Trilha 6 — Repouso Após Escala:** O aplicativo executa rapidamente as notas da escala ativa (em semicolcheias) e, em seguida, toca a **nota alvo longa** (qualquer grau sorteado da escala, inclusive a tônica) para o cantor entoar. A trajetória melódica varia aleatoriamente entre 4 padrões (*Ascendente da tônica até a oitava*, *Descendente da oitava até a tônica*, *Dupla ascendente e descendente* e *Dupla descendente e ascendente*) para calibrar a retenção tonal e o ataque vocal afinado imediatamente após o contexto da escala.
7. **Trilha 7 — Espelho Vocal (Emitir → Gravar 3s → Comparar):** O aplicativo emite a nota de referência, inicia automaticamente uma **gravação de 3 segundos** da voz do usuário e, em seguida, reproduz a comparação: **1º Nota Original**, **2º Áudio Gravado** e **3º As Duas Juntas (em uníssono)**.
8. **Trilha 8 — Comparação Especial (Auto-Tune):** O aplicativo emite a nota de referência, grava a voz do usuário por **3 segundos** e, em seguida, reproduz a sequência completa: **1º Nota Original**, **2º Áudio Gravado**, **3º Áudio Gravado Corrigido na Afinação (Auto-Tune na oitava exata da nota emitida)** e, por fim, **4º Os 2 Áudios Gravados Juntos (Áudio Gravado + Voz Corrigida, sem a nota guia)**.

### 2. Biofeedback Visual Contínuo e Repetição Pedagógica
- **Régua Direcional de Cents (`-100` a `+100 cents`):** Mostra instantaneamente a nota detectada, o desvio numérico em *cents* e a orientação motora (*"Suba um pouco — está Grave ♭"* ou *"Relaxe/desça um pouco — está Agudo ♯"*).
- **Gráfico de Contorno Vocal no Tempo (`Canvas`):** Traça a curva da voz do estudante em relação à linha central da nota alvo, permitindo analisar o ataque vocal (*onset*) e a estabilidade de sustentação.
- **Repetição Pedagógica Inteligente (Até 3 Vezes):** Quando o estudante erra uma nota, o aplicativo repete a **mesma nota** por no máximo **3 vezes consecutivas** para permitir a correção sensório-motora antes de sortear uma nova nota.
- **Diagnóstico Vocal Automático da Sessão:** Calcula o erro médio absoluto em *cents* e identifica se o estudante possui tendência **calante (grave ♭)**, **sustenida (aguda ♯)** ou **centro equilibrado**, gerando recomendações fisiológicas personalizadas.

### 3. Áudio SoundFont (`FluidR3_GM`), Regiões Vocais e Controle de Oitava
- **Motor SoundFont sob Demanda (`SoundFontEngine`):** Carrega dinamicamente instrumentos do banco General MIDI `FluidR3_GM` (`https://gleitz.github.io/midi-js-soundfonts/FluidR3_GM/`), iniciando com **Coro Vocal (`choir_aahs`)**, com cache de `AudioBuffer` decodificados apenas para as notas utilizadas e *fallback* automático para síntese nativa (`Tone.Synth`).
- **Classificação / Região Vocal:**
  - **Vozes Graves (de Sol a Sol):** 13 notas cromáticas de `Sol` a `Sol'`.
  - **Vozes Agudas (de Dó a Dó):** 13 notas cromáticas de `Dó` a `Dó'`.
- **Controle de Oitava das Notas de Referência:**
  - **Oitava Grave (Padrão):** `Sol2–Sol3` (`98,0–196,0 Hz`) para Vozes Graves | `Dó3–Dó4` (`130,8–261,6 Hz`) para Vozes Agudas.
  - **Oitava Acima (`+8va`):** `Sol3–Sol4` (`196,0–392,0 Hz`) para Vozes Graves | `Dó4–Dó5` (`261,6–523,3 Hz`) para Vozes Agudas.
- **Tônica (Nota Base) com Enarmonia Precisa e Catálogo de Escalas (22 Tipos):**
  - **Enarmonia Teórica Rigorosa:** Distinção tonal exata entre notas enarmônicas (ex.: `D♯` não é igual a `E♭`, `C♯` não é igual a `D♭`, `F♯` não é igual a `G♭`). A tônica escolhida determina a correta soletração das notas da escala (um nome de letra para cada grau diatônico), intervalos melódicos (terças maiores/menores com o salto de letra exato) e tríades harmônicas (ex.: 3ª menor de Dó é Mi♭ e não Ré♯; 3ª maior de Ré é Fá♯ e não Sol♭; 3ª maior de Ré♯ é Fá𝄪 e não Sol).
  - **Tônica:** Seleção individual de todas as 17 tonalidades enarmônicas (`C`, `C♯`, `D♭`, `D`, `D♯`, `E♭`, `E`, `F`, `F♯`, `G♭`, `G`, `G♯`, `A♭`, `A`, `A♯`, `B♭`, `B`), atualizando automaticamente o Diapasão Interativo, os exercícios e o Pedal Tônico.
  - **Tipos de Escala:** *Maior Natural (Jônio)*, *Menor Natural (Eólio)*, *Menor Harmônica*, *Menor Melódica*, *Pentatônica Maior*, *Pentatônica Menor*, *Blues (Hexatônica)*, *Modos Gregos (Dórico, Frígio, Lídio, Mixolídio / Nordestina, Lócrio)*, *Cromática (12 semitons)*, *Tons Inteiros (Hexafônica)*, *Acústica (Lídio Dominante)*, *Frígio Dominante (Cigana Espanhola)*, *Menor Cigana (Húngara)*, *Diminuta (Semitom–Tom e Tom–Semitom)*, *Bebop Maior*, *Bebop Dominante* e *Hirajoshi (Pentatônica Japonesa)*.
- **Níveis de Rigor (Tolerância):** *Iniciante (`±65 cents`)*, *Intermediário (`±38 cents`)* e *Avançado / Coral (`±20 cents`)*.

### 4. Gamificação Simples Sem Backend (`localStorage`)
- **Níveis e XP:** 5 níveis de evolução (*Ouvinte Curioso* a *Mestre da Entonação*).
- **Sequência (*Streak*) e Recorde Pessoal:** Contabilização de acertos seguidos e bônus de precisão máxima (`≤ 12 cents`).
- **Missões Pedagógicas e 6 Conquistas (*Badges*):** Desbloqueio salvo automaticamente no navegador sem necessidade de servidor externo.

---

## Bibliografia e Referências Científicas de Acesso Aberto (*Open Access*)

Todas as referências que fundamentam a aba **"Ciência & Pedagogia"** e os exercícios do aplicativo possuem texto completo **100% aberto e gratuito** para consulta direta (*PubMed Central / PMC*, *SciELO Brasil*, *Frontiers in Psychology* e *PLOS ONE*):

1. **BLANCO, A. D.; TASSANI, S.; RAMIREZ, R.** (2021). *Effects of Visual and Auditory Feedback in Violin and Singing Voice Pitch Matching Tasks.* **Frontiers in Psychology**, v. 12, art. 684693.  
   - **Acesso Aberto:** [PubMed Central (PMC8297736)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8297736/) • [DOI: 10.3389/fpsyg.2021.684693](https://doi.org/10.3389/fpsyg.2021.684693)

2. **CIELO, C. A.; LIMA, J. P. M.; CHRISTMANN, M. K.; BRUM, R.** (2013). *Exercícios de trato vocal semiocluído: revisão de literatura.* **Revista CEFAC**, v. 15, n. 6, p. 1679–1689.  
   - **Acesso Aberto (Português):** [SciELO Brasil — DOI: 10.1590/S1516-18462013005000041](https://doi.org/10.1590/S1516-18462013005000041)

3. **HUTCHINS, S.; MORENO, S.** (2013). *The Linked Dual Representation model of vocal perception and production.* **Frontiers in Psychology**, v. 4, art. 825.  
   - **Acesso Aberto:** [PubMed Central (PMC3817506)](https://pmc.ncbi.nlm.nih.gov/articles/PMC3817506/) • [DOI: 10.3389/fpsyg.2013.00825](https://doi.org/10.3389/fpsyg.2013.00825)

4. **LÉVÊQUE, Y.; SCHÖN, D.** (2013). *Listening to the Human Voice Alters Sensorimotor Brain Rhythms.* **PLOS ONE**, v. 8, n. 11, e80659.  
   - **Acesso Aberto:** [PubMed Central (PMC3827177)](https://pmc.ncbi.nlm.nih.gov/articles/PMC3827177/) • [DOI: 10.1371/journal.pone.0080659](https://doi.org/10.1371/journal.pone.0080659)

5. **MARTINHO, D. H. C.; CONSTANTINI, A. C.** (2020). *Efeitos imediatos de exercícios de trato vocal semiocluído em vozes graves e agudas: estudo sobre a autopercepção.* **CoDAS**, v. 32, n. 5, e20190079.  
   - **Acesso Aberto (Português):** [SciELO Brasil — DOI: 10.1590/2317-1782/20202019079](https://doi.org/10.1590/2317-1782/20202019079)

6. **MORETI, F.; PEREIRA, L. D.; GIELOW, I.** (2012). *Triagem da Afinação Vocal: comparação do desempenho de musicistas e não musicistas.* **Jornal da Sociedade Brasileira de Fonoaudiologia**, v. 24, n. 4, p. 368–373.  
   - **Acesso Aberto (Português):** [SciELO Brasil — DOI: 10.1590/S2179-64912012000400013](https://doi.org/10.1590/S2179-64912012000400013)

7. **TITZE, I. R.** (2008). *Nonlinear source–filter coupling in phonation: Theory.* **The Journal of the Acoustical Society of America**, v. 123, n. 5, p. 2733–2749.  
   - **Acesso Aberto:** [PubMed Central (PMC2811547)](https://pmc.ncbi.nlm.nih.gov/articles/PMC2811547/) • [DOI: 10.1121/1.2832337](https://doi.org/10.1121/1.2832337)

---

## Tecnologias Utilizadas

- **HTML5 & Canvas 2D** – estrutura semântica e gráfico de contorno melódico em tempo real
- **Tailwind CSS** – estilização responsiva e *glassmorphism*
- **JavaScript (ES6+)** – motor `SoundFontEngine` sob demanda (`FluidR3_GM`), detecção de altura por autocorrelação, trilhas pedagógicas e gamificação via `localStorage`
- **Web Audio API & Tone.js** – decodificação/reprodução polifônica de amostras com envelope via `GainNode`, síntese de *fallback* e análise espectral em tempo real

---

## Créditos e Apoio

Desenvolvido pelo professor **Glauber Santiago** — DAC/UFSCar  
- [aprenda-musica-comigo.web.app](https://aprenda-musica-comigo.web.app/) • [servidores.ufscar.br/glauber/](https://servidores.ufscar.br/glauber/) • [https://glauberia.web.app/](https://glauberia.web.app/)  
- **Apoio:** Grupo de Estudos e Pesquisas sobre Inovação em Educação, Tecnologias e Linguagens (Grupo Horizonte-UFSCar) — [grupohorizonte.ufscar.br](https://grupohorizonte.ufscar.br/)
