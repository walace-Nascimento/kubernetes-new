# kube-news

# Tópicos

* [Descrição do Projeto](#descrição-do-projeto)
* [Tecnologias utilizadas](#tecnologias-utilizadas)
* [Demonstração da Aplicação](#passo-a-passo-da-aplicação)

# Descrição do Projeto
 Criação de uma aplicação utilizando kubernetes na máquina local
 
# Tecnologias utilizadas
**Docker**

**kubectl**

**K3D**

# Passo-a-passo da aplicação

## Passo 1
Fazer o Fork do repositório: **https://github.com/KubeDev/kube-news**

## Passo 2 
Criação da imagem docker e push para o docker hub
## Passo 3 
Instalar o kubectl, ferramenta para interagir com o nosso cluster kubernetes:

```https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl```
## Passo 4 
Instalar o K3D para montar o cluster K3S

``` $ curl -s https://raw.githubusercontent.com/rancher/k3d/main/install.sh | bash ```

## Passo 5 
Criar o cluster kubernetes com a porta de escolha para ter acesso na Web, utiliz-se o seguinte comando:

``` kd3 cluster create meucluster --server --agents -p 3000:3000@loadbalancer   ```

## Passo 6 
Criando o manifesto do kubernetes-new com **Deployment**, responsável por realizar o controle de versão da aplicação, gerando versões do **Replicaset** e por sua vez, o ReplicaSet fica responsável por gerenciar a quantidade de pods e por último o **Pod** é o responsável por sua aplicação rodar.

``` kubectl apply -f deployment.yaml   ```

## Passo 7
Testando a aplicação na web

*localhost:3000*

