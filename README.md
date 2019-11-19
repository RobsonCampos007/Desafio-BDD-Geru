# Desafio-BDD-Geru
Imagine que o PO do seu time acabou de escrever o esboço de uma story e apresentou a você;
BDD na Geru:
Hoje os QAs tem papel fundamental em todo o fluxo de desenvolvimento. Um de suas principais atividades é auxiliar o PO na construção das stories e criar bdds para que todos os envolvidos no projeto consigam trabalhar seguindo uma documentação em comum.

Desafio:
Imagine que o PO do seu time acabou de escrever o esboço de uma story e apresentou a você;

Como usuário quero conseguir realizar login na plataforma da Geru a fim de retornar para a solicitação do meu empréstimo ou ver as informações do meu empréstimo concedido.

Critérios de aceite:

Para que o usuário consiga se conectar ele precisa ter uma conta criada
É obrigatório o usuário informar o email e a senha
O usuário precisa clicar no botão entrar para acessar a plataforma
Deve ter um botão para que o usuário consiga acessar o esqueci minha senha caso ele não lembre mais da sua senha atual.
Caso o usuário esteja no fluxo de solicitação deve retornar para etapa posterior ao último envio de informações
Caso o usuário esteja concedido(dinheiro na conta e já pagando as parcelas) deve ser redirecionado para o dashboard.
Informações complementares Fluxo de solicitação fictício possui 4 etapas.

Dados Gerais
Dados Bancários
Assinatura
Envio de Documentos

# Acesso a conta na Geru
Cenário: Acesso a Conta na Geru
Dado que usuário possua conta cadastrada 
E esteja no site da Geru
Quando usuário acessar o menu Minha Conta
Então o sistema exibe a tela Acesse Sua Conta
E preencher o campo E-mail
E preencher o campo Senha
Então o sistema habilita o botão Entrar
E clicar no botão Entrar
Então o usuário acessa a plataforma da Geru com sucesso

# Usuário informa e-mail ou senha inválido
Cenário: Usuário esqueceu sua senha de acesso
Dado que usuário possua conta cadastrada
Quando o usuário acessar o menu Minha Conta
Então o sistema exibe a tela Acesse Sua Conta
E eu preencho o campo E-mail
E eu preencho o campo Senha inválida
E eu clico no botão Entrar
Então o sistema exibe a mensagem “Usuário ou senha incorretos”


# Usuário esqueceu a senha
Cenário: Usuário esqueceu sua senha de acesso
Dado que usuário possua conta cadastrada
Quando o usuário acessar o menu Minha Conta
Então o sistema exibe a tela Acesse Sua Conta
E usuário clicar no link esqueci minha senha
Então o sistema exibe a tela redefinir sehna
E usuário preencher o campo E-mail
E clicar no botão enviar e-mail verificação
Então o sistema exibe a mensagem “Um e-mail com as instruções de como
redefinir a sua senha foi enviado para você.”

# Usuário esteja concedido(dinheiro na conta e já pagando as parcelas)
Cenário: Usuário esteja concedido(dinheiro na conta e já pagando as parcelas)
Dado que usuário esteja na tela acesse sua conta
E usuário preencher o campo E-mail
E usuário preencher o campo Senha
Quando usuário clicar em entrar
Então o sistema redireciona para o dashboard

# Simular empréstimo
Cenário: simulação de empréstimo
Dado que usuário não possua conta cadastrada
E esteja no site da Geru
Quando usuário acessar empréstimo pessoal online
E clicar no campo quanto você precisa?
E clicar no campo em quantas parcelas?
Então o sistema abre a pop up simule sem compromisso
E preencher o campo nome
E preencher o campos e-mail
E preencher o campo cpf
E selecionar o campo qual a finalidade?
Então o sistema habilita o botão simular
E clicar no botão simular
Então o sistema exibe a mensagem "enviado e-mail para continuar o cadastro"

# Usuário cadastra a senha
Cenário: Acesso esteja no e-mail de cadastro
Dado que usuário nã possua conta cadastrada 
Quando usuário acessar o link do e-mail
Então o sistema exibe a tela para cadastrar senha
E preencher o campo senha
E preencher o campo conformar senha
E flegar no cmapo Li e aceito os termos
Então o sistema habilita o botão cadastrar senha

# Usuário esteja no fluxo de solicitação deve retornar para etapa posterior ao último envio de informações
Cenário: Acesso a última interação do fluxo de solicitação
Dado que sua último intreação foi em preencher cadastro
E possua conta cadastrada
Quando usuário esteja na tela minha conta
E preencher o campo e-mail
E preencher o campo senha
Então o sistema habilita o botão entrar
E clicar no botão entrar
E o sistema acesso a tela preencher cadastro

# Solicitação de empréstimo
Cenário: Solicitar um empréstimo pessoal
Dado que usuário possua conta cadastrada 
E esteja logado na plataforma
Quando usuário esteja na tela de solicitação
E preencher o campo Dados Gerais
E preencher o campo Dados Bancários
E preencher o campo Assinatura
E preencher o campo Envio de Documentos
Então o sistema concede o empréstimo pessoal.


