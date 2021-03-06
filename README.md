# GeMan:  Sistema de Gestão da Manutenção do IFES
Trabalho desenvolvido durante a disciplina de BD

# Sumário

### 1. COMPONENTES<br>
Integrantes do grupo:<br>
Gabriel Marchezi: gabriel_marchezi@hotmail.com<br>
Helen França: helenfranca93@gmail.com<br>
Olavo Curátola: olavo.curatola@gmail.com<br>

### 2.INTRODUÇÃO E MOTIVAÇAO<br>
Este documento contém a especificação do projeto do banco de dados do Sistema de Gestão da Manutenção dos Equipamentos e Instalações do IFES <nome do projeto> 


<br>Sistema de Gestão da Manutenção dos Equipamentos e Instalações do IFES <br>
Analisando o nível de utilização atual dos equipamentos e instalações do Instituto Federal do Espírito Santo - IFES - Campus Serra, principalmente em função do aumento do número de usuários e da importância de se garantir a disponibilidade e reduzir a degradação dos equipamentos, consideramos ser necessário implementar um maior envolvimento dos usuários atraves de um sistema informatizado com interface para smartphones.
O sistema almeja dar suporte à manutenção de salas, laboratórios, banheiros e demais instalações, bem como cadeiras, mesas, bancadas, computadores, monitores, projetores, iluminação, tomadas, modens, sistemas de som, e etc. Consequentemente procuramos viabilzar a implantação de um sistema em que os alunos, professores e demais funcionários possam  comunicar ao setor responsável qualquer mal funcionamento ou falha de equipamentos ou instalações para e destacar a necessidade de manutenção ou troca.
<br>A partir de um smartphone, com câmera e acesso a internet, o usuário preenche um formulário em uma aplicação, ou via site web (portabilidade), gerando uma ocorrência. Os dados são então enviados via sistema de gestão da manutenção ao setor responsável para as providências necessárias. O setor responsável deverá responder aos usuários quanto as providências até a solução definitiva da ocorrência registrada, com posterior avaliação pelos usuários.

### 3.MINI-MUNDO<br>

<br>Descrição do GeMan<br>
<br>   O sistema de gestão de manutenção GeMan objetiva dar suporte à realização dos serviços de manutenção de equipamentos e instalações, bem como às atividades de administração e controle da manutenção. O sistema será composto de:<br>
<br>Cadastro de Local e Instalações, Cadastro de Equipamentos, Identificação de Locais e Equipamentos por Barcode, Cadastro de Usuários, Cadastro de Padrões de Serviço, Cadastro de Planos de Manutenção, Abertura de Ordem de Serviço, Programação da Ordem de Serviço - Execução, Fechamento da Ordem de Serviço – Execução, Histórico de Ordens de Serviço Executadas, Registro de Ocorrências pelo Usuário, Histórico de Ocorrências por Usuário, Feedback ao Usuário, e Avaliação da Solução da Ocorrência pelo Usuário.<br>

<br>    O gerenciamento do sistema é de responsabilidade da equipe de manutenção. O cadastramento dos Locais e Instalações, e dos Equipamentos e a Identificação com Barcode será realizado com base em desenhos e manuais e demais documentos técnicos.<br>
<br>   Os padrões de serviço e a elaboração dos planos de manutenção serão elaborados com base nas recomendações dos fabricantes dos equipamentos, nas melhores práticas das especialidades e na experiência da equipe de manutenção.<br>
<br>   As ocorrências serão geradas pelos usuários cadastrados no sistema que a princípio seriam os alunos, professores e demais funcionários exceto pessoal da equipe de manutenção. O usuário geraria a ocorrência ao se deparar com um mal funcionamento ou indisponibilidade de equipamentos ou instalações. Para isto usaria a interface mobile para descrever e identificar o local ou equipamento, com barcode ou patrimônio, acompanhado eventualmente de uma foto.<br>
<br>   O supervisor de manutenção será responsável por promover a classificação e agrupamento das ocorrências geradas e pela abertura da ordem de serviço para diagnóstico e solução do problema reportado na ocorrência e pelo feedback ao usuário.<br>

### 4.RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>
Os protótipos de telas, desenvolvidas para este banco de dados de manutenção, permitirão o acesso por smartphones e via computadores pessoais ou computadores de mesa.<br>
Mobile - https://github.com/GeManBD/GeMan-Project/blob/master/Prototipos/Prot%C3%B3tipo-Mobile%202017-04-09.pdf<br>
Desktop - https://github.com/GeManBD/GeMan-Project/blob/master/Prototipos/Prot%C3%B3tipo-Desktop2017-04-09.pdf<br>
 
