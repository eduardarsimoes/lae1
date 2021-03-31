# DISCIPLINA: Laboratório de Extensão 1 - lae1

# TRABALHO:  Machine Learning

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
<br><br>
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
<br>

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
<br>

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
<br>

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
<br>

### 3.Pré-processamento dos Datasets <br>

>#### 3.1 Pré-processamento e tratamento na base de dados clássica:<br>
![Colab Titanic](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/Titanic.ipynb)
<br>
As decisões de projeto tomadas para o pré processamento do dataset clássico Titanic foram divididas em etapas. São elas:
<br>

>##### 3.1.1 Valores duplicados
<p align="justify">
A partir do carregamento do dataset, o primeiro passo foi a verificação da existência de valores duplicados, no qual, até o momento, não apresentava nenhum. No entanto, após o tratamento dos atributos irrelevantes, novamente foi feita essa verificação, porém o dataset passou a apresentar 111 valores duplicados, com isso, realizamos o tratamento dos valores nulos, e verificamos novamente a quantidade de valores duplicados, valor esse que baixou para 58, mas continuou assim mesmo depois de todos os pré-processamentos adotados.
</p>
<br>

>##### 3.1.2 Atributos irrelevantes
<p align="justify">
Algumas colunas foram identificadas como irrelevantes pois não agregam muita informação para o modelo, apenas aumentando a complexidade. Para otimizar o modelo foram retiradas as seguintes colunas: nome do passageiro (não é relevante no caso de um naufrágio), o código do ticket que o passageiro comprou (novamente apenas um nome que não interfere) , o id do passageiro, que é apenas um código serial, e a cabine, uma vez que a classe nos proporciona a mesma informação.
</p>

![Removendo](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/removendo_atributos.png)
<p align="left">
    <i>Imagem 01 - Atributos irrelevantes - dataset Titanic</i>
</p>

<br>

>##### 3.1.3 Tratamento dos valores nulos
<p align="justify">
Foi observado que as colunas embarkedHarbor e idade possuíam valores nulos. A idade apresentava 177 registros nulos, equivalente a 19% de todas as respostas de idade. </p>

![Nulos](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/verificacaoNulos_tipos.png) 
 <p align="left">
    <i>Imagem 02 - Verificação dos nulos - dataset Titanic</i>
</p>

<p align="justify"> EmbarkedHarbor apresentava apenas 2 dados nulos. Nas duas colunas foi usado a mesma abordagem, a Input last observation para usar o valor anterior para imputar o valor ausente. </p>

![Nulos](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/preenche_nulos_age.png) 
<p align="left">
    <i>Imagem 03 - Preenchimento dos nulos do atributo age - dataset Titanic</i>
</p>

![Nulos](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/preenche_nulos_embarked.png) 
<p align="left">
    <i>Imagem 04 - Preenchimento dos nulos do atributo EmbarkedHarbor - dataset Titanic</i>
</p>

<br>

>##### 3.1.4 Conversão de dados categóricos em dados numéricos
<p align="justify">
Foi necessário realizar a conversão no atributo sexo, e, primeiramente, haviamos utilizado a abordagem label enconding, porém, como a máquina pode atribuir um certo peso na hora do seu aprendizado, uma vez que 1 é maior que 0, decidimos trocar de abordagem, usando assim a one hot enconding.
</p>

![Conversao](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/onehot.png)
<p align="left">
    <i>Imagem 05 - One hot enconding aplicado no atributo sexo - dataset Titanic</i>
</p>

<br>

>##### 3.1.5 Encaixotamento (BINNING)
<p align="justify">
Optamos por usar a abordagem binning em razão das discrepâncias encontradas no atributo fareTicket, com isso, separamos os atributos em 5 categorias, visando assim melhorar o desempenho do modelo, e também trazendo benefícios para quando posteriormente, fossemos realizar a identificação de outliers.
</p>

![Encaixotamento](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/binning.png)
<p align="left">
    <i>Imagem 06 - Binning aplicado no atributo fareTicket - dataset Titanic</i>
