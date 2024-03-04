
# Relatório: usando SonarQube com Docker e .NET Core

## Introdução

Esse relatório detalha a utilização do SonarQube, Docker e .NET Core para aprimorar a qualidade e a segurança do código. São abordados os conceitos chave, os benefícios e as etapas práticas para implementar essa solução.

## Tecnologias abordadas
- **SonarQube**: ferramenta de análise de código que identifica bugs, vulnerabilidades, odores de código e duplicações.
- **Docker**:  plataforma de conteinerização que simplifica a execução de aplicações em ambientes isolados.
- **.NET Core**: estrutura de código aberto para construção de aplicações web modernas, APIs e microsserviços.


## Conceitos aprendidos
### 1. Configurando o SonarQube:
- Instalar o Java e o Docker.
- Executar o SonarQube em um contêiner Docker.

### 2. Preparando o ambiente de desenvolvimento:
- Instalar o SonarScanner para .NET Core.
- Configurar o SonarScanner com detalhes do projeto.

### 3. Análise de código:
- Usar o SonarScanner para analisar o código-fonte.
- Visualizar os resultados da análise no SonarQube.

### 4. Configuração adicional:
- Personalizar o escopo da análise (por exemplo, excluir arquivos/diretórios específicos).

## Benefícios da abordagem
- **Qualidade de código aprimorada**: é possível identificar e corrigir bugs, vulnerabilidades e padrões de código (conceitos de Clean Code) antes que impactem a produção.
- **Segurança robusta**: o SonarQube ajuda a detectar potenciais vulnerabilidades de segurança no código.
- **Colaboração em equipe**: fornece uma plataforma centralizada para análise e revisão de código, promovendo a colaboração entre desenvolvedores.
- **Quality Gate**: permite definir padrões de qualidade aceitáveis, e a análise gráfica do código fornece insights visuais sobre o progresso da codificação.



## Capturas de tela: 

### Executando o código
![image](assets\1.png)
<br>

![image](assets\2.png)
<br>

![image](assets\3.png)
<br>

![image](assets\4.png)
<br>

### Acessando o dashboard
![image](assets\5.png)
<br>

### Overview do sistema, onde há 2 open issues em Reliability e 4 em Maintainability.
![image](assets\6.png)
<br>

### Visualizando os bugs em Reliability
![image](assets\7.png)
<br>








<br>
<br>
<br>











# Instruções

# Analyze Your Code Using SonarQube, Docker and .NET Core

This app is an example app for learning how to use SonarQube on your projects. For more details please read [Analyze Your Code Using SonarQube, Docker and .NET Core](link_to_replace) to see a detailed instruction on how to do that.

**Prerequisites:**

- [Java 11](https://adoptopenjdk.net/)+
- [Docker](https://docs.docker.com/get-docker/)
- [.NET Core](https://dotnet.microsoft.com/download)
- [SonarScanner for .NET Core](https://github.com/SonarSource/sonar-scanner-msbuild/releases/download/4.7.1.2311/sonar-scanner-msbuild-4.7.1.2311-netcoreapp2.0.zip)

**Table of Contents**

- [Getting Started](#getting-started)
- [Help](#help)
- [License](#license)

## Getting Started

Begin with running SonarQube on Docker:
```sh
docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube
```

**NOTE:** You'll be able to login with `admin/admin`. After first login, you will be promted to change the default credentials.

In order to run SonarScanner, run the following commands:

```sh
dotnet sonarscanner begin /k:"project-key" /d:sonar.login=admin /d:sonar.password=admin
dotnet build <path_to_solution.sln>
dotnet sonarscanner end /d:sonar.login=admin /d:sonar.password=admin
```

> **NOTE:** Remember to replace "path_to_solution" and "password" with correct ones for your example.

## Help

Please post any questions as comments on the [blog post](link_to_replace), or visit our [Okta Developer Forums](https://devforum.okta.com/). You can also ask them on [Stack Overflow with the `sonarqube` tag](https://stackoverflow.com/tags/sonarqube).

## License

Apache 2.0, see [LICENSE](LICENSE).
