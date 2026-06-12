# Workshop W6 — Maven e Gradle

Este repositório é o modelo da atividade prática do Workshop W6 da disciplina TMS. A turma será dividida em dois times: um usando Maven e outro usando Gradle. O objetivo é clonar o projeto, rodar o build inicial, adicionar a dependência `org.json` e executar o `.jar` gerado.

## Pré-requisitos

Antes da aula, confira se tudo está instalado rodando estes comandos no terminal:

```bash
java -version
mvn -version
gradle -version
git --version
```

O Java precisa estar na versão 17.

## Etapa 1 — Clonar e rodar o build inicial

```bash
git clone https://github.com/<usuario>/workshop-maven-gradle.git
```

### Time Maven

```bash
cd workshop-maven-gradle/projeto-maven
mvn package
```

### Time Gradle

```bash
cd workshop-maven-gradle/projeto-gradle
gradle build
```

Se o build terminar sem erro, a etapa 1 foi concluída.

## Etapa 2 — Adicionar a dependência `org.json` e descomentar o código

### Maven

No arquivo `projeto-maven/pom.xml`, coloque o trecho abaixo dentro de `<dependencies>`:

```xml
<dependency>
  <groupId>org.json</groupId>
  <artifactId>json</artifactId>
  <version>20240303</version>
</dependency>
```

Depois rode novamente:

```bash
mvn package
```

### Gradle

No arquivo `projeto-gradle/build.gradle`, coloque o trecho abaixo dentro de `dependencies { }`:

```groovy
implementation 'org.json:json:20240303'
```

Depois rode novamente:

```bash
gradle build
```

### Descomentar o código

Nos dois projetos, abra o arquivo:

```text
src/main/java/br/ufu/tms/App.java
```

Descomente:

```java
// import org.json.JSONObject;
```

E também descomente o bloco que cria e imprime o JSON.

## Etapa 3 — Executar o `.jar`

### Time Maven

```bash
java -jar target/workshop-demo-1.0.jar
```

### Time Gradle

```bash
java -jar build/libs/workshop-demo-1.0.jar
```

A saída esperada é o banner do workshop e um JSON impresso na tela.

## Entrega de participação

Enviar:

- print do build executado com sucesso;
- link do seu repositório com a dependência adicionada.