</p>

<br>

>##### 3.1.6 Outliers
<p align="justify">
A abordagem utilizada para tratar os valores discrepantes que o dataset apresentava foi a exclusão dos outliers, porém, após realizar a exclusão deles, percebemos que os outliers compunham cerca de 50% da base, com isso, optamos por não excluí-los.
</p>

![Outliers](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/esclusao_outliers.png)
<p align="left">
    <i>Imagem 07 - Excluindo outliers - dataset Titanic</i>
</p>

![Outliers](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/iqr.png)
<p align="left">
    <i>Imagem 08 - Outliers - dataset Titanic</i>
</p>

<br>

>##### 3.1.7 Balanceamento
<p align="justify"> Após a realização dos pré-processamentos citados anteriormente, fizemos a verificação do balanceamento do dataset, com isso, concluímos que apesar de estar um pouco desbalanceado, não era tão desigual a ponto de ser necessário o uso de alguma abordagem para balancear.
</p>

![Balanceamento](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/balanceamento.png)
<p align="left">
    <i>Imagem 09 - Verificação do balanceamento do dataset - dataset Titanic</i>
</p>

<br>

>##### 3.1.8 Treinamento e teste

![Precisao](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/precisao.png)
<p align="left">
    <i>Imagem 10 - Precisão do treino e do teste - dataset Titanic</i>
</p>

<br>

