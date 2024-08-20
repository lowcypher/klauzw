# klauzw
Sistema Simples de Armazenamento de Senhas

Sistema KlauzW

Com base no sistema Klauz 3 em Python, esta ferramenta é voltada para Web.
Utiliza PHP/Bootstrap e MySQL.

Arquivos que devem ser ajustados antes do uso do sistema.
Dentro do diretório "extras" possui o arquivo SQL com a estrutura do banco, sem os dados.

Ajuste o arquivo conexao.php com o usuário e senha do banco.

O banco de dados se chama password_manager, mas pode ser outro qualquer, mas então precisa
modificar o arquivo de conexão para que acesse o banco com o nome diferente do pré-definido.

O sistema utiliza criptografia AES-256-CBC com chave/senha. Isso faz com que as senhas gravadas no banco
sejam criptografadas. Para poder ler as senhas em modo de texto plano, somente dentro da aplicação. 

Para isso os arquivos que grava/edita/visualiza as senhas gravadas, precisam ter uma senha/chave para isso.

Os arquivos são:

cadastrar_registro.php - este arquivo cadastra os registros e criptografa as senhas para o campo senha no banco.
dashboard.php - este tem o bloco com a função de descriptografar as senhas para serem exibidas.
editar_registro.php - para editar o registro, incluindo a senha a ser mostrada.
exportar_pdf.php - para exportar todos os registros com as senhas em texto plano, num relatório em PDF.

Nos arquivos, na linha onde for encontrado "senha-a-ser-definida" coloque uma senha forte.

Os arquivos devem estar no seu diretório de páginas do Apache. Eu utilizo o módulo "user_dir",
mas pode ser mesmo em /var/www/html/
No diretório principal/raiz do projeto (klauzw que utilizo) atribua permissões 755 e no subdiretório klauz/vendor 777 
Esta permissão 777 é para que a biblioteca mPDF possa gravar os arquivos temporários e gerar o PDF.

No primeiro acesso, abra o arquivo "cads.php" e cadastre seu usuário/proprietário do sistema. 
Só haverá este usuário/propietário.

Após o cadastro deste usuário/proprietário será redirecionado para a página de login. 
Nesta página só existe o campo de senha, uma vez que só existe um usuário no sistema.

Se autentique no sistema e já poderá cadastrar os serviços que exijam senha de acesso.

Obs: depende da biblioteca mPDF. 
Use no diretório raiz do projeto: composer require mpdf/mpdf

Sistema: KlauzW

Data: 2024-08-18

Versão: 0.7.5

Autor: Mario Medeiros - Disaster Developer

Site: https://www.mariomedeiros.eti.br
