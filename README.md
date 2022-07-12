# kubernetes-news

# Tópicos

* [Descrição do Projeto](#descrição-do-projeto)
* [Tecnologias utilizadas](#tecnologias-utilizadas)
* [Demonstração da Aplicação](#passo-a-passo-da-aplicação)

# Descrição do Projeto
 Utilização do kubernetes na máquina local com resiliência e escalabilidade para aplicação de uma página web de notícias
 
# Tecnologias utilizadas
**Docker**

**kubectl**

**K3D**

**PostgreSQL**

# Passo-a-passo da aplicação

## Passo 1
Fazer o Fork do repositório: **https://github.com/KubeDev/kube-news**

## Passo 2 
Criação da imagem docker e seu Dockerfile e por seguinte, fazer o push para o docker hub
## Passo 3 
Instalar o kubectl, ferramenta para interagir com o nosso cluster kubernetes:

```https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl```
## Passo 4 
Instalar o K3D para montar o cluster K3S

``` $ curl -s https://raw.githubusercontent.com/rancher/k3d/main/install.sh | bash ```

## Passo 5 
Criar o cluster kubernetes com a porta de escolha, nesse caso foi a 30000  para ter acesso na Web, utilizou-se o seguinte comando:

``` kd3 cluster create meucluster --server --agents -p 30000:30000@loadbalancer   ```

## Passo 6 
Criando o manifesto do kubernetes-new com **Deployment**, responsável por realizar o controle de versão da aplicação, gerando versões do **Replicaset** e por sua vez, o ReplicaSet fica responsável por gerenciar a quantidade de pods e por último o **Pod** é o responsável por sua aplicação rodar. Para rodar a aplicação, digita-se o comando:

``` kubectl apply -f deployment.yaml   ```

## Passo 7
Testando a aplicação na web

*localhost:30000*

O PostgreSQL é o banco de dados responsável por armanzenar os dados advindos da página web

