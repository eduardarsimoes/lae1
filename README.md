# DISCIPLINA: Laboratório de Extensão 1 - lae1

# TRABALHO 01:  Dataset Mania + Titanic

# Sumário

### 1. Componentes <br>
Integrantes do grupo
<br>
Eduarda Simões: eduardarsimoes@gmail.com
<br>
Serenna Ferrari: serenna.ferrari@hotmail.com
<br>
Thais de Souza: thais.souza.ifes@gmail.com
<br>

### 2.Apresentação dos Datasets (Clássico + Em estudo)<br>
Visão geral das bases de dados<br>

> Após obter a(s) base(s) de dados Responda as seguintes perguntas sobre o conjunto de dados:
* seus dados são sobre o que? 
* o que você deseja com este conjunto de dados?
* quais são os tipos de atributos existentes e qual é o atributo alvo? 
* quais são os problemas existentes?
* qualidade e clareza: garantir que a semântica dos atributos seja clara (nomes coerentes com os dados, se necessário renomear atributos).

>#### 2.1 Visão geral da base de dados clássica:<br>
<p align="justify">
A base de dados possui informações a respeito dos tripulantes do navio Titanic, como informações pessoais desde o nome, idade, suas relações familiares a bordo e embarque, se sobreviveram etc, no qual deseja-se prever se certos dados de um indivíduo aumentam a chance de sobrevivência e se sim, quais seriam os fatores, sendo portanto o survived o atributo alvo. Foi possível observar que os tipos de atributos existentes são categóricos (nominais e binário) e também numéricos (discreto e contínuo). Ademais a isso, acredita-se que existem atributos irrelevantes para o propósito estabelecido como passengerId, name, cabin e ticket, pois não influenciam na sobrevivência (ou não sobrevivência) do indivíduo. É válido ressaltar que a base possui 891 registros e foi disponibilizada em formato csv. 
Analisando os problemas existentes na base foi encontrado incompletude (valores ausentes referentes a cabine, idade e porto de embarque), inconsistência (violação de domínio na idade e algumas discrepâncias quando preço da passagem e classe do navio são associados). Visto isso, para melhor clareza e qualidade dos dados, alguns atributos foram renomeados para melhor entendimento, são eles:<br>
- SibSp: siblingsSpousesOnboard <br>
- Parch: parentsChildrenOnboard <br>
- Fare: fareTicket <br>
- Embarked: embarkedHarbor <br>
- pClass: shipClass <br>
</p>

>#### 2.2 Visão geral da base de dados em estudo:<br>
<p align="justify">
O dataset traz dados referentes à Mania que é um distúrbio mental definido como um período distinto, durante o qual existe um humor anormal e persistentemente elevado, expansivo ou irritável, abordando possíveis causas, associações a outras doenças, tempo de sintomas etc. A partir disso, o objetivo desejado com a análise desses dados é identificar indivíduos que possuam esse distúrbio através das respostas às perguntas - que foram transformadas em atributos.
Foi possível observar que os atributos são do tipo categóricos nominais, mas foram convertidos previamente para números discretos. O atributo alvo acreditamos ser o ‘dsm_man’, por não estar presente no dicionário de dados, por ser do tipo binário (1 = sim, 5 = não) e por seu nome (disturbiomental_mania).
Feita a análise no dataset, os problemas encontrados foram a incompletude (muitos valores vazios), algumas quebras de domínio (poucos valores avulsos) e um sério desbalanceamento de dados, pois há 35 casos de mania contra 5002 casos sem mania. A fim de garantir uma compreensão melhor dos dados, os campos a seguir foram renomeados:
</p>

