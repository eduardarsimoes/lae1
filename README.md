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

> Após obter a(s) base(s) de dados, responda as seguintes perguntas sobre o conjunto de dados:
* seus dados são sobre o que? 
* o que você deseja com este conjunto de dados?
* quais são os tipos de atributos existentes e qual é o atributo alvo? 
* quais são os problemas existentes?
* qualidade e clareza: garantir que a semântica dos atributos seja clara (nomes coerentes com os dados, se necessário renomear atributos).

>#### 2.1 Visão geral da base de dados clássica:<br>
<p align="justify">
A base de dados possui informações a respeito dos tripulantes do navio Titanic, como informações pessoais desde o nome, idade, suas relações familiares a bordo e embarque, se sobreviveram etc, no qual deseja-se prever se certos dados de um indivíduo aumentam a chance de sobrevivência e se sim, quais seriam os fatores, sendo portanto o survived o atributo alvo. Foi possível observar que os tipos de atributos existentes são categóricos (nominais e binário) e também numéricos (discreto e contínuo). Ademais a isso, acredita-se que existem atributos irrelevantes para o propósito estabelecido como passengerId, name, cabin e ticket, pois não influenciam na sobrevivência (ou não sobrevivência) do indivíduo. É válido ressaltar que a base possui 891 registros e foi disponibilizada em formato csv. 
Analisando os problemas existentes na base foi encontrado incompletude (valores ausentes referentes a cabine, idade e porto de embarque), inconsistência (violação de domínio na idade e algumas discrepâncias quando preço da passagem e classe do navio são associados). Visto isso, para melhor clareza e qualidade dos dados, alguns atributos foram renomeados para melhor entendimento, são eles:<br>
</p>

 Nome | Novo nome 
----|----
 SibSp | siblingsSpousesOnboard 
 Parch | parentsChildrenOnboard 
 Fare | fareTicket 
 Embarked | embarkedHarbor 
 pClass | shipClass 
<p align="left">
    <i>Tabela 01: Atributos que foram renomeados - dataset Titanic</i>
</p>
<br>

>#### 2.2 Visão geral da base de dados em estudo:<br>
<p align="justify">
O dataset traz dados referentes à Mania que é um distúrbio mental definido como um período distinto, durante o qual existe um humor anormal e persistentemente elevado, expansivo ou irritável, abordando possíveis causas, associações a outras doenças, tempo de sintomas etc. A partir disso, o objetivo desejado com a análise desses dados é identificar indivíduos que possuam esse distúrbio através das respostas às perguntas - que foram transformadas em atributos.
Foi possível observar que os atributos são do tipo categóricos nominais, mas foram convertidos previamente para números discretos. O atributo alvo acreditamos ser o ‘dsm_man’, por não estar presente no dicionário de dados, por ser do tipo binário (1 = sim, 5 = não) e por seu nome (disturbiomental_mania).
Feita a análise no dataset, os problemas encontrados foram a incompletude (muitos valores vazios), algumas quebras de domínio (poucos valores avulsos) e um sério desbalanceamento de dados, pois há 35 casos de mania contra 5002 casos sem mania. A fim de garantir uma compreensão melhor dos dados, os campos a seguir foram renomeados:
</p>

 Nome atual | Pergunta traduzida | Novo nome 
