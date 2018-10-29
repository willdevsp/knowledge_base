# Easy Admin - Criar redirecionamento HTTP para HTTPS [DEV]

A configuração é feita individualmente por **STORE_ID**. Segue passo a passo de como configurar:

* Entrar no servidor **comp301** via ssh com usuário **oracle**:
```sh
$ ssh oracle@comp301
```

* Antes de alterar o arquivo de configuração do Apache é recomendado fazer um backup do mesmo:
```sh
$ sudo cp httpd.conf httpd.conf-2018-08-23-1
```

* Abrir arquivo de configuração do Apache:
```sh
$ vim /opt/apache-2.4-nc-ad/conf/httpd.confg
```

* Procurar tag **VirtualHost** com primeira configuração de um loja (**SGHMX** por exemplo):
![image](/uploads/7abaa15849493f527de23495674b103c/image.png)

* Adicionar código abaixo logo após o **Include**:
```conf
# Redirect url easyadmin HTTP to HTTPS
RewriteCond %{HTTPS} off
RewriteRule ^/?easyadmin/(.*) https://%{SERVER_NAME}/easyadmin/$1 [R,L]
```

* Resultado final:
![image](/uploads/68de7a41b72d0ba4160f14f29d8f90f2/image.png)

* Agora será necessário reiniciar o Apache:
```sh
$ sudo sh /opt/apache-2.4-nc-ad/bin/apachectl restart
```