| Nome atual | Pergunta traduzida | Novo nome |
|-|------------------------------------|--|
| SC1 | Qual a sua idade | age |
| SC7 | Fumante, Ex Fumante, Nunca fumou | have_smoked |
| SC8_1 | Classifique sua saúde física geral  | physical_health_rate |
| SC8_2 | Classifique sua saúde mental geral  | mental_health_rate |
| SC20 | Teve ataque de medo/pânico | had_fear_panic_attack |
| SC26 | Muito mais preocupado que outras pessoas | too_worried |
| SC26A | Muito mais ansioso/nervoso que outras pessoas | too_anxious_nervous |
| SC27A | Fobia de cobras/cachorros/insetos/animais | has_animal_phobia |
| SC27D | Claustrofobia | has_claustrophobia |
| SC27E | Fobia de altura | has_height_phobia |
| SC27F | Fobia de voar | has_flying_phobia |
| CC55 | Acha que sem ajuda fica melhor | better_without_help |
| CC49D | Visitou enfermeira ou nutricionista... | visits_nurse_nutritionist |
| CC49B | visitou psiquiatra em 1 ano | visits_psychiatrist_past_year |
| CC49A | Visitou médico em 1 ano | visits_doctor_past_year |
| CC28G | Outra dor crônica séria | has_chronic_other_pain |
| CC28F | Sérias dores de cabeça crônicas | has_chronic_headaches |
| CC28E | Dor torácica crônica séria | has_chronic_chest_pain |
| CC28D | Dor crônica séria no rosto ou mandíbula | has_chronic_face_or_jaw pain |
| CC28C | Dor crônica séria nas articulações | has_chronic_joint_pain |
| CC28B | Dor crônica grave de estômago ou abdômen | has_chronic_stomach_or_abdomen_pain |
| CC28A | Dores crônicas graves no pescoço ou nas costas | has_chronic_neck_or_back_pain |
| CC26C | Tem dificuldade para se levantar de manhã nos últimos 12 meses | difficulty_getting_up_past_year |
| CC24E | Sinto cansaço durante o dia nos últimos 12 meses | feel_fatigued_past_12_months |
| CC22 | Nas últimas 52 semanas tiveram problemas de sono | has_problem_sleep_past_52_weeks |
| CC9 | Vezes que viu o médico nos últimos 12 meses para tratamento | times_see_doctor_year |
| CC1S | Epilepsia ou convulsões | had_epilepsy_or_seizures |
| CC1Q | Teve problema neurológico, como esclerose múltipla | had_neurological_problem |
| CC1M | Teve malária ou alguma outra doença parasitária | had_parasitic_disease |
| CC1L | Teve qualquer outra doença pulmonar crônica | had_chronic_lung_disease |
| CC1E | Teve alergias sazonais como febre do feno | had_seasonal_allergies |
Tabela 01 - Atributos em que foram renomeados

<p align="justify">
Visto isso, também ao analisarmos os documentos junto à base de dados, separamos os atributos em que compreendíamos tanto a pergunta quanto a resposta dos atributos que não sabíamos a pergunta e/ou a resposta, ambos referentes às siglas SC e CC, como pode ser observado abaixo.
</p>