---|---|---
SC1 | Qual a sua idade | age
SC7 | Fumante, Ex Fumante, Nunca fumou | have_smoked
SC8_1 | Classifique sua saúde física geral  | physical_health_rate
SC8_2 | Classifique sua saúde mental geral  | mental_health_rate
SC20 | Teve ataque de medo/pânico | had_fear_panic_attack
SC26 | Muito mais preocupado que outras pessoas | too_worried
SC26A | Muito mais ansioso/nervoso que outras pessoas | too_anxious_nervous
SC27A | Fobia de cobras/cachorros/insetos/animais | has_animal_phobia
SC27D | Claustrofobia | has_claustrophobia
SC27E | Fobia de altura | has_height_phobia
SC27F | Fobia de voar | has_flying_phobia
CC55 | Acha que sem ajuda fica melhor | better_without_help
CC49D | Visitou enfermeira ou nutricionista... | visits_nurse_nutritionist
CC49B | visitou psiquiatra em 1 ano | visits_psychiatrist_past_year
CC49A | Visitou médico em 1 ano | visits_doctor_past_year
CC28G | Outra dor crônica séria | has_chronic_other_pain
CC28F | Sérias dores de cabeça crônicas | has_chronic_headaches
CC28E | Dor torácica crônica séria | has_chronic_chest_pain
CC28D | Dor crônica séria no rosto ou mandíbula | has_chronic_face_or_jaw pain
CC28C | Dor crônica séria nas articulações | has_chronic_joint_pain
CC28B | Dor crônica grave de estômago ou abdômen | has_chronic_stomach_or_abdomen_pain
CC28A | Dores crônicas graves no pescoço ou nas costas | has_chronic_neck_or_back_pain
CC26C | Tem dificuldade para se levantar de manhã nos últimos 12 meses | difficulty_getting_up_past_year
CC24E | Sinto cansaço durante o dia nos últimos 12 meses | feel_fatigued_past_12_months
CC22 | Nas últimas 52 semanas tiveram problemas de sono | has_problem_sleep_past_52_weeks
CC9 | Vezes que viu o médico nos últimos 12 meses para tratamento | times_see_doctor_year
CC1S | Epilepsia ou convulsões | had_epilepsy_or_seizures
CC1Q | Teve problema neurológico, como esclerose múltipla | had_neurological_problem
CC1M | Teve malária ou alguma outra doença parasitária | had_parasitic_disease
CC1L | Teve qualquer outra doença pulmonar crônica | had_chronic_lung_disease
CC1E | Teve alergias sazonais como febre do feno | had_seasonal_allergies
<p align="left">
    <i>Tabela 02 - Atributos que foram renomeados - dataset Mania</i>
</p>

<p align="justify">
Visto isso, também ao analisarmos os documentos junto à base de dados, separamos os atributos em que compreendíamos tanto a pergunta quanto a resposta dos atributos que não sabíamos a pergunta e/ou a resposta, ambos referentes às siglas SC e CC, como pode ser observado abaixo.
</p>

 Nome | Pergunta traduzida | Resposta
