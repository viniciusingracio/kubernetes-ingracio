# Documentação sobre o repo e outras coisinhas
---

## Configurar o kubectl para usar o GKE

[Instalar e configurar kubectl com GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl?hl=pt-br#install_plugin)

Com acesso ao cluster no GCP, usando o Google Cloud Shell, usei o seguinte comando para pegar o config do kubernetes no ```.kube```

```bash
$ kubectl config view
```
Copiei o config e criei no meu ```.kube``` local com o nome ```cluster-dev```, nome do meu cluster no GKE.

Eu particularmente, uso os seguintes comandos para fazer a conexão do meu ```kubectl``` com o contexto que eu quero:

```bash
$ export KUBECONFIG=$KUBECONFIG:$HOME/.kube/cluster-dev
$ kubectl config use-context CONTEXT_NAME
```
Aqui começaram meus problemas. Para fazer essa conexão, você precisa usar o passo a passo do link citado acima.

Primeiramente instale o plugin e depois use os comandos de autenticação para logar na conta do GCP.
Uma coisa importante: Quando ele abre o navegador para fazer essa autenticação, não funcionou simplesmente clicando na conta que eu uso, mas tive que clicar em conetar nova conta e criar uma senha.