#### 4.1 TABELA DE DADOS DO SISTEMA:
    Esta tabela deve conter todos os atributos do sistema e um mínimo de 10 linhas.
    (esta tabela tem a intenção de simular um relatório com todos os dados que serão armazenados 
    e deve ser criada antes do modelo conceitual)

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/Tabela%20Dados-1.PNG)

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/Tabela%20Dados-2.PNG)

![Alt text](https://github.com/GeManBD/trab01/blob/master/Tabela%20do%20sistema.PNG)

### 5.MODELO CONCEITUAL<br>
    A) NOTACAO ENTIDADE RELACIONAMENTO
![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/Imagens%20Projeto/GeMan_Conceitual_v9.1.jpg)
   
    B) NOTACAO UML (Caso esteja fazendo a disciplina de analise)
    C) QUALIDADE 
        Garantir que a semântica dos atributos seja clara no esquema
        Criar o esquema de forma a garantir a redução de informação redundante, possibilidade de valores null, 
        e tuplas falsas
    
#### 5.1 Validação do Modelo Conceitual
    BCLL-CantinaIFES: Brenno Milanezi, Luiz Antônio Roque, Caio Pupolin
    Projeto Evasão/Automação Assistência Estudantil: Paulo Ricardo Viana, Antônio carlos Lemos, Lucas Oliveira Garcia

#### 5.2 DECISÕES DE PROJETO
    Em todo projeto decidimos por seguir a normalidade aplicada a criação de banco de dados.
    
    [atributo]: [descrição da decisão]
    
    EXEMPLO:
    a) Campo endereço: em nosso projeto optamos por um campo multivalorado e composto, pois a empresa 
    pode possuir para cada departamento mais de uma localização... 
    b) justifique!

#### 5.3 DESCRIÇÃO DOS DADOS 
 
   Padrao: Tabela que armazena dados dos Padrões de Serviço;<br>
           ID: Número Serial atribuído a cada Padrão (chave primária da Tabela Padrao);<br>
           Descricao: Descrição do Padrão de Serviço, ou seja, como o serviço deve ser feito, seguindo<br>
           instruções de segurança, manuseio, ferramentas e outros;<br>
           Link: URL para acesso do Padrão de Serviço;<br>
   
   Status: Tabela que possui as 3 situações possíveis de uma ocorrência;<br>
           ID: Número Serial atribuído a cada um dos 3 status de uma ocorrência(chave primária da Tabela<br>
           Status);<br>
           Nome: Definição de cada Status. Podendo ser “resolvido”, “em andamento” e “em espera”;<br>
   
   Andar: Tabela que contém os andares das instalações;<br>
           ID: Número Serial atribuído a cada andar (chave primária da Tabela Andar);<br>
           Nome: Definição do andar (Ex: Primeiro andar, Segundo andar...);<br>

   Plano: Tabela que contém os dados do Plano de Manutenção;<br>
          ID: Número Serial atribuído a cada Plano de Manutenção (chave primária da Tabela Plano);<br>
          Nome: Atividade a ser executada de acordo com o plano de manutenção (Ex: Revisão dos<br>
          projetores, limpeza dos aparelhos de ar-condicionado);<br>
          Frequencia: Intervalo de tempo, em meses, entre as execuções da tarefa em específico;<br>

   Perfil: Tabela que possui os 3 perfis possíveis de um usuário;<br>
          ID: Número Serial atribuído a cada Perfil de Usuário (chave primária da Tabela Perfil);<br>
          Nome: Caracteriza o usuário a qual foi relacionado como “Aluno”, ”Servidor” ou<br>
          “Manutenção”. <br>

   Local: Tabela que possui dados dos locais das instalações sob domínio do GeMan;<br>
          ID: Número Serial atribuído a cada Local (chave primária da Tabela Local);<br>
          Bloco: Bloco no qual está presente o local;<br>
          Nome: Nome do local (Ex.: Sala 107, Lab. 208);<br>
          ID_ANDAR: Andar no qual o local se encontra (chave estrangeira exportada da Tabela Andar);<br>

   Equipamento: Tabela que possui dados dos Equipamentos sob domínio do GeMan;<br>
          ID: Número Serial atribuído a cada Equipamento (chave primária da Tabela Equipamento);<br>
          Nome: Nome do equipamento (Ex.: Cadeira, Mesa, Projetor...);<br>
          Descrição: Características do equipamento em questão;<br>
          ID_LOCAL: Local em que se encontra o equipamento(chave estrangeira exportada da Tabela<br>
          Local);<br>

   Usuario: Tabela que possui as informações dos usuários cadastrados no GeMan;<br>
          ID: Número Serial atribuído a cada usuário (chave primária da Tabela Usuario);<br>
          Matricula: O número de matrícula do aluno ou servidor;<br>
          Nome: Nome do Usuário (Ex.: Olavo Curatola);<br>
          Login: Login de acesso escolhido pelo usuário;<br>
          Senha: Senha de acesso escolhida pelo usuário;<br>
          Email: E-mail cadastrado pelo usuário;<br>
          ID_PERFIL: Define se o usuário é aluno, professor ou técnico de manutenção (chave estrangeira<br>
          exportada da Tabela Perfil);<br>
          
   Ordem_de_Servico: Tabela que possui as informações das ordens de serviço;<br>
          ID: Número Serial atribuído a cada Ordem de Serviço (chave primária da Tabela<br>
          Ordem_de_Servico);<br>
          Descricao: Pequeno texto que informa o objetivo do serviço;<br>
          Data: data de execução do serviço;<br>
          ID_EQUIPAMENTO: Número Serial do equipamento alvo do serviço (chave estrangeira<br>
          exportada da Tabela Equipamento);<br>
          ID_OCORRENCIA: Número Serial da ocorrência que gerou a ordem de serviço (chave<br>
          estrangeira exportada da Tabela Ocorrencia);<br>
          ID_PLANO: Número Serial do Plano de Manutenção (chave estrangeira exportada da Tabela<br>
          Plano);<br>
          ID_PADRAO: Número Serial do Padrão de Serviço a ser adotado pela Ordem de Serviço (chave<br>
          estrangeria exportada da Tabela Padrao); <br><br>       

   Ocorrencia: Tabela que possui as informações das Ocorrências;<br>
          ID: Número Serial atribuído a cada ocorrência (chave primária da Tabela Ocorrencia);<br>
          Descricao: Pequeno texto descritivo, deixando claro a situação que motivou a abertura da<br>
          ocorrência;<br>
          Data: Data da abertura da ocorrência;<br>
          Feedback: Pequeno texto enviado, por um técnico de manutenção, ao usuário que abriu a<br>
          ocorrência;<br>
          ID_STATUS: Situação da ocorrência(chave estrangeira exportada da Tabela Status); <br>
          ID_USUARIO: Número Serial atribuído ao usuário que abriu a ocorrência (chave estrangeira da<br>
          Tabela Usuario);<br>
          Matricula: Número de Matrícula do usuário que abriu a ocorrência (chave estrangeria da<br>
          Tabela Usuario);<br>
    
    

    