---|---|---
CC1A | Teve artrite ou reumatismo. | 1 sim, 5 não, 8 não sabe
CC1B | Teve problemas nas costas ou pescoço. | 1 sim, 5 não, 8 não sabe
CC1C | Teve frequente ou fortes dores de cabeça. | 1 sim, 5 não, 8 não sabe
CC1D | Teve alguma outra dor crônica. | Binário (1 sim, 5 não)
CC1E | Teve alergias sazonais como rinite alérgica. | 1 sim, 5 não, 8 não sabe
CC1F | Teve um avc. | 1 sim, 5 não, 8 não sabe
CC1G | Teve um ataque cardíaco. | 1 sim, 5 não, 8 não sabe
CC1H | Teve doença cardíaca. | 1 sim, 5 não, 8 não sabe
CC1I | Teve pressão alta. | 1 sim, 5 não, 8 não sabe
CC1J | Teve asma. | 1 sim, 5 não, 8 não sabe
CC1K | Teve tuberculose. | 1 sim, 5 não, 8 não sabe
CC1L | Teve alguma outra doença pulmonar. | 1 sim, 5 não, 8 não sabe
CC1M | Teve malária ou alguma outra doença parasitária. | 1 sim, 5 não, 8 não sabe
CC1N | Teve diabetes ou açúcar alto no sangue. | 1 sim, 5 não, 8 não sabe
CC1O | Teve uma úlcera no estômago ou intestino. | 1 sim, 5 não, 8 não sabe
CC1P | Teve a doença da tireoide. | 1 sim, 5 não, 8 não sabe
CC1Q | Teve problema neurológico, como esclerose múltipla. | 1 sim, 5 não, 8 não sabe
CC1R | Teve infecção por HIV ou AIDS. | 1 sim, 5 não, 8 não sabe
CC1S | Epilepsia ou convulsões. | 1 sim, 5 não, 8 não sabe
CC1T | Teve câncer. | 1 sim, 5 não, 8 não sabe
CC7 | Checkpoint cartao referência. | Binário (1 ?, 2 todas as outras possibilidades)
CC8 | Checkpoint cartao referência. | Numérico
CC9 | Vezes que viu o médico nos últimos 12 meses para tratamento. | Numérico, 998 não sabe
CC10A | Interfere na gestão da casa (12 meses). | Escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou
CC10B | Interfere na habilidade de trabalhar (12 meses). | Escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou, um valor ‘30’ avulso
CC10C | Interfere nas relações próximas (12 meses). | Escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou
CC10D | Interfere na vida social (12 meses). | Escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou, um valor ‘50’ avulso
CC11 | Checkpoint (CC10A - CC10D). | Binário (1 ?, 2 todas as outras possibilidades)
CC12 | Número de dias após 365 que estava incapaz de realizar atividades normais. | Numérico, 998 não sabe
CC20A | Problemas para dormir nos últimos 12 meses. | 1 sim, 5 não, 8 não sabe
CC20B | Problemas para permanecer dormindo nos últimos 12 meses. | 1 sim, 5 não, 8 não sabe
CC20C | Problemas de acordar muito cedo nos últimos 12 meses . | 1 sim, 5 não, 8 não sabe
CC20D | Problemas de sentir sono durante o dia nos últimos 12 meses. | 1 sim, 5 não, 8 não sabe
CC21 | Checkpoint (CC20 series). | Binário (1 ?, 2 todas as outras possibilidades)
CC22 | Quantidade de semanas nas últimas 52 que teve problema com sono. | Numérico, 998 não sabe
CC23 | Checkpoint CC20D. | Binário (1 ?, 2 todas as outras possibilidades)
CC24B | Sonolento em 10 minutos sentado quieto nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou
CC24C | Cochila quando relaxa nos últimos 12 meses. | 1 nada, 2 um pouco, 3 moderadamente, 4 muito, 5 extremamente, 8 não sabe
CC24E | Sente cansado/fadiga nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou
CC24F | Acorda mais de 3 vezes durante a noite nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe
CC24G | Acorda se sentindo descansado nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou
CC24H | Sente dificuldade para levantar de manhã nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou
CC25 | Checkpoint (CC1A, CC1B, CC1C, CC1D). | Binário (1 ?, 2 todas as outras possibilidades)
CC26A | Acorda mais de 3 vezes durante a noite nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou
CC26B | Acorda se sentindo cansado nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou
CC26C | Sente dificuldade para levantar de manhã nos últimos 12 meses. | 1 muitas vezes, 2 às vezes, 3 raramente, 4 nunca, 8 não sabe, 9 recusou
CC27 | Checkpoint (CC1A, CC1B, CC1C, CC1D). | Binário (1 ?, 2 todas as outras possibilidades)
CC28A | Dor crônica grave nas costas ou pescoço. | 1 sim, 5 não, 8 não sabe, 9 recusou
CC28B | Dor crônica grave no estômago ou abdômen. | 1 sim, 5 não, 8 não sabe, 9 recusou
CC28C | Dor crônica grave na articulação. | 1 sim, 5 não, 8 não sabe, 9 recusou
CC28D | Dor crônica grave na face ou mandíbula. | 1 sim, 5 não, 8 não sabe, 9 recusou
CC28E | Dor crônica grave no tórax/peito. | 1 sim, 5 não, 8 não sabe, 9 recusou
CC28F | Dor crônica grave de cabeça. | 1 sim, 5 não, 8 não sabe, 9 recusou
CC28G | Outras dores crônicas grave. | 1 sim, 5 não, 8 não sabe, 9 recusou
CC29 | Checkpoint (CC1A, CC1B, CC1C, CC1D) | Binário (1 ?, 2 todas as outras possibilidades)
CC30 | Dias por mês com dor em mês severo. | Numérico, 998 não sabe, 99 recusou
CC31A | Duração de dor em um mês severo. | Numérico, 998 não sabe, 99 recusou
CC31B | Unidade de tempo de CC31A. | 1 muitas vezes, 2 às vezes, 8 não sabe, 9 recusou
CC32 | Pior dor dos últimos 12 meses. | Escala de 1 a 10, 998 não sabe, 999 se recusou, um valor ‘81’ avulso
CC33 | Menor dor dos últimos 12 meses. | Escala de 1 a 10, 998 não sabe, 999 se recusou
CC34 | Média de dor dos últimos 12 meses. | Escala de 1 a 10, 998 não sabe, 999 se recusou
CC35 | Alívio a partir do tratamento providenciado. | Escala de 1 a 10, 998 não sabe, 999 se recusou
CC48 | Tem visita regular ao médico quando precisa de cuidados médicos de rotina. | Binário (1 sim, 5 não)
CC48A | Tem lugar regular para ir quando quando precisa de cuidados médicos de rotina. | 1 sim, 5 não, 8 não sabe
CC49A | Visitas ao médico ano passado. | Numérico, 998 não sabe
CC49B | Visitas ao psiquiatra nos últimos 12 meses. | Numérico, 998 não sabe
CC49C | Visitas a um especialista tipo cardiologista (nos últimos 12 meses?). | Numérico, 998 não sabe, 999 recusou
CC49D | Visitas a um profissional da saúde, enfermeira ou nutricionista. | Numérico, 998 não sabe, 999 recusou
C55 | Estimativa % de pessoas que melhoraram sem serem ajudadas. | Numérico, 998 não sabe, 999 recusou
SC1  | Idade. | Numérico
SC2 | Há quanto tempo você mora no seu endereço atual? | Numérico, 998 não sabe, 999 recusou
SC2A | Tempo (número e unidade) vivendo no mesmo endereço. (Medida de tempo do SC2) | Unidade: 1 dias, 2 semanas, 3 meses, 4 anos
SC7  | Atualmente você é fumante, ex fumante ou nunca fumou. | 1 fumante, 2 ex fumante, 3 não fumante. Inferido pela ordem na pergunta
SC8_1 | Classificação de saúde física. | (1 a 5, inferindo que 1 é ruim e 5 é bom), 8 não sabe
SC8_2 | Classificação de saúde mental. | (1 a 5, inferindo que 1 é ruim e 5 é bom), 8 não sabe
SC20  | Ataque de medo/pânico.  | 1 sim, 5 não, 8 não sabe
SC23  | Vários dias ou mais sem interesse em coisas que gostava. | 1 sim, 5 não, 8 não sabe
SC24  | 4 ou mais dias agindo feliz/excitado/maníaco. | 1 sim, 5 não, 8 não sabe
SC25  | Vários dias ou mais muito irritável/amuado/mau humor.  | 1 sim, 5 não, 8 não sabe
SC25A | Vários dias ou mais começou discussões/bateu em pessoas.  | Binário (1 sim, 5 não) 
SC26  | Se preocupou muito mais com coisas do que outras pessoas.  | 1 sim, 5 não, 8 não sabe
SC26A | Muito mais nervoso ou ansioso do que outras pessoas.  | 1 sim, 5 não, 8 não sabe
SC26B | Um mês ou mais preocupado/ansioso na maior parte do tempo.  | 1 sim, 5 não, 8 não sabe
SC27A | Medo de insetos/cobras/cachorros/animais.  | Binário (1 sim, 5 não)
SC27B | Medo de eventos climáticos.  | Binário (1 sim, 5 não)
SC27C | Medo de sangue/médicos/feridas.  | 1 sim, 5 não, 8 não sabe
SC27D | Medo de espaços fechados.  | 1 sim, 5 não, 8 não sabe
SC27E | Medo de lugares altos. | 1 sim, 5 não, 8 não sabe
SC27F | Medo de voar.  | (1 sim, 5 não, 8 não sabe, 9 recusou a responder)
SC28  | Check point para SC27.  | Binário (1 sim, 5 não). Inferindo que a ‘pergunta’ é se a pessoa tem alguma fobia.
SC29  | Medo extremo de situações sociais ou performance social  | 1 sim, 5 não, 8 não sabe
SC30  | Medo extremo de multidões/espaços públicos.  | 1 sim, 5 não, 8 não sabe
SC31  | Dificuldade de concentração na infância.  | 1 sim, 5 não, 8 não sabe
SC32  | Agitação/inquietude na infância.  | 1 sim, 5 não, 8 não sabe
SC33  | Irritou outras pessoas na infância.  | 1 sim, 5 não, 8 não sabe
SC34  | Problemas com cuidadores na infância.  | 1 sim, 5 não, 8 não sabe, 9 recusou
SC35  | Problemas com separação de parentes/amigos.  | 1 sim, 5 não, 8 não sabe
<p align="left">
    <i>Tabela 03 - Atributos em que sabemos a pergunta e a respectiva resposta - dataset Mania</i>
