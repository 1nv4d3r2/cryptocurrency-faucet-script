INSTALAR:

Baixe o projeto e descompacte para o diretório raiz do seu servidor web (ou seja, www/html)


Editar config.php

- $don_faucet: Coind address label used for donations/payouts.
- $btclogin:   RPC User/Pass settings
- $sqllogin:   Database user/pass settings


Adicione IP remoto para acessar o painel de administração / servidor

- Edit header.php to include remote IP for Server/Admin panel access (Line 96)
- Edit server.php to accept remote IP for Server/Admin panel access (Line 21)



Base de dados

- Create SQL user matching config and grant full permissions to faucet database:
- CREATE USER 'username'@'localhost' IDENTIFIED BY 'mypass';
- GRANT ALL ON dbname.* TO 'user'@'localhost';
Importe faucet.sql para seu banco de dados:
- Change to "core" directory
- mysql -u user -p database < faucet.sql
Ou se você estiver usando um frontend GUI (PHPMyadmin, ADminer, etc), apenas crie o banco de dados e importe o arquivo .sql para ele.

Notas:
Qualquer nome de conta definido no arquivo de configuração deve corresponder ao nome real da Carteira no daemon. IE Uma carteira rotulada como 'FaucetWallet' na configuração deve ter o mesmo nome (FaucetWallet) no Daemon da carteira.
