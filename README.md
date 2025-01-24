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
    ├── dhparam.pem
    └── server.pem
````
## Keystore
Mescle as chaves pública e privada em um único arquivo:
```
cat fulchain.pem privkey.pem > ../haproxy/pky/server.pem
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
Acesse a url de estatísticas na porta que fou configurada http://0.0.0.0:9090 com as credencias configuradas no "haproxy.cfg"