</p>

| Nome | Nome | Nome | Nome |
|---|---|---|---|
| CC2 | CC2A05 | CC2A10 | CC50C |
| CC2A01 | CC2A06 | CC2A11 | CC50D |
| CC2A02 | CC2A07 | CC2A12 | CC50E |
| CC2A03 | CC2A08 | CC3 | CC50I |
| CC2A04 | CC2A09 | CC3A | CC52 |
<p align="left">
    <i>Tabela 04 - Atributos que não sabemos a pergunta e/ou a respectiva resposta (41) - dataset Mania</i>
</p>

<p align="justify">
Por fim, detectamos siglas referenciadas nos documentos as quais não conseguimos descobrir do que se tratam, são elas:
</p>

| Nome | Nome |
| --- | --- |
| PD1 INTROD 1 | AG1 |
| SP1 | IED3 |
| SO1 | SD1 |

<p align="left">
    <i>Tabela 05 - Referências desconhecidas nos documentos (6) - dataset Mania</i>
</p>

### 3.Pré-processamento dos Datasets <br>

Realize o Pré-processamento e Tratamento de Dados em sua base/dataset.

>#### 3.1 Pré-processamento e tratamento na base de dados clássica:<br>
As decisões de projeto tomadas para o pré processamento do dataset clássico Titanic foram divididas em etapas. São elas:
>#### VALORES DUPLICADOS
<p align="justify"> A partir do carregamento do dataset, o primeiro passo foi a verificação da existência de valores duplicados, no qual, até o momento, não apresentava nenhum. No entanto, após o tratamento dos atributos irrelevantes, novamente foi feita essa verificação, porém o dataset passou a apresentar 111 valores duplicados, com isso, realizamos o tratamento dos valores nulos, e verificamos novamente a quantidade de valores duplicados, valor esse que baixou para 58, mas continuou assim mesmo depois de todos os pré-processamentos adotados. </p>

