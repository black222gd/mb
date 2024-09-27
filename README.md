# Documentação do Sistema de Agendamento

O Sistema de Agendamento é uma aplicação desenvolvida em Node.js, projetada para ajudar os usuários a gerenciar compromissos de maneira prática e eficiente. Ele serve principalmente para facilitar a vida cotidiana, permitindo que os usuários agendem, visualizem, editem e excluam compromissos de forma simples.

Com essa ferramenta, os usuários podem agendar compromissos para eventos importantes, como consultas médicas, reuniões ou atividades de lazer, além de visualizar todos os compromissos agendados de maneira clara. Isso contribui para uma melhor organização pessoal, evitando a perda de compromissos importantes e ajudando na programação de novas atividades.

A segurança é uma prioridade do sistema; ele utiliza criptografia para proteger as senhas dos usuários, garantindo que as informações pessoais permaneçam seguras. Além disso, validações rigorosas asseguram que apenas dados válidos sejam armazenados, minimizando erros.

A aplicação é acessível via terminal, tornando-a leve e fácil de usar em diferentes sistemas operacionais, o que a torna ideal para usuários com variados níveis de habilidade técnica. Também oferece um mecanismo seguro para recuperação de senhas, permitindo que os usuários redefinam suas credenciais em caso de esquecimento.

Em suma, o Sistema de Agendamento é uma ferramenta valiosa para qualquer pessoa que queira organizar melhor sua rotina, proporcionando um meio eficiente de gerenciar compromissos e garantindo a segurança das informações pessoais. É especialmente útil para estudantes, profissionais e qualquer um que busque aumentar sua produtividade e organização.

## Estrutura do Projeto

O sistema é implementado em JavaScript utilizando o Node.js e as seguintes bibliotecas:

- `readline`: Para interagir com o usuário via terminal.
- `fs`: Para manipulação de arquivos (leitura e escrita).
- `crypto`: Para a criptografia de senhas.

## Funcionalidades

### Registro de Usuário
- **Função**: `registro()`
- **Descrição**: Permite que um novo usuário registre-se no sistema.
- **Validações**:
  - Nome de usuário deve ter de 5 a 12 caracteres, apenas letras (A-Z, a-z).
  - E-mail deve ter um formato válido.
  - Senha deve conter de 6 a 12 caracteres, incluindo letras maiúsculas, minúsculas, números e símbolos.

### Login
- **Função**: `promptLogin()`
- **Descrição**: Permite que um usuário existente faça login.
- **Validações**: Verifica se o nome de usuário e a senha estão corretos.

### Recuperação de Senha
- **Função**: `recuperarSenhha()`
- **Descrição**: Permite que um usuário recupere sua senha, validando o nome de usuário e e-mail associados.

### Agendamentos
- **Marcar Agendamento**: `marcarAgendamento(username)`
- **Visualizar Agendamentos**: `visualizarAgendamento(username)`
- **Editar Agendamento**: `editarAgendamento(username, usuariosAgendados)`
- **Deletar Agendamento**: `deletarAgendamento(username, id)`

### Funções Auxiliares
- **Criptografia**: `criptografar(senha)`
- **Carregar Usuários**: `carregarUsuarios()`
- **Salvar Usuários**: `salvarUsuarios(usuarios)`
- **Carregar Agendamentos**: `carregarAgendamentos()`
- **Salvar Agendamentos**: `salvarAgendamentos(agendamentos)`

### Validações
- **Validação de Nome de Usuário**: `validacaoUsername(username)`
- **Validação de Senha**: `validacaoSenha(senha)`
- **Validação de E-mail**: `validacaoEmail(email)`

## Estrutura dos Dados

### Usuários
Os dados dos usuários são armazenados em um arquivo `users.json` com o seguinte formato:
```json
{
  "username": {
    "senha": "hash_da_senha",
    "email": "email_do_usuario"
  }
}