https://github.com/GeManBD/GeMan-Project/blob/master/GeMan_Descricao-PDF.pdf


### 6	MODELO LÓGICO<br>
        a) inclusão do modelo lógico do banco de dados
![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/Imagens%20Projeto/modelo_logico_v9.1.jpg)

        b) verificação de correspondencia com o modelo conceitual 
        (não serão aceitos modelos que não estejam em conformidade)

### 7	MODELO FÍSICO<br>
        a) inclusão das instruções de criacão das estruturas DDL (criação de tabelas, alterações, etc..)
        Entrega até este ponto em: (Data a ser definida)
https://raw.githubusercontent.com/GeManBD/GeMan-Project/master/GeMan-BD-CREATE.sql

### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
        Detalhamento sobre as informações e processo de obtenção ou geração dos dados.
        Referenciar todas as fontes referentes a :
        a) obtenção dos dados
        b) obtenção de códigos reutilizados
        c) fontes de estudo para desenvolvimento do projeto


#### 8.2 INCLUSÃO DO SCRIPT DE INSERÇÃO DOS DADOS
        a) inclusão das instruções de inserção dos dados nas tabelas criadas pelo script de modelo físico
        b) inclusão das instruções para execução de outros procedimentos necessários (caso existam) 
https://raw.githubusercontent.com/GeManBD/GeMan-Project/master/GeMan-BD-INSERT.sql

#### 8.3 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELA E INSERÇÃO DOS DADOS
        a) Junção dos scripts anteriores em um único script 
        (tabelas e estruturas de dados + dados a serem inseridos)
        b) Criar um novo banco de dados para testar a restauracao 
        (em caso de falha na restauração o grupo não pontuará neste quesito)
        
https://github.com/GeManBD/GeMan-Project/blob/master/GeMan-BD-CREATE-INSERT.sql

        Entrega até este ponto em: (Data a ser definida)


### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>
 
SELECT * FROM andar ORDER BY id DESC

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/print_select_andar.png)

SELECT * FROM equipamento ORDER BY id ASC 

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/print_select_equipamento.png)

SELECT * FROM local ORDER BY id ASC 

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/print_select_local.png)

SELECT * FROM ocorrencia ORDER BY id ASC 

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/print_select_ocorrencia.png)

SELECT * FROM ordem_de_servico ORDER BY id ASC 

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/print_select_ordem_de_servico.png)

SELECT * FROM padrao ORDER BY id ASC 

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/print_select_padrao.png)

SELECT * FROM perfil ORDER BY id ASC 

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/print_select_perfil.png)