>#### ATRIBUTOS IRRELEVANTES    <p align="justify">  </p>
<p align="justify"> Algumas colunas foram identificadas como irrelevantes pois não agregam muita informação para o modelo, apenas aumentando a complexidade. Para otimizar o modelo foram retiradas as seguintes colunas: nome do passageiro (não é relevante no caso de um naufrágio), o código do ticket que o passageiro comprou (novamente apenas um nome que não interfere) , o id do passageiro, que é apenas um código serial, e a cabine, uma vez que a classe nos proporciona a mesma informação. </p>

>#### TRATAMENTO DOS VALORES NULOS
<p align="justify"> Foi observado que as colunas embarkedHarbor e idade possuíam valores nulos. A idade apresentava 177 registros nulos, equivalente a 19% de todas as respostas de idade. e embarkedHarbor apresentava apenas 2 dados nulos. Nas duas colunas foi usado a mesma abordagem, a Input last observation para usar o valor anterior para imputar o valor ausente. </p>

>#### CONVERSÃO DE DADOS CATEGÓRICOS EM DADOS NUMÉRICOS
<p align="justify"> Foi necessário realizar a conversão no atributo sexo, e, primeiramente, haviamos utilizado a abordagem label enconding, porém, como a máquina pode atribuir um certo peso na hora do seu aprendizado, uma vez que 1 é maior que 0, decidimos trocar de abordagem, usando assim a one hot enconding. </p>

