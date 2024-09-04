# AULA 1: Plann.er

# Sobre o projeto

> O projeto Journey tem como objetivo ajudar ****o usuário a organizar viagens à trabalho ou lazer. O usuário pode criar uma viagem com nome, data de início e fim. Dentro da viagem o usuário pode planejar sua viagem adicionando atividades para realizar em cada dia.
> 

## Requisitos

### Requisitos funcionais

1. O usuário cadastra uma viagem informando o local de destino, data de início, data de término, e-mails dos convidados e também seu nome completo e endereço de e-mail;
2. O criador da viagem recebe um e-mail para confirmar a nova viagem através de um link. Ao clicar no link, a viagem é confirmada, os convidados recebem e-mails de confirmação de presença e o criador é redirecionado para a página da viagem;
3. Os convidados, ao clicarem no link de confirmação de presença, são redirecionados para a aplicação onde devem inserir seu nome (além do e-mail que já estará preenchido) e então estarão confirmados na viagem;
4. Na página do evento, os participantes da viagem podem adicionar links importantes da viagem como reserva do AirBnB, locais para serem visitados, etc...
5. Ainda na página do evento, o criador e os convidados podem adicionar atividades que irão ocorrer durante a viagem com título, data e horário;
6. Novos participantes podem ser convidados dentro da página do evento através do e-mail e assim devem passar pelo fluxo de confirmação como qualquer outro convidado

# Criando o projeto

## Entidade Viagem

```jsx
    "destination": {
      "type": "string",
      "minLength": 4,
      "description": "O destino da viagem."
    },
    "starts_at": {
      "type": "string",
      "format": "date-time",
      "description": "A data e hora de início da viagem no formato RFC 3339."
    },
    "ends_at": {
      "type": "string",
      "format": "date-time",
      "description": "A data e hora de término da viagem no formato RFC 3339."
    },
    "emails_to_invite": {
      "type": "array",
      "items": {
        "type": "string",
        "format": "email"
      },
      "description": "Uma lista de emails a serem convidados para a viagem."
    },
    "owner_name": {
      "type": "string",
      "description": "O nome do proprietário da viagem."
    },
    "owner_email": {
      "type": "string",
      "format": "email",
      "description": "O email do proprietário da viagem."
    }
```