| Nome | Pergunta traduzida | Resposta|
|-|-----------------------------------|-|
| CC1A | Teve artrite ou reumatismo. | 1 sim, 5 não, 8 não sabe |
| CC1B | Teve problemas nas costas ou pescoço. | 1 sim, 5 não, 8 não sabe |
| CC1C | Teve frequente ou fortes dores de cabeça. | 1 sim, 5 não, 8 não sabe |
| CC1D | Teve alguma outra dor crônica. | Binário (1 sim, 5 não) |
| CC1E | Teve alergias sazonais como rinite alérgica. | 1 sim, 5 não, 8 não sabe |
| CC1F | Teve um avc. | 1 sim, 5 não, 8 não sabe |
| CC1G | Teve um ataque cardíaco. | 1 sim, 5 não, 8 não sabe |
| CC1H | Teve doença cardíaca. | 1 sim, 5 não, 8 não sabe |
| CC1I | Teve pressão alta. | 1 sim, 5 não, 8 não sabe |
| CC1J | Teve asma. | 1 sim, 5 não, 8 não sabe |
| CC1K | Teve tuberculose. | 1 sim, 5 não, 8 não sabe |
| CC1L | Teve alguma outra doença pulmonar. | 1 sim, 5 não, 8 não sabe |
| CC1M | Teve malária ou alguma outra doença parasitária. | 1 sim, 5 não, 8 não sabe |
| CC1N | Teve diabetes ou açúcar alto no sangue. | 1 sim, 5 não, 8 não sabe |
| CC1O | Teve uma úlcera no estômago ou intestino. | 1 sim, 5 não, 8 não sabe |
| CC1P | Teve a doença da tireoide. | 1 sim, 5 não, 8 não sabe |
| CC1Q | Teve problema neurológico, como esclerose múltipla. | 1 sim, 5 não, 8 não sabe |
| CC1R | Teve infecção por HIV ou AIDS. | 1 sim, 5 não, 8 não sabe |
| CC1S | Epilepsia ou convulsões. | 1 sim, 5 não, 8 não sabe |
| CC1T | Teve câncer. | 1 sim, 5 não, 8 não sabe |
| CC7 | Checkpoint cartao referência. | Binário (1 ?, 2 todas as outras possibilidades) |
| CC8 | Checkpoint cartao referência. | Numérico |
| CC9 | Vezes que viu o médico nos últimos 12 meses para tratamento. | Numérico, 998 não sabe |
| CC10A | Interfere na gestão da casa (12 meses). | Escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou |
| CC10B | Interfere na habilidade de trabalhar (12 meses). | escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou, um valor ‘30’ avulso |
| CC10C | Interfere nas relações próximas (12 meses). | escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou |
| CC10D | Interfere na vida social (12 meses). | escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou, um valor ‘50’ avulso |
| CC11 | Checkpoint (CC10A - CC10D). | Binário (1 ?, 2 todas as outras possibilidades) |
| CC12 | Número de dias após 365 que estava incapaz de realizar atividades normais. | Numérico, 998 não sabe |
| CC20A | Problemas para dormir nos últimos 12 meses. | 1 sim, 5 não, 8 não sabe |
| CC20B | Problemas para permanecer dormindo nos últimos 12 meses. | 1 sim, 5 não, 8 não sabe |
| CC20C | Problemas de acordar muito cedo nos últimos 12 meses . | 1 sim, 5 não, 8 não sabe |
| CC20D | Problemas de sentir sono durante o dia nos últimos 12 meses. | 1 sim, 5 não, 8 não sabe |
| CC21 | Checkpoint (CC20 series). | Binário (1 ?, 2 todas as outras possibilidades) |
| CC22 | Quantidade de semanas nas últimas 52 que teve problema com sono. | Numérico, 998 não sabe |
| CC23 | Checkpoint CC20D. | Binário (1 ?, 2 todas as outras possibilidades) |
| CC24B | Sonolento em 10 minutos sentado quieto nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou |
| CC24C | Cochila quando relaxa nos últimos 12 meses. | 1 nada, 2 um pouco, 3 moderadamente, 4 muito, 5 extremamente, 8 não sabe |
| CC24E | Sente cansado/fadiga nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou |
| CC24F | Acorda mais de 3 vezes durante a noite nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe |
| CC24G | Acorda se sentindo descansado nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou |
| CC24H | Sente dificuldade para levantar de manhã nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou |
| CC25 | Checkpoint (CC1A, CC1B, CC1C, CC1D). | Binário (1 ?, 2 todas as outras possibilidades) |
| CC26A | Acorda mais de 3 vezes durante a noite nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou |
| CC26B | Acorda se sentindo cansado nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou |
| CC26C | Sente dificuldade para levantar de manhã nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou |
| CC27 | Checkpoint (CC1A, CC1B, CC1C, CC1D). | Binário (1 ?, 2 todas as outras possibilidades) |
| CC28A | Dor crônica grave nas costas ou pescoço. | 1 sim, 5 não, 8 não sabe, 9 recusou |
| CC28B | Dor crônica grave no estômago ou abdômen. | 1 sim, 5 não, 8 não sabe, 9 recusou |
| CC28C | Dor crônica grave na articulação. | 1 sim, 5 não, 8 não sabe, 9 recusou |
| CC28D | Dor crônica grave na face ou mandíbula. | 1 sim, 5 não, 8 não sabe, 9 recusou |
| CC28E | Dor crônica grave no tórax/peito. | 1 sim, 5 não, 8 não sabe, 9 recusou |
| CC28F | Dor crônica grave de cabeça. | 1 sim, 5 não, 8 não sabe, 9 recusou |
| CC28G | Outras dores crônicas grave. | 1 sim, 5 não, 8 não sabe, 9 recusou |
| CC29 | Checkpoint (CC1A, CC1B, CC1C, CC1D) | Binário (1 ?, 2 todas as outras possibilidades) |
| CC30 | Dias por mês com dor em mês severo. | Numérico, 998 não sabe, 99 recusou |
| CC31A | Duração de dor em um mês severo. | Numérico, 998 não sabe, 99 recusou |
| CC31B | Unidade de tempo de CC31A. | 1 muitas vezes, 2 às vezes, 8 não sabe, 9 recusou |
| CC32 | Pior dor dos últimos 12 meses. | escala de 1 a 10, 998 não sabe, 999 se recusou, um valor ‘81’ avulso |
| CC33 | Menor dor dos últimos 12 meses. | escala de 1 a 10, 998 não sabe, 999 se recusou |
| CC34 | Média de dor dos últimos 12 meses. | escala de 1 a 10, 998 não sabe, 999 se recusou |
| CC35 | Alívio a partir do tratamento providenciado. | escala de 1 a 10, 998 não sabe, 999 se recusou |
| CC48 | Tem visita regular ao médico quando precisa de cuidados médicos de rotina. | Binário (1 sim, 5 não) |
| CC48A | Tem lugar regular para ir quando quando precisa de cuidados médicos de rotina. | 1 sim, 5 não, 8 não sabe |
| CC49A | Visitas ao médico ano passado. | Numérico, 998 não sabe |
| CC49B | Visitas ao psiquiatra nos últimos 12 meses. | Numérico, 998 não sabe |
| CC49C | Visitas a um especialista tipo cardiologista (nos últimos 12 meses?). | Numérico, 998 não sabe, 999 recusou |
| CC49D | Visitas a um profissional da saúde, enfermeira ou nutricionista. | Numérico, 998 não sabe, 999 recusou |
| C55 | Estimativa % de pessoas que melhoraram sem serem ajudadas. | Numérico, 998 não sabe, 999 recusou |
| SC1  | Idade. | Numérico |
| SC2 | Há quanto tempo você mora no seu endereço atual? | Numérico, 998 não sabe, 999 recusou |
| SC2A | Tempo (número e unidade) vivendo no mesmo endereço. (Medida de tempo do SC2) | Unidade: 1 dias, 2 semanas, 3 meses, 4 anos |
| SC7  | Atualmente você é fumante, ex fumante ou nunca fumou. | 1 fumante, 2 ex fumante, 3 não fumante. Inferido pela ordem na pergunta |
| SC8_1 | Classificação de saúde física. | (1 a 5, inferindo que 1 é ruim e 5 é bom), 8 não sabe |
| SC8_2 | Classificação de saúde mental. | (1 a 5, inferindo que 1 é ruim e 5 é bom), 8 não sabe |
| SC20  | Ataque de medo/pânico.  | 1 sim, 5 não, 8 não sabe |
| SC23  | Vários dias ou mais sem interesse em coisas que gostava. | 1 sim, 5 não, 8 não sabe |
| SC24  | 4 ou mais dias agindo feliz/excitado/maníaco. | 1 sim, 5 não, 8 não sabe |
| SC25  | Vários dias ou mais muito irritável/amuado/mau humor.  | 1 sim, 5 não, 8 não sabe |
| SC25A | Vários dias ou mais começou discussões/bateu em pessoas.  | Binário (1 sim, 5 não)  |
| SC26  | Se preocupou muito mais com coisas do que outras pessoas.  | 1 sim, 5 não, 8 não sabe |
| SC26A | Muito mais nervoso ou ansioso do que outras pessoas.  | 1 sim, 5 não, 8 não sabe |
| SC26B | Um mês ou mais preocupado/ansioso na maior parte do tempo.  | 1 sim, 5 não, 8 não sabe |
| SC27A | Medo de insetos/cobras/cachorros/animais.  | Binário (1 sim, 5 não) |
| SC27B | Medo de eventos climáticos.  | Binário (1 sim, 5 não) |
| SC27C | Medo de sangue/médicos/feridas.  | 1 sim, 5 não, 8 não sabe |
| SC27D | Medo de espaços fechados.  | 1 sim, 5 não, 8 não sabe |
| SC27E | Medo de lugares altos. | 1 sim, 5 não, 8 não sabe |
| SC27F | Medo de voar.  | (1 sim, 5 não, 8 não sabe, 9 recusou a responder) |
| SC28  | Check point para SC27.  | Binário (1 sim, 5 não). Inferindo que a ‘pergunta’ é se a pessoa tem alguma fobia. |
| SC29  | Medo extremo de situações sociais ou performance social  | 1 sim, 5 não, 8 não sabe |
| SC30  | Medo extremo de multidões/espaços públicos.  | 1 sim, 5 não, 8 não sabe |
| SC31  | Dificuldade de concentração na infância.  | 1 sim, 5 não, 8 não sabe |
| SC32  | Agitação/inquietude na infância.  | 1 sim, 5 não, 8 não sabe |
| SC33  | Irritou outras pessoas na infância.  | 1 sim, 5 não, 8 não sabe |
| SC34  | Problemas com cuidadores na infância.  | 1 sim, 5 não, 8 não sabe, 9 recusou |
| SC35  | Problemas com separação de parentes/amigos.  | 1 sim, 5 não, 8 não sabe |
Tabela 02 - Atributos em que foram renomeados