SELECT * FROM plano ORDER BY id ASC 

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/print_select_perfil_plano.png)

SELECT * FROM status ORDER BY id ASC 

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/print_select_status.png)

SELECT * FROM usuario ORDER BY matricula ASC, id ASC 

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/print_select_usuario.png)

#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 3)<br>

SELECT nome FROM andar WHERE id >  1;

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/select_92_1.PNG)

SELECT nome FROM usuario WHERE id_perfil = 3;

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/select_92_2.PNG)

SELECT patrimonio FROM equipamento WHERE nome = 'Ar condicionado';

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/select_92_3.PNG)

#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E CAMPOS RENOMEADOS (Mínimo 2)<br>

SELECT equipamento.patrimonio AS "Patrimônio", equipamento.nome AS "Equipamentos do Primeiro Andar" FROM equipamento
INNER JOIN local<br>
ON (local.id_andar=2)<br>
GROUP BY equipamento.patrimonio, equipamento.nome HAVING equipamento.patrimonio<900000<br>
ORDER BY equipamento.patrimonio<br>

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/select_93_1.PNG)

SELECT ordem_de_servico.descricao AS "OS - Aberta", ocorrencia.descricao AS "Problema Relatado" FROM ordem_de_servico<br>
INNER JOIN ocorrencia<br>
ON (ocorrencia.id=ordem_de_servico.id_ocorrencia )<br>
GROUP BY ocorrencia.id, ordem_de_servico.descricao,ordem_de_servico.data<='2017/07/01' HAVING ordem_de_servico.data<='2017/07/01'<br>
ORDER BY ocorrencia.id<br>

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/select_93_2.PNG)

#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE (Mínimo 3) <br>

SELECT * FROM usuario WHERE nome LIKE 'D%';

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/select_94_1.PNG)

SELECT * FROM ordem_de_servico WHERE descricao LIKE 'Verificar%';

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/select_94_2.PNG)

SELECT * FROM local WHERE nome LIKE 'Sala%';

![Alt text](https://github.com/GeManBD/GeMan-Project/blob/master/imagens/select_94_3.PNG)

#### 9.5	ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>
https://github.com/GeManBD/GeMan-Project/blob/master/atual_exclude.sql<br>
#### 9.6	CONSULTAS COM JUNÇÃO E ORDENAÇÃO (Todas Junções)<br>
https://github.com/GeManBD/GeMan-Project/blob/master/join_group.sql<br>
#### 9.7	CONSULTAS COM GROUP BY (Mínimo 5)<br>
https://github.com/GeManBD/GeMan-Project/blob/master/group_by.sql<br>
#### 9.8	CONSULTAS COM LEFT E RIGHT JOIN (Mínimo 4)<br>
https://github.com/GeManBD/GeMan-Project/blob/master/left_right_join.sql<br>
#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Todas Possíveis)<br>
https://github.com/GeManBD/GeMan-Project/blob/master/self_join_view.sql<br>
#### 9.10	SUBCONSULTAS (Mínimo 3)<br>
        Entrega até este ponto em: (Data a ser definida)
### 10	ATUALIZAÇÃO DA DOCUMENTAÇÃO DOS SLIDES PARA APRESENTAÇAO FINAL (Mínimo 6 e Máximo 10)<br>
### 11	TUTORIAL COMPLETO DE PASSOS PARA RESTAURACAO DO BANCO E EXECUCAO DE PROCEDIMENTOS ENVOLVIDOS NO TRABALHO PARA OBTENÇÃO DOS RESULTADOS<br>
        a) Outros grupos deverão ser capazes de restaurar o banco 
        b) executar todas as consultas presentes no trabalho
        c) executar códigos que tenham sido construídos para o trabalho 
        d) realizar qualquer procedimento executado pelo grupo que desenvolveu o trabalho
        
### 12   DIFICULDADES ENCONTRADAS PELO GRUPO<br>
### 13   TRABALHO DE MINERAÇÃO DE DADOS
        a) captura das informaçõs
        b) integração com banco de dados em desenvolvimento
        c) atualização da documentação do trabalho incluindo a mineração de dados
        
### 13  FORMATACAO NO GIT: https://help.github.com/articles/basic-writing-and-formatting-syntax/

### 14 Backup completo do banco de dados postgres 
    a) deve ser realizado no formato "backup" 
        (Em Dump Options #1 Habilitar opções Don't Save Owner e Privilege)
    b) antes de postar o arquivo no git o mesmo deve ser testado/restaurado por outro grupo de alunos/dupla
    c) informar aqui o grupo de alunos/dupla que realizou o teste.
    
### OBSERVAÇÕES IMPORTANTES

#### Em tese todos os arquivos do trabalho devem ser compartilhados no git 
1. Caso existam arquivos com conteúdos sigilosos, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário deste GIT, para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.



