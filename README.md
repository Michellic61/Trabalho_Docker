### Implementação de Estrutura com Docker Compose



## Objetivo Principal: 

Desenvolver uma infraestrutura utilizando Docker Compose para o jogo de adivinhação. Esta infraestrutura deve contemplar os seguintes serviços:

- Um container para o backend em Python (Flask).
- Um container para o banco de dados Postgres.
- Um container NGINX que funcione como proxy reverso e sirva as páginas do frontend React.



## Pré-requisitos:

Para rodar este projeto, certifique-se de ter os seguintes itens instalados:

- **Docker Compose**: Instalação do Docker Compose(https://docs.docker.com/compose/install/)

- **Git**: Instalação do Git (https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)


## Gitbash/VisualCode: 

**Clonar para o seu ambiente**: git clone git@github.com:Michellic61/Trabalho_Docker.git

**Acessar a pasta**: cd Trabalho_Docker/Trabalho_Docker/

**Em seguida, executar**: docker-compose up --build

**Acessar a Aplicação**: http://localhost:80

![Aplicação](image.png)



## Estrutura do Repositório:

- Arquivo Docker Compose: docker-compose.yml
- Dockerfile do Backend (Python): Dockerfile
- Dockerfile do Frontend (React): frontend/Dockerfile
- Configuração do NGINX: nginx.conf


## Nota Técnica:
O parâmetro `restart: always` foi adicionado a todos os serviços no arquivo `docker-compose.yml`.

Essa configuração garante que, em caso de falhas, o Docker reiniciará automaticamente os contêineres, aumentando a robustez da aplicação.


## Estrutura do Ambiente: 

1. **Arquivo docker-compose.yml**

É um arquivo que descreve como os contêineres Docker devem ser configurados e executados. Ele inclui informações sobre os serviços que compõem a aplicação, as imagens Docker a serem usadas ou construídas, as redes que conectam os contêineres, os volumes para armazenamento de dados persistentes, as variáveis de ambiente necessárias para cada serviço e outras configurações importantes, como mapeamento de portas e dependências entre serviços.

![Imagem1](image-1.png)


**Definição do Dockerfiles** 

Dockerfiles são entradas cruciais para compilações de imagens e podem facilitar compilações de imagens automatizadas e multicamadas com base em suas configurações exclusivas. Dockerfiles podem começar simples e crescer com suas necessidades para dar suporte a cenários mais complexos. Fonte: https://docs.docker.com/build/concepts/dockerfile/

2. **Dockerfile do Backend**

Este Dockerfile configura um ambiente de contêiner para executar uma aplicação Flask, garantindo que todas as dependências sejam instaladas e que o servidor Flask seja iniciado corretamente.

![Imagem2](image-2.png)

3. **Dockerfile do Frontend**

Este Dockerfile configura um ambiente de contêiner para construir uma aplicação React e servir os arquivos estáticos resultantes usando Nginx, garantindo que a aplicação seja construída e servida de maneira eficiente e consistente.

![Imagem3](image-3.png)

4. **Configuração do NGINX**

Este arquivo de configuração do NGINX define um servidor que entrega arquivos estáticos do frontend e encaminha as requisições da API para o backend. Isso assegura uma separação distinta entre o frontend e o backend, otimizando a eficiência e a estrutura da aplicação.

![Imagem4](image-4.png)


## Facilidade de Atualização:

Esses comandos explicam como atualizar diferentes componentes de uma aplicação Docker Compose, incluindo o backend em Python, o frontend e o balanceador de carga NGINX. Para aplicar as mudanças, use docker-compose down seguido de docker-compose up.

- docker-compose down: Desliga e remove todos os recursos associados ao seu ambiente Docker Compose, incluindo contêineres, redes e volumes.

- docker-compose up: Cria e inicia todos os serviços definidos no seu arquivo Docker Compose, configurando um ambiente de contêineres pronto para uso.


## Considerações Importantes:

Todas as diretrizes para a concepção e implementação inicial foram fornecidas pelo criador do repositório Guess Game. Esta documentação foi desenvolvida com base no **Trabalho Prático Unidade 1 Docker**.