| Nome |
|------|
| CC2 |
| CC2A01 |
| CC2A02 |
| CC2A03 |
| CC2A04 |
| CC2A05 |
| CC2A06 |
| CC2A07 |
| CC2A08 |
| CC2A09 |
| CC2A10 |
| CC2A11 |
| CC2A12 |
| CC3 |
| CC3A |
| CC4 |
| CC5 |
| CC49C |
| CC50A |
| CC50B |
| CC50C |
| CC50D |
| CC50E |
| CC50I |
| CC52 |
| CC53 |
| CC54 |
| SC3  |
| SC1_1 |
| SC3A |
| SC9 |
| SC19 |
| SC20A |
| SC20_1  |
| SC20_2  |
| SC20_3  |
| SC21 |
| SC22 |
| SC29A |
| SC33_1 |
| SC33_2 |
| SC33_3 |
Tabela 03 - Atributos que não SABEMOS a pergunta E/OU a respectiva resposta (41)

<p align="justify">
Por fim, detectamos siglas referenciadas nos documentos as quais não conseguimos descobrir do que se tratam, são elas:
</p>

| Nome|
| ------------------------- |
| PD1 INTROD 1 |
| SP1 |
| SO1 |
| AG1 |
| IED3 |
| SD1 |
Tabela 04 - Referências desconhecidas (6)

