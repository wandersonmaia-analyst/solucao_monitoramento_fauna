# 🐾 Solução: Monitoramento da Fauna - Parque Nacional do Cerrado

Este repositório contém a resolução do desafio prático de análise de dados aplicado ao programa de monitoramento de fauna de uma unidade de conservação brasileira. A análise foi desenvolvida em Python dentro do ambiente do Google Colab, processando um ecossistema sintético de **5.000 registros** coletados entre **01/05/2026 e 30/05/2026**.

## 🗺️ Estrutura do Parque e Sensores
O monitoramento cobriu **12 câmeras automáticas** distribuídas igualmente em 3 macroambientes do Cerrado:
*   **Cerrado Aberto:** CAM01, CAM02, CAM03, CAM04 (Vegetação rasteira e alta passagem).
*   **Mata de Galeria:** CAM05, CAM06, CAM07, CAM08 (Margens de cursos d'água, mata densa).
*   **Veredas e Áreas Úmidas:** CAM09, CAM10, CAM11, CAM12 (Nascentes e regiões alagáveis).

---

## 📈 Conclusões dos Desafios e Evidências

### 🛠️ Bônus 1 - Preparação e Limpeza dos Dados (Data Cleaning)
*   **Inconsistências Identificadas:** Presença de strings textuais (`" °C"` e `"%"`), formatos de data inconsistentes e ocorrências de valores ausentes mascarados como texto (`'None'`).
*   **Tratamento Adotado:** As strings numéricas foram limpas e convertidas via `pd.to_numeric(errors='coerce')`. Para não descartar dados vitais de fauna, as lacunas de temperatura e umidade causadas pelos registros nulos foram preenchidas estrategicamente utilizando a **mediana de leituras da respectiva câmera**.

### 🦌 Desafio 1 - Animais Solitários ou em Grupo? (Foco: Capivara)
*   **Conclusão:** As capivaras apresentaram comportamento marcadamente **social**. A maioria esmagadora das capturas envolve grupos familiares em vez de indivíduos isolados. O número médio de indivíduos por registro gira em torno de valores superiores a 1 (conforme verificado na distribuição do gráfico gerado no notebook).

### ⏰ Desafio 2 - Quando a Fauna está mais Ativa?
*   **Conclusão:** O maior pico de movimentação geral da fauna ocorre nos períodos da **Noite/Madrugada**, seguido pelos horários crepusculares. Comparando três espécies-alvo (Lobo-guará, Tamanduá-bandeira e Onça-pintada), observou-se curvas de densidade horária com hábitos majoritariamente noturnos para predadores e comportamento catemeral (ativo em frações do dia e da noite) para grandes forrageadores.

### 🐸 Desafio 3 - Vale a pena procurar Anfíbios em Períodos mais Úmidos?
*   **Conclusão:** **Sim, absolutamente.** A distribuição estatística revelou uma correlação linear fortíssima entre os níveis altos de umidade do ar e a frequência de disparos envolvendo *Rã-manteiga*, *Sapo-cururu* e *Perereca-verde*. Os registros acumulam-se massivamente na faixa de **Muito Alta (>85%)**, justificando que equipes de campo priorizem saídas em noites chuvosas ou pós-chuva.

### 📍 Desafio 4 - Onde Concentrar o Monitoramento?
*   **Conclusão:** As câmeras localizadas no ambiente de **Mata de Galeria** e algumas das **Veredas** registraram tanto o maior volume de movimentação animal (quantidade absoluta de registros) quanto os maiores índices de riqueza de espécies (variedade biológica). Recomenda-se manter o desenho amostral atual, mas alocar baterias de maior duração nesses pontos focais.

### 🐆 Desafio 5 - Onde Procurar uma Onça-Pintada?
*   **Recomendação Técnica:** Para maximizar as chances de novos registros visuais, a equipe de biólogos deve concentrar esforços:
    1.  **Espaço:** Nas imediações das câmeras da **Mata de Galeria**, ambiente que registrou maior incidência por servir como corredor biológico e zona de caça.
    2.  **Tempo:** Durante o período da **Noite/Madrugada**, horário preferencial em que o felino se desloca ativamente.

### ⏱️ Bônus 2 - Duração dos Registros
*   **Evidência:** Espécies herbívoras de grande e médio porte apresentam os registros mais longos (comportamento de repouso e alimentação sob o foco do sensor). Já a *Onça-pintada* e a *Ema* figuram com os registros mais curtos, indicando comportamentos estritos de **deslocamento rápido** e passagem pelas trilhas de amostragem.

### 🦊 Bônus 3 - O Comportamento do Lobo-Guará
*   **Padrão Identificado:** O lobo-guará exibiu forte fidelidade ecológica às áreas de **Cerrado Aberto** (CAM01 a CAM04), seu habitat natural de caça de pequenos roedores. Seu relógio biológico no parque confirmou picos estritos no início da noite e fim da madrugada (hábito crepuscular-noturno).

### 📊 Bônus 4 - Investigação Autoral: Temperatura vs. Tamanho dos Grupos
*   **Pergunta:** *O calor extremo do Cerrado afeta o comportamento social dos mamíferos?*
*   **Conclusão:** Os dados mostram que em temperaturas extremas (**Muito Quente >28°C**), o tamanho médio dos grupos de mamíferos diminui consideravelmente, registrando interações predominantemente individuais ou em duplas. O comportamento de agrupamento (maior média de indivíduos por registro) expande-se nas faixas **Amenas e Quentes**, indicando que as interações de bando acontecem prioritariamente fora dos horários de pico de calor do sol do Cerrado.

---

## 🛠️ Tecnologias Utilizadas
*   **Python 3.13**
*   **Pandas** (Tratamento, agregação e limpeza de dados)
*   **NumPy** (Operações matriciais e tratamento de NaNs)
*   **Matplotlib** & **Seaborn** (Visualização estatística de dados)

---
*Relatório gerado pelo analista de dados Wanderson Maia.*