>#### ENCAIXOTAMENTO (BINNING)
<p align="justify"> Optamos por usar a abordagem binning em razão das discrepâncias encontradas no atributo fareTicket, com isso, separamos os atributos em 5 categorias, visando assim melhorar o desempenho do modelo, e também trazendo benefícios para quando posteriormente, fossemos realizar a identificação de outliers. </p>

>#### OUTLIERS
<p align="justify"> A abordagem utilizada para tratar os valores discrepantes que o dataset apresentava foi a exclusão dos outliers, porém, após realizar a exclusão deles, percebemos que os outliers compunham cerca de 50% da base, com isso, optamos por não excluí-los. </p>

>#### BALANCEAMENTO
<p align="justify"> Após a realização dos pré-processamentos citados anteriormente, fizemos a verificação do balanceamento do dataset, com isso, concluímos que apesar de estar um pouco desbalanceado, não era tão desigual a ponto de ser necessário o uso de alguma abordagem para balancear. </p>


>...
>#### 3.2 Pré-processamento e tratamento na base de dados em estudo:<br>
As decisões de projeto tomadas para o pré processamento do dataset Mania foram divididas em etapas. São elas:
>#### TRATAMENTO DOS VALORES NULOS E BALANCEAMENTO
<p align="justify"> Foi observado que todos os atributos de mania (M) possuem porcentagem maior que 85% de linhas nulas, entretanto devido a sua relevância para com o nosso objetivo, definimos apenas a retirada dessas linhas que estivessem 100% nulas, mesmo sabendo que não é o caminho mais correto, pois podemos perder padrões importantes referentes aos dados gerais para determinação do paciente ter ou não mania. Decisão essa que foi tomada devido ao alto desbalanceamento. As técnicas de balanceamento undersampling e oversampling também foram consideradas, porém reduziam ou aumentavam excessivamente os dados e por isso, não optamos pelo uso, apenas para fins de comparação. Ademais a isso, técnicas mais avançadas foram superficialmente estudadas, entretanto não houve tempo suficiente para analisá-las e aplicá-las. Foi utilizado o método last input observation para as colunas com os nulos, porém, por algum motivo não identificado, ainda sobraram alguns campos restantes com nulos. Estes foram preenchidos pelo valor 1, pois ele está presente normalmente nos domínios.
Em relação aos atributos gerais, referentes aos conjuntos SC e CC, foi realizada a retirada das colunas iguais ou maiores que 90% de valores nulos. Além disso, foi considerado realizar um merge com os atributos CC26A e CC24F, pois ambos representam a mesma pergunta e possuem as respostas inversamente correlatas, permitindo, então, uma junção entre os mesmos, entretanto não foi possível por falta de tempo.
 </p>
 
>#### VIOLAÇÃO DE DOMÍNIO
<p align="justify"> No dataset foram encontrados valores que violam o domínio dos atributos (CC32, CC10B, CC10D) e, portanto, como solução foi decidido a retirada de uma casa decimal desses valores. Não tratamos por enquanto.</p>

