Desafio DevOps - Docker e GitHub Actions
Objetivo
Executar uma aplicação HTML estática utilizando Docker com Nginx e automatizar sua validação através do GitHub Actions.

Pré-requisitos
Git instalado
Docker Desktop instalado e em execução
Conta no GitHub com GitHub Actions habilitado
Estrutura do projeto
.
├── index.html
├── Dockerfile
├── .dockerignore
├── README.md
└── .github
    └── workflows
        └── ci.yml
Construir a imagem Docker
docker build -t desafio-devops:v1 .
Executar o container
docker run -d \
  --name desafio-web \
  -p 127.0.0.1:8080:80 \
  desafio-devops:v1
Consultar logs
docker logs desafio-web
Ou em tempo real:

docker logs -f desafio-web
Parar o container
docker stop desafio-web
Remover o container
docker rm desafio-web
Endereço da aplicação
A aplicação estará disponível em:

http://127.0.0.1:8080
Validação da aplicação
Verificar HTTP 200:

curl -I http://127.0.0.1:8080
Verificar conteúdo:

curl http://127.0.0.1:8080
Resultado esperado:

<h1>Meu primeiro desafio DevOps</h1>
Workflow GitHub Actions
Gatilhos
O workflow é executado quando:

Há push na branch main
Um Pull Request é aberto para main
Um Pull Request para main é atualizado
Etapas do workflow
Checkout do código
Build da imagem Docker
Inicialização do container
Verificação de HTTP 200
Verificação da mensagem da página
Exibição de logs
Remoção do container
Evidência da execução local
Inserir aqui uma captura de tela da aplicação no navegador ou da execução:

curl http://127.0.0.1:8080
Exemplo:

<h1>Meu primeiro desafio DevOps</h1>
<p>Docker e GitHub Actions funcionando!</p>
Evidências do GitHub Actions
Execução com sucesso
Cole aqui o link da execução:

https://github.com/SEU-USUARIO/desafio-devops-docker-actions/actions/runs/XXXXXXXX
Execução com falha
Cole aqui o link da execução que falhou após a alteração temporária do h1:

https://github.com/SEU-USUARIO/desafio-devops-docker-actions/actions/runs/YYYYYYYY
Execução corrigida
Cole aqui o link da execução bem-sucedida após restaurar a mensagem:

https://github.com/SEU-USUARIO/desafio-devops-docker-actions/actions/runs/ZZZZZZZZ
Repositório
Adicionar o link:

https://github.com/SEU-USUARIO/desafio-devops-docker-actions
Pull Request
Adicionar o link:

https://github.com/SEU-USUARIO/desafio-devops-docker-actions/pull/1
