# HAProxy
Balanceador como container simples 

## Diretórios
Crie a seguinte estrutura de diretórios e/ou ajuste os caminhos nos arquivos.
````
../haproxy/
├── conf
│   └── haproxy.cfg
├── docker-compose.yaml
└── pki
    ├── ctrl-list.txt
    ├── dhparam.pem
    └── server.pem
````
## Keystore
Mescle suas chaves pública e privada em um único arquivo por host:
```
cat fulchain1.pem privkey1.pem > ../haproxy/pky/server1.pem
cat fulchain2.pem privkey2.pem > ../haproxy/pky/server2.pem
cat fulchain3.pem privkey3.pem > ../haproxy/pky/server3.pem
```
Relacione os certificados aos domínios criando o arquivo `./pki/ctrl-list.txt`
```
/usr/local/etc/haproxy/pki/server.pem host1.dominio.com.br
/usr/local/etc/haproxy/pki/server.pem host2.dominio.com.br
/usr/local/etc/haproxy/pki/server.pem host3.dominio.com.br
```
## Configuração
Configure o arquivo "haproxy.cfg" com as entradas dos hosts e demais configurações de balancemento.
Para maiores informações consulte a documentação oficial (https://git.haproxy.org/?p=haproxy-2.3.git;a=tree;f=examples;hb=HEAD)

## Docker
Instale o docker conforme a documentação oficial (https://docs.docker.com/engine/install/debian/).
Inicie o container na raiz do diretório:
````
docker compose up -d
````

# Teste
Acesse a url de estatísticas na porta que foi configurada http://0.0.0.0:9090 com as credencias configuradas no "haproxy.cfg"
Acesse as demais urls configuradas.
