# Easy Admin - Adicionar Certificado SSL [DEV]

Com a mudança das lojas em DEV para HTTPS o Browser passou a bloquear algumas requisições de APIs feitas com HTTP, ver exemplo abaixo:

![image](/uploads/36f4b8ab26ebd29e2caec6730f8070d6/image.png)

Para resolver esse problema é necessário adicionar um certificado SSL na configuração **VirtualHost** na porta 443 da loja. Primeiramente abra o arquivo `httpd.confg` do Apache no servidor **comp301**. Ver os primeiros passos da configuração [Criar redirecionamento de requisições HTTP para HTTPS](easyadmin/config/apache/Redirecionamento-HTTP-para-HTTPS).

* Procurar tag **VirtualHost** na porta 443 da configuração de uma loja (**TESC** por exemplo):

![image](/uploads/8bc62e5326f34a3e1e02a40e726e76b0/image.png)

* Adicionar código abaixo logo após o **Include**:
```conf
SSLEngine on
#SSLCipherSuite ALL:!ADH:!EXPORT56:RC4+RSA:+HIGH:+MEDIUM:+LOW:+SSLv2:+EXP:+eNULL
#SSLv3 and TLSv1
#SSLProtocol -ALL +SSLv3 +TLSv1
#SSLCipherSuite ALL:!ADH:RC4+RSA:+HIGH:+MEDIUM:-LOW:-SSLv2:-EXP
SSLCertificateFile /opt/ssl/star-infracommerce.com.br-2018/star-infracommerce.com.br.crt
SSLCertificateKeyFile /opt/ssl/star-infracommerce.com.br-2018/star-infracommerce.com.br.key
SSLCACertificateFile /opt/ssl/star-infracommerce.com.br-2018/star-infracommerce.com.br.ca.crt
```

* Resultado final:

![image](/uploads/94f1978947a54b050e200efdca6c15a6/image.png)

* Agora será necessário reiniciar o Apache:

```sh
$ sudo sh /opt/apache-2.4-nc-ad/bin/apachectl restart
```