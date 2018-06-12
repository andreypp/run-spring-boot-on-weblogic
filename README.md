# run-spring-boot-on-weblogic
Passos para executar uma aplicação Spring Boot no Oracle Weblogic

## Criando um servidor com o WebLogic

É importante fazer os downloads dos pré-requisitos necessários antes de iniciar a construção das imagens 

- Server JRE: http://www.oracle.com/technetwork/java/javase/downloads/server-jre8-downloads-2133154.html
- Fusion Middleware Infrastructure: http://www.oracle.com/technetwork/middleware/weblogic/downloads/wls-for-dev-1703574.html
- Generic Installer: http://www.oracle.com/technetwork/middleware/weblogic/downloads/wls-for-dev-1703574.html
- Quick Installer:http://www.oracle.com/technetwork/middleware/weblogic/downloads/wls-for-dev-1703574.html
- Supplemental Installer: http://www.oracle.com/technetwork/middleware/weblogic/downloads/wls-for-dev-1703574.html

Clonar o repositorio da Oracle onde existem imagens para o WebLogic (Dockerfiles). Os arquivos que foram feito download acima serão usados durante a build das imagens
`git clone https://github.com/oracle/docker-images.git`

Na pasta `OracleWebLogic`, arquivo `README`, existe o passo a passo de como construir as imagens necessárias (3)

1. Imagem com o Java Server JRE
2. Imagem com a "base" do WebLogic
3. Alguma das imagens da pasta `samples`

No mesmo arquivo `README` existem as instruções de como fazer o `docker run` de cada imagem

## Configurando a aplicação para o WebLogic

No link abaixo está o passo a passo de como adaptar sua aplicação com Spring Boot para rodar no WebLogic.
https://docs.spring.io/spring-boot/docs/current/reference/html/howto-traditional-deployment.html

Resumidamente, é necessário: 
- Alterar a classe principal da aplicação
- Alterar o pom.xml para gerar o war ao invés de jar
- Criar o arquivo weblogic.xml dentro da pasta WEB-INF