- [ ]  Criar projeto usando [Spring Initializr](https://start.spring.io/)
    - Spring Web
    - Flyway
    - Dev Tools
    - Lombok
    - JPA
    - H2 Database
- [ ]  Configurar banco de dados na aplicação
- [ ]  Criar migration para criação da tabela `trips`
    - Arquivos de Migration representam mudanças na estrutura do nosso banco de dados
        - criar uma tabela
        - alterar tabela, removendo campo, adicionando um campo
        - instalacao de driver
        - inserção em massa, de dados default
    - Arquivos de migration ⇒ scripts SQL, rodar comandos no banco
- [ ]  Criar entidades que irá representar uma `Trip`
- [ ]  Criar repository da entidade viagem
- [ ]  Criar endpoint de cadastro de viagem **`POST**/trips`
- [ ]  Criar endpoint de consulta de viagem **`GET**/trips/{tripId}`

# Pós-aula!!

- [ ]  Acessar comunidade do Discord
    - [ ]  Para tirar dúvidas e ajudar outros devs
- [ ]  Completar a aula na plataforma para concorrer a prêmios


# AULA 2: Plann.er

Nessa aula iremos implementar finalizar as funcionalidades das viagens e o cadastro e confirmação de participantes

- [ ]  Criar endpoint de atualização de viagem **`PUT**/trips/{tripId}`
- [ ]  Criar endpoint confirmação de viagem **`GET**/trips/{tripId}/confirm`
- [ ]  Criar tabela de `Participant`
- [ ]  Criar entidade que irá representar um`Participant`
- [ ]  Criar repository da entidade participante
- [ ]  Criar endpoint confirmação de participante **`POST**/participants/{participantId}/confirm`
- [ ]  Criar endpoint para convidar participante **`POST**/trips/{tripId}/invites`
- [ ]  Criar endpoint para consultar participantes **`GET**/trips/{tripId}/participants`

# Pós-aula!!

- [ ]  Acessar comunidade do Discord
    - [ ]  Para tirar dúvidas e ajudar outros devs
- [ ]  Completar a aula na plataforma para concorrer a prêmios


# AULA 3: Plann.er

Nessa aula iremos implementar todas as funcionalidades que dizem respeito as atividades da viagem e os links:

- [ ]  Criar tabela de `Activities`
- [ ]  Criar entidade que irá representar uma `Activity`
- [ ]  Criar repository da entidade atividade
- [ ]  Criar endpoint para cadastro de atividade **`POST**/trips/{tripId}/activities`
- [ ]  Criar endpoint para consultar atividades de uma viagem **`GET**/trips/{tripId}/invites`
- [ ]  Criar tabela de `Links`
- [ ]  Criar entidade que irá representar um `Link`
- [ ]  Criar repository da entidade links
- [ ]  Criar endpoint para criação de link **`POST**/trips/{tripId}/links`
- [ ]  Criar endpoint para consultar links de uma viagem **`GET**/trips/{tripId}/links`

## Features extras

- [ ]  Adicionar uma validação nos campos de data
    - [ ]  A data de começo da viagem, é inferior a data de término viagem
    - [ ]  A data de uma atividade está entre as datas da viagem
        
        **Exemplo:**
        Viagem entre os dias 20 á 25 de julho no Rio de Janeiro
        
        ⇒ Atividade 19 de julho
        
        ⇒ Atividade 21 de julho
        
- [ ]  Extração do core das trips pra dentro de uma classe Service
- [ ]  Mapeamento das exceções da nossa aplicação
    - [ ]  Com tratativas de erro personalizadas
     


# EXTRA: Instalação do **IntelliJ IDEA**

Nesse passo a passo vamos entender como realizar a instalação do **IntelliJ IDEA**  na versão gratuita na nossa máquina

> **ATENÇÃO: Realize a instalação do IntelliJ somente após ter o JDK instalado na sua máquina**
> 

# Download

1. Acessar o [site para download](https://www.jetbrains.com/idea/download/) do **IntelliJ IDEA**
2. Escolher a versão: IntelliJ IDEA Community Edition
    
    ![Screenshot 2024-04-01 at 13.51.53.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7e08ccba-1e15-4032-8025-5db6afff0a93/f30b872a-ff47-4a93-98c3-5843a85cda94/Screenshot_2024-04-01_at_13.51.53.png)
    
3. Após feito o download do installer, siga as instruções do próprio aplicativo para finalizar a instação na máquina

# Configuração

Com o IntelliJ instalado, precisamos nos certificar que ele está encontrando o JDK para realizar a compilação e execução dos nossos projetos.

**FAÇA ISSO QUANDO JÁ TIVER O PROJETO CRIADO NO SPRING INITIALZER**

1. Abra o IntelliJ
2. Clique para abrir um novo projeto
3. Selecione a pasta do projeto descompactada que acabou de criar usando o Spring Initializer
4. Após importar o projeto, o IntelliJ pode solicitar que você configure o SDK que será usado
    - Se necessário, selecione a versão do JDK que você deseja usar para o projeto.
    - Se o JDK não estiver listado, clique em "Add SDK" (Adicionar SDK) e navegue até o local onde o JDK está instalado no seu sistema
5. E agora na classe principal da sua aplicação, você pode tentar executar seu projeto usando o botão verde de Run Application

![Screenshot 2024-04-01 at 14.06.58.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7e08ccba-1e15-4032-8025-5db6afff0a93/6d50e754-9456-4748-b516-ded7d905324d/Screenshot_2024-04-01_at_14.06.58.png)

## Conferindo

Após a sincronização do projeto com o JDK, você pode verificar se as configurações do projeto estão corretas. 

Você pode fazer isso acessando "File" > "Project Structure" > "Project" (Arquivo > Estrutura do Projeto > Projeto). 

Certifique-se de que o SDK correto está selecionado e que as configurações do projeto estão conforme o esperado.

![Screenshot 2024-04-01 at 14.01.13.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7e08ccba-1e15-4032-8025-5db6afff0a93/5f9d3d6c-28d1-48bc-8ef6-9c54fbd29882/Screenshot_2024-04-01_at_14.01.13.png)

### Em caso de não encontrar o SDK

Caso não tenha nenhum SDK selecionado, você pode adicionar um novo na aba “SDKs”

1. Clique em SDKs, no canto esquerdo abaixo de Platform Settings ou Configurações de Plataforma

![Screenshot 2024-04-01 at 14.02.04.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7e08ccba-1e15-4032-8025-5db6afff0a93/43953be1-00e4-4780-8cb1-861d41424f65/Screenshot_2024-04-01_at_14.02.04.png)

1. Clique no +
    
    ![Screenshot 2024-04-01 at 14.02.54.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7e08ccba-1e15-4032-8025-5db6afff0a93/45818999-3726-481b-9cd5-58515f5870fa/Screenshot_2024-04-01_at_14.02.54.png)
    
    1. Clique em Add JDK ou Adicionar JDK
    
    ![Screenshot 2024-04-01 at 14.03.10.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7e08ccba-1e15-4032-8025-5db6afff0a93/ccbda75f-5dde-48a1-8596-7d175e853dd4/Screenshot_2024-04-01_at_14.03.10.png)
    
    1. Selecione a pasta onde foi instalado a sua JDK local
    
    ![Screenshot 2024-04-01 at 14.04.00.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7e08ccba-1e15-4032-8025-5db6afff0a93/e62c2bc7-2b5d-4ecd-81db-b77c1c31d510/Screenshot_2024-04-01_at_14.04.00.png)
    
    1. Feito isso você pode dar o nome que preferir
        
        ![Screenshot 2024-04-01 at 14.05.38.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7e08ccba-1e15-4032-8025-5db6afff0a93/ac110d25-df73-4041-b406-feb201b1199e/Screenshot_2024-04-01_at_14.05.38.png)
        
    2. E agora voltando para Project ou Projeto, você pode selecionar o JDK recém configurado como o SDK para seu projeto
    
    ![Screenshot 2024-04-01 at 14.05.54.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7e08ccba-1e15-4032-8025-5db6afff0a93/17e95546-2f64-47c6-84d0-07198b510382/Screenshot_2024-04-01_at_14.05.54.png)
    
    1. Clique em Apply e OK
    
    ![Screenshot 2024-04-01 at 14.06.29.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7e08ccba-1e15-4032-8025-5db6afff0a93/2cfa9fa5-036f-4f82-807c-a83439b142e4/Screenshot_2024-04-01_at_14.06.29.png)
    
    1. E agora na classe principal da sua aplicação, você pode tentar executar seu projeto usando o botão verde de Run Application