### 3.Pré-processamento dos Datasets <br>

Realize o Pré-processamento e Tratamento de Dados em sua base/dataset.

>#### 3.1 Pré-processamento e tratamento na base de dados clássica:<br>
>...
>#### 3.2 Pré-processamento e tratamento na base de dados em estudo:<br>
>...    

### 4.Análise Exploratória dos datasets<br>
Explore conjunto de dados por meio de uma ferramenta (EDA), destacando em suas observações o que for considerado mais relevante.

>#### 4.1 Análise exploratória na base de dados clássica:<br>
>...
>#### 4.2 Análise exploratória na base de dados em estudo:<br>
>...    
Sugestão: Utilizar ferramentas como Pandas Proffile e Sweetviz , Seaborn e Matplotlib <br>
    
[Tutorial básico com Seaborn](https://github.com/profmoisesomena/escience_and_tools/blob/master/seaborn/Seaborn_introduction.ipynb "Seaborn Introduction")

># Marco de Entrega 01: Itens do Sprint 01 <br>
    
### 5.processos de Classificação  (explicação + datasets)<br>
    A) Explicação sobre o algoritmo/método de classificação adotado
    B) Implementar método nos datasets utilizados
    
>#### 5.1 Processo de classificação na base de dados clássica:<br>
>...
>#### 5.2 Processo de classificação na base de dados obtida:<br>
>...


### 6.processos de Estimação  (explicação + datasets)<br>
    A) Explicação sobre o algoritmo/método de classificação adotado
    B) Implementar método nos datasets utilizados
    
>#### 6.1 Processo de estimação/regressão na base de dados clássica:<br>
>...
>#### 6.2 Processo de estimação/regressão na base de dados obtida:<br>
>...
>
># Marco de Entrega 02: Itens do Sprint 02 <br>

### 7.Automated machine learning - AutoML <br>
    A) Explicação sobre o que é e o processo de AutoML
    B) Aplicar o processo de AutoML nos conjuntos de dados utilizados
    
>#### 7.1 Processo de AutoML na base de dados clássica:<br>
>...
>#### 7.2 Processo de AutoML na base de dados obtida:<br>
>...
>
### 8. Resultados e Artefatos
>#### 8.1 Slides Finais
>#### 8.3 Demais artefatos solicitados pelo professor


># Marco de Entrega 03: Conclusão das atividades <br>

### 9 FORMATACAO NO GIT:<br> 
https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
    
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/
#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/

    
### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. <strong>Caso existam arquivos com conteúdos sigilosos<strong>, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário do git "profmoisesomena", para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.

Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")