| Nome | Tipo resposta |
| --- | --- |
| CC10B | Escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou → um valor ‘30’ avulso |
| CC10D | Escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou → um valor ‘50’ avulso |
| CC32 | Escala de 1 a 10, 998 não sabe, 999 se recusou → um valor ‘81’ avulso |
<p align="left">
    <i>Tabela 05 - Atributos com violação de domínio (3) - dataset Mania</i>
</p>
<br>

>#### CORRELAÇÃO
<p align="justify"> A fim de afunilar o dataset, com a remoção de colunas com alta relação, ao calcularmos e analisarmos a correlação dos atributos, o grupo escolheu tirar as colunas de perguntas gerais que possuíam  correlação igual ou maior que 0,85 (valor absoluto), conforme tabela a seguir: </p>
| Atributos SC/CC correlacionados | Atributo SC/CC retirado |
| --- | --- |
| CC10D ←→ CC10C | CC10D |
| CC23 ←→ CC20D | CC23 |
| CC31B ←→ C31A | CC31B |
<p align="left">
    <i>Tabela 06 - Atributos com forte correlação (3) SC/CC - dataset Mania</i>
</p>
<br>
<p align="justify"> Já as colunas de mania, o threshold considerado foi de 0.95 (valor absoluto). As seguintes colunas foram retiradas: </p>
 | Atributos M correlacionados | Atributo M a ser retirado |
 | --- | --- |
| M26 ←→ M19 | M26 |
| M6 ←→ M1 | M6 |
| M55 ←→ M6B1 | M55 |
| M19A ←→ M3C, M3D1, M6D1 | M19A |
| M18D1 ←→ M3C, M3D1 | M18D1 |
| M18 ←→ M3C, M3D1 | M18 |
| M19D ←→ M3, M6C | M19D |
| M33A ←→ M3D2, M6D2 (inversamente) | M33A |
| M18B ←→ M3B2 | M18B |
| M48 ←→ M3D2 | M48 |
| M45B ←→ M3C, M3D1, M3D2 | M45B |
| M45A ←→ M3C, M3D1, M3D2 (inversamente) | M45A |
| M45C ←→ M3B1, M3B2 (ambos inversamente) | M45C |
| MM2A ←→ M3D2 (inversamente) | M22A |
| M30H ←→ M6D1 | M30H |
| M47 ←→ M3D2 (inversamente) | M47 |
| M27C ←→ M3C, M3D1 | M27C |
| M27A ←→ M3C, M3D1 | M27A |
| M48_1 ←→ M6D1 | M48_1 |
| M30F ←→ M30E | M30F |
| M18C ←→ M6D1 | M18C |
| M30A ←→ M3C, M3D1 | M30A |
| M48A ←→ M3C, M3D1, M6C (inversamente) | M48A |
| M23 ←→ M3D2 | M23 |
| M27D ←→ M3C, M3D1, M27C | M27D |
| M29 ←→ M3C, M3D1 | M29 |
<p align="left">
    <i>Tabela 07 - Atributos com forte correlação (26) M - dataset Mania</i>
</p>
<br>
<p align="justify"> Vale ressaltar que dividimos em dois datasets as colunas referentes às perguntas gerais e as perguntas específicas de mania. A coluna target não foi levada em consideração.
 </p> 
 

### 4.Análise Exploratória dos datasets<br>
Explore conjunto de dados por meio de uma ferramenta (EDA), destacando em suas observações o que for considerado mais relevante.<br>
Para acessar os HTML abaixo, acessar: https://htmlpreview.github.io/
>#### 4.1 Análise exploratória na base de dados clássica:<br>
> ![Pandas Profile Titanic](Titanic/output.html)
>#### 4.2 Análise exploratória na base de dados em estudo:<br>
> ![Pandas Profile Mania](Mania/mania_raw.html)

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


