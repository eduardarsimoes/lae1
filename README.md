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
<br>Visão geral das bases de dados<br>

> Após obter a(s) base(s) de dados Responda as seguintes perguntas sobre o conjunto de dados:
* seus dados são sobre o que? 
* o que você deseja com este conjunto de dados?
* quais são os tipos de atributos existentes e qual é o atributo alvo? 
* quais são os problemas existentes?
* qualidade e clareza: garantir que a semântica dos atributos seja clara (nomes coerentes com os dados, se necessário renomear atributos).

>#### 2.1 Visão geral da base de dados clássica:<br>
A base de dados possui informações a respeito dos tripulantes do navio Titanic, como informações pessoais desde o nome, idade, suas relações familiares a bordo e embarque, se sobreviveram etc, no qual deseja-se prever se certos dados de um indivíduo aumentam a chance de sobrevivência e se sim, quais seriam os fatores, sendo portanto o survived o atributo alvo. Foi possível observar que os tipos de atributos existentes são categóricos (nominais e binário) e também numéricos (discreto e contínuo). Ademais a isso, acredita-se que existem atributos irrelevantes para o propósito estabelecido como passengerId, name, cabin e ticket, pois não influenciam na sobrevivência (ou não sobrevivência) do indivíduo. É válido ressaltar que a base possui 891 registros e foi disponibilizada em formato csv. 
Analisando os problemas existentes na base foi encontrado incompletude (valores ausentes referentes a cabine, idade e porto de embarque), inconsistência (violação de domínio na idade e algumas discrepâncias quando preço da passagem e classe do navio são associados). Visto isso, para melhor clareza e qualidade dos dados, alguns atributos foram renomeados para melhor entendimento, são eles:
- SibSp: siblingsSpousesOnboard <br>
- Parch: parentsChildrenOnboard <br>
- Fare: fareTicket <br>
- Embarked: embarkedHarbor <br>
- pClass: shipClass <br>

>#### 2.2 Visão geral da base de dados em estudo:<br>
>... 

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