>#### 3.2 Pré-processamento e tratamento na base de dados em estudo:<br>
![Colab Mania](https://github.com/eduardarsimoes/lae1/blob/main/Mania/ManiaDS.ipynb)
<br>
As decisões de projeto tomadas para o pré processamento do dataset Mania foram divididas em etapas. São elas:

>##### 3.2.1 Tratamento dos valores nulos e balanceamento
<p align="justify">
Foi observado que todos os atributos de mania (M) possuem porcentagem maior que 85% de linhas nulas, entretanto devido a sua relevância para com o nosso objetivo, definimos apenas a retirada dessas linhas que estivessem 100% nulas, mesmo sabendo que não é o caminho mais correto, pois podemos perder padrões importantes referentes aos dados gerais para determinação do paciente ter ou não mania. Decisão essa que foi tomada devido ao alto desbalanceamento.
</p>

![Nulos](https://github.com/eduardarsimoes/lae1/blob/main/Mania/imagens/nulos.png)
<p align="left">
    <i>Imagem 11 - Verificação de nulos - dataset Mania</i>
</p>

<p align="justify"> 
As técnicas de balanceamento undersampling e oversampling também foram consideradas, porém reduziam ou aumentavam excessivamente os dados e por isso, não optamos pelo uso, apenas para fins de comparação. Ademais a isso, técnicas mais avançadas foram superficialmente estudadas, entretanto não houve tempo suficiente para analisá-las e aplicá-las. Foi utilizado o método last input observation para as colunas com os nulos, porém, por algum motivo não identificado, ainda sobraram alguns campos restantes com nulos. Estes foram preenchidos pelo valor 1, pois ele está presente normalmente nos domínios.
</p>

![Nulos](https://github.com/eduardarsimoes/lae1/blob/main/Mania/imagens/preenchendo_nulos.png)
<p align="left">
    <i>Imagem 12 - Preenchendo nulos com o método last input observation - dataset Mania</i>
</p>

![Nulos](https://github.com/eduardarsimoes/lae1/blob/main/Mania/imagens/preenchendo_nulos_com1.png)
<p align="left">
    <i>Imagem 13 - Preenchendo restante dos nulos com abordagem de constante global - dataset Mania</i>
</p>
 
<p align="justify"> 
Em relação aos atributos gerais, referentes aos conjuntos SC e CC, foi realizada a retirada das colunas iguais á 100% de valores nulos. Além disso, foi considerado realizar um merge com os atributos CC26A e CC24F, pois ambos representam a mesma pergunta e possuem as respostas inversamente correlatas, permitindo, então, uma junção entre os mesmos, entretanto não foi possível por falta de tempo.
</p>

![Nulos](https://github.com/eduardarsimoes/lae1/blob/main/Mania/imagens/removendo_colunas.png)
<p align="left">
    <i>Imagem 14 - Removendo colunas com 100% valores nulos - dataset Mania</i>
</p>

<br>

>##### 3.2.2 Violação de domínio
<p align="justify">
No dataset foram encontrados valores que violam o domínio dos atributos (CC32, CC10B, CC10D) e, portanto, como solução foi decidido a retirada de uma casa decimal desses valores. Não tratamos por enquanto.
</p>

| Nome | Tipo resposta |
| --- | --- |
| CC10B | Escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou → um valor ‘30’ avulso |
| CC10D | Escala 0 a 10, 97 não se aplica, 98 não sabe, 99 recusou → um valor ‘50’ avulso |
| CC32 | Escala de 1 a 10, 998 não sabe, 999 se recusou → um valor ‘81’ avulso |
<p align="left">
    <i>Tabela 05 - Atributos com violação de domínio (3) - dataset Mania</i>
</p>
<br>

>##### 3.2.3 Correlação
<p align="justify">
A fim de afunilar o dataset, com a remoção de colunas com alta relação, ao calcularmos e analisarmos a correlação dos atributos, o grupo escolheu tirar as colunas de perguntas gerais que possuíam  correlação igual ou maior que 0,85 (valor absoluto), conforme tabela a seguir:
</p>

| Atributos SC/CC correlacionados | Atributo SC/CC retirado |
| --- | --- |
| CC10D ←→ CC10C | CC10D |
| CC23 ←→ CC20D | CC23 |
| CC31B ←→ C31A | CC31B |
<p align="left">
    <i>Tabela 06 - Atributos com forte correlação (3) SC/CC - dataset Mania</i>
</p>
<br>

![Nulos](https://github.com/eduardarsimoes/lae1/blob/main/Mania/imagens/removendo_colunas_90%25.png)
<p align="left">
    <i>Imagem 15 - Removendo colunas com correlação - dataset Mania</i>
</p>

<br>

<p align="justify">
Já as colunas de mania, o threshold considerado foi de 0.95 (valor absoluto). As seguintes colunas foram retiradas:
</p>

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

<p align="justify">
Vale ressaltar que dividimos em dois datasets as colunas referentes às perguntas gerais e as perguntas específicas de mania. A coluna target não foi levada em consideração.
</p> 
<br>

>##### 3.2.4 Treinamento e teste

![Precisao](https://github.com/eduardarsimoes/lae1/blob/main/Mania/imagens/precisao.png)
<p align="left">
    <i>Imagem 16 - Precisão do treino e do teste - dataset Mania</i>
</p>

<br>

### 4.Análise Exploratória dos datasets<br>
Explore conjunto de dados por meio de uma ferramenta (EDA), destacando em suas observações o que for considerado mais relevante.<br>

>#### 4.1 Análise exploratória na base de dados clássica:<br>
Análise gráfica do dataset sem tratamento: ![Profile Titanic raw](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/profile/titanic_raw.html)
<br>
Para fazer uma análise superficial dos dados pós tratamento: ![Profile Titanic done](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/profile/titanic_raw.html)
<br>
Recomendamos baixar os arquivos para os botões (toggle details) funcionarem.
<br>

<p align="justify">
Antes do tratamento dos dados, tínhamos 12 colunas e 891 registros, no qual a partir do uso do Profile Reporting foi possível observar que o dataset possuía 8,1% de missing cels (células vazias) e os mesmos foram tratados, como visto anteriormente. Os tipos eram numéricos (41,7%) e categóricos (58,3%), os quais os categóricos também foram tratados seja com a exclusão dos atributos por serem considerados irrelevantes ou com a técnica de one hot encoding e os numéricos muito discrepantes com a técnica de encaixotamento. Não havia nenhuma duplicata e não soubemos interpretar muito bem as medidas estatísticas para maiores conclusões (fora a frequência).
Já após o pré processamento dos dados dos dataset, continuamos com 12 colunas, entretanto com 4 colunas “novas” referentes ao sex (2), embarked (3) (estas com one hot encoding) e categories_fareTicket (1) com encaixotamento. Visto que não eliminamos nenhum valor por estar nulo, mantivemos os 891 registros. Em contrapartida, passou a ter valores considerados duplicados (6.5%) após os atributos considerados relevantes terem sido excluídos, pois os mesmos que diferenciavam-os.
</p>
<br>

>#### 4.2 Análise exploratória na base de dados em estudo:<br>
O link para análise gráfica é este: ![Profile Mania raw](Mania/profile/mania_raw.html).
<br>
Para fazer uma análise superficial, este link abre códigos HTML do git: ![Profile Mania done](Mania/profile/mania_done.html)
<br>
Recomendamos baixar os arquivos para os botões (toggle details) funcionarem. 
<br>
<p align="justify">
Antes do tratamento do dataset, temos 229 colunas e 5037 registros, tendo assim 1.153.473‬ células. Com a ajuda da ferramenta, descobrimos acertadamente que 53.2% destas estavam vazias, o que é um grave problema que foi tratado no pré-processamento.
Foi interessante descobrir que 141 colunas (61,6%) são do tipo categórico - a variável target inclusa, enquanto 79 (34,5%) são do tipo numérico. As variáveis reportadas como “não suportadas” são justamente as colunas retiradas no pré-processamento por estarem completamente vazias. Não soubemos interpretar muito bem as medidas estatísticas (fora a frequência).
Após o pré-processamento, o dataset ficou com uma coluna que não sabemos a origem (df_index), que aparenta representar o número da linha dos registros. Como mencionado na seção 3, o input last observation ainda deixou uma pequena quantidade de nulos distribuída entre as colunas (0,2% das células), tratado antes de treinar o modelo. Reduzimos a quantidade de colunas em 30,6% (de 229 para 159) e a quantidade de registros em 86% (de 5037 para 708).
</p>
<br>

># Marco de Entrega 01: Itens do Sprint 01 <br>
    
### 5. Processos de Classificação  (explicação + datasets)<br>
    A) Explicação sobre o algoritmo/método de classificação adotado
    B) Implementar método nos datasets utilizados
    
>#### 5.1 Processo de classificação na base de dados clássica:<br>

<p align="justify">
O processo de classificação adotado foi o de regressão logística, que visa estimar as relações entre uma variável dependente categórica (atributo alvo/target), sendo normalmente do tipo ponto flutuante (real/float), e uma ou mais variáveis independentes (características/ features). Como já foi aplicado esse método no dataset Titanic, visamos melhorar o pré-processamento para obter melhor resultado. Contudo, os pré-processamentos modificados ou acrescentados foram:
</p>

>##### 5.1.1 Tratamento dos valores nulos
<p align="justify">Foi realizado mudança na abordagem de tratamento dos nulos da instância age, uma vez que antes estavam sendo preenchidos com base no valor da linha anterior, agora são preenchidos com base na média de idade.
</p>

![Nulos](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/p_nulos_media.png)
<p align="left">
    <i>Imagem 17 - Preenchendo nulos de idade - dataset Titanic</i>
</p>

>##### 5.1.2 Valores duplicados
<p align="justify">Foi optado a não remoção dos dados duplicados, em razão de que na primeira verificação (com o dataset sem nenhum pré-processamento realizado) não havia dados duplicados, porém depois da remoção de algumas colunas, eles apareceram, com isso, considerando que o id, nome, cabine, e ticket desses passageiros não eram iguais, esse dados não são realmente duplicados. Com a não retirada, a acurácia de teste e de treino foram para 79%.
</p>

![Duplicados](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/duplicados_0.png)
<p align="left">
    <i>Imagem 18 - Dados duplicados antes da remoção de colunas irrelevantes - dataset Titanic</i>
</p>

![Duplicados](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/duplicados_114.png)
<p align="left">
    <i>Imagem 19 - Dados duplicados depois da remoção de colunas irrelevantes - dataset Titanic</i>
</p>

>##### 5.1.3 Atributos irrelevantes
<p align="justify">Foi realizado a retirada de mais duas colunas, a coluna fareticket, devido a alta correlação com a coluna categories_fareTicket gerada através do binning e a coluna embarkedharbor, pela suposição de não agregação de informação importante e pelo geramento de três novas colunas depois de realizar o one hot encoding. Com essas duas remoções, o modelo passou a executar de forma mais otimizada, sem a necessidade de aumentar o número de iterações.
</p>

>##### 5.1.4 Exclusão dos outliers
<p align="justify"> Novamente foi realizado a tentativa de exclusão dos outliers, porém, com sucesso dessa vez. Uma análise sobre o código de exclusão foi feito e sobre os outliers de fato existentes também. Com a exclusão, a acurácia de treino e teste subiram para respectivamente 82% e 80%. Contudo, ainda estava removendo muitos dados do nosso dataset, então foi realizado a modificação do código, trocando o valor do cálculo de 1.5 para 3, visando excluir uma quantidade menor de outliers, e consequentemente a acurácia de treino e teste foram para respectivamente 81% e 84%.
</p>

![Shape](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/shape_antes.png)
<p align="left">
    <i>Imagem 20 - Shape antes da exclusão dos outliers - dataset Titanic</i>
</p>

![Boxplot](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/outliers_antes_exclusao.png)
<p align="left">
    <i>Imagem 21 - Boxplot antes da exclusão dos outliers - dataset Titanic</i>
</p>

![Boxplot](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/outliers_depois_exclusao.png)
<p align="left">
    <i>Imagem 22 - Boxplot depois da exclusão dos outliers - dataset Titanic</i>
</p>

![Shape](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/shape_depois.png)
<p align="left">
    <i>Imagem 23 - Shape depois da exclusão dos outliers - dataset Titanic</i>
</p>

>##### 5.1.5 Conversão de dados categóricos em dados numéricos
<p align="justify"> Por último, foi trocada a abordagem de conversão da coluna sexo, estava sendo utilizado o método one hot encoding, porém, as duas colunas geradas (sex_male e sex_female) estavam tendo alta correlação, com isso, a abordagem foi trocada para o método label encoder, não interferindo na acurácia.
</p>

![Correlação](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/duplicados_e_correla%C3%A7ao_sexo.png)
<p align="left">
    <i>Imagem 24 - correlação - dataset Titanic</i>
</p>

>##### 5.1.6 Métricas
<p align="justify"> Por fim, as métricas foram aplicadas para medir o quão distante o modelo está da classificação perfeita, são elas:
</p>

>###### Matriz de confusão
<p align="justify"> Usada para calcular a quantidade de falso positivo, falso negativo, verdadeiro positivo e verdadeiro negativo, além de fornecer a acurácia, recall, f1 score e support.
</p>

![Matriz](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/matriz_confus%C3%A3o.png)
<p align="left">
    <i>Imagem 25 - Matriz de confusão - dataset Titanic</i>
</p>

>###### Classificação probabilistíca
<p align="justify"> Usada para calcular a probabilidade de um passageiro ter sobrevivido ou não.
</p>

![Probabilidade](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/classifica%C3%A7ao_probabilistica.png)
<p align="left">
    <i>Imagem 26 - Classificação probabilistíca - dataset Titanic</i>
</p
 
>##### Cross validate
<p align="justify"> Usado para mostrar o desempenho do modelo para um novo conjunto de dados, a validação ocorre com ele particionando o conjunto de dados em subconjuntos, usando alguns subconjuntos para a estimação do treino e o restante para a estimação do teste.
</p>

![Cross_validate](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/cross_validate_titanic.png)
<p align="left">
    <i>Imagem 27 - Cross validate - dataset Titanic</i>
</p>


<br>

>#### 5.2 Processo de classificação na base de dados obtida:<br>
>...

### 6. Processos de Estimação  (explicação + datasets)<br>
    A) Explicação sobre o algoritmo/método de classificação adotado
    B) Implementar método nos datasets utilizados
    
<p align="justify">
O processo de estimação é considerado um tipo de classificação que trabalha visando prever o resultado com base num atributo de classe normalmente ponto flutuante (real/float), ou seja, a análise de regressão está relacionada a processos estatísticos utilizados visando estimar as relações entre uma variável dependente (variável alvo/target) e uma ou mais variáveis independentes (características/ features).
</p>

Usada principalmente para dois propósitos conceitualmente distintos:
- Predição e previsão;
- Inferir relações causais entre as variáveis independentes e dependentes.

<p align="justify">
É válido ressaltar que para usar regressões para previsão ou para inferir relações causais, respectivamente, um pesquisador deve justificar cuidadosamente porque as relações existentes têm poder preditivo para um novo contexto ou porque uma relação entre duas variáveis tem uma interpretação causal (lembrar por exemplo que correlação não implica em causa).
</p>

<br>

>#### 6.1 Processo de estimação/regressão na base de dados clássica:<br>

<p align="justify">
Uma vez que a regressão linear é utilizada para estimar valores reais baseado em variáveis contínuas, tivemos dúvidas quanto à aplicação da mesma no Titanic dataset, devido aos tipos dos dados. Entretanto, para meios didáticos de aprendizado, efetuamos o processo de regressão mesmo assim e, para isso, as variáveis escolhidas para realizar a estimação foram a ‘fareticket’ por ser um número flutuando e a ‘survived’ por definir quem (não) sobreviveu.
</p>


![Separando](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/titanic_separandoConjunto.PNG)

<br>

<p align="justify">
Foi construído um gráfico para observá-las.
</p>


![Gráfico](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/titanic_grafico1.png)

<br>
Visto isso, foi realizada a separação das variáveis.

![Separando 2](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/titanic_separandoConjunto2.PNG)

<br>

<p align="justify">
O modelo foi criado com a regressão linear e ajustado através da função fit(valoresFareTicket,valoresSurvived).
</p>

![Modelo](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/titanic_modelo.PNG)

<br>

A partir do modelo criado, obtivemos os fareTickets estimados.

![FareTickets estimados](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/titanic_fareticketEstimado.PNG)

<br>

Calculamos então as métricas de desempenho através da MSE e R², no qual:
- MSE (Erro Quadrático Médio): expressa a acurácia dos resultados numéricos do modelo, ou seja, quanto maior o valor, pior o desempenho. Erro neste caso significa a diferença dos valores observados.
- R²: é a variância explicada pelas variáveis independentes, ou seja, quanto maior o valor, maior a correlação.

![Metricas](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/titanic_metricas.PNG)

<br>

<p align="justify">
Sendo possível constatar, portanto, que de acordo com as métricas de desempenho aplicadas ao modelo, o mesmo pode ser considerado um mau modelo.
Ademais a isso, também foram calculados os coeficientes da equação de uma reta (Yi = β0 + β1 Xi), onde:
</p>

- β0: interseção, ou seja, valor de y (Survived) quando x (FareTicket) é zero.
- β1: inclinação da reta, ou seja, mede a variação em y dada uma variação em x.

![Coeficientes](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/titanic_coeficientes.PNG)

<br>

<p align="justify">
Portanto, através dos coeficientes angular e linear, pudemos aplicar a equação para cada valor de x e, assim, obter o valor esperado, também podendo comparar com o valor real e calculando os resíduos.
</p>

![Valor esperado](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/titanic_valorEsperado.PNG)
<br>

<p align="justify">
Por fim, geramos um gráfico para melhor visualização dos resultados obtidos através da função lmplot da biblioteca seaborn que desenha um gráfico de dispersão de duas variáveis (x e y), em seguida, ajustam o modelo de regressão e representam a linha de regressão resultante.
</p>

![Resultado](https://github.com/eduardarsimoes/lae1/blob/main/Titanic/imagens/titanic_resultado.png)

<br>
<br>

>#### 6.2 Processo de estimação/regressão na base de dados obtida:<br>
<p align="justify">
As variáveis escolhidas foram a Temperatura e a Altitude, visto que a altitude é um dos principais fatores que influenciam no clima, no qual ambas as variáveis representadas normalmente são grandezas inversamentes proporcionais, ou seja, quanto maior a altitude menor a temperatura e vice versa.
</p>

![Separando](https://github.com/eduardarsimoes/lae1/blob/main/Estacoes/Imagens/estacoes_separandoConjunto.PNG)

<br>

<p align="justify">
Então, foi construído um gráfico para observá-las em que podemos analisar a tendência linear.
</p>

![Gráfico](https://github.com/eduardarsimoes/lae1/blob/main/Estacoes/Imagens/estacoes_tendencialinear.png)

<br>

Visto isso, foi realizada a separação da variável independente e da variável dependente.

![Separando 2](https://github.com/eduardarsimoes/lae1/blob/main/Estacoes/Imagens/estacoes_separandoConjunto2.PNG)

<br>

<p align="justify">
O modelo foi criado com a regressão linear e ajustado através da função fit(valoresAtltitude,valoresTemperatura).
</p>

![Modelo](https://github.com/eduardarsimoes/lae1/blob/main/Estacoes/Imagens/estacoes_modelo.PNG)

<br>

A partir do modelo criado, obtivemos as temperaturas estimadas.

![Temperaturas estimadas](https://github.com/eduardarsimoes/lae1/blob/main/Estacoes/Imagens/estacoes_tempEstimada.PNG)

<br>

Calculamos então as métricas de desempenho através da MSE e R², no qual:
- MSE (Erro Quadrático Médio): expressa a acurácia dos resultados numéricos do modelo, ou seja, quanto maior o valor, pior o desempenho. Erro neste caso significa a diferença dos valores observados.
- R²: é a variância explicada pelas variáveis independentes, ou seja, quanto maior o valor, maior a correlação.

![Metricas](https://github.com/eduardarsimoes/lae1/blob/main/Estacoes/Imagens/estacoes_metricas.PNG)

<br>

<p align="justify">
Sendo possível constatar, portanto, que de acordo com as métricas de desempenho aplicadas ao modelo, o mesmo pode ser considerado um bom modelo.
Ademais a isso, também foram calculados os coeficientes da equação de uma reta (Yi = β0 + β1 Xi), onde:
</p>

- β0: interseção, ou seja, valor de y (temperatura) quando x (altitude) é zero.
- β1: inclinação da reta, ou seja, mede a variação em y dada uma variação em x.

![Coeficientes](https://github.com/eduardarsimoes/lae1/blob/main/Estacoes/Imagens/estacoes_coeficientes.PNG)

<br>

<p align="justify">
Portanto, através dos coeficientes angular e linear, pudemos aplicar a equação para cada valor de x e, assim, obter o valor esperado, também podendo comparar com o valor real e calculando os resíduos.
</p>

![Valor esperado](https://github.com/eduardarsimoes/lae1/blob/main/Estacoes/Imagens/estacoes_valorEsperado.PNG)

<br>

<p align="justify">
Por fim, geramos um gráfico para melhor visualização dos resultados obtidos, através da função lmplot da biblioteca seaborn que desenha um gráfico de dispersão de duas variáveis (x e y), em seguida ajusta o modelo de regressão e representa a linha de regressão resultante.
</p>

![Resultado](https://github.com/eduardarsimoes/lae1/blob/main/Estacoes/Imagens/estacoes_resultado.png)

<br>
<br>

># Marco de Entrega 02: Itens do Sprint 02

### 7. Automated machine learning - AutoML <br>
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

### 9. FORMATACAO NO GIT:<br> 
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


