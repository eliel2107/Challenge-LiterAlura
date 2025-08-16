Markdown

# LiterAlura Challenge 📚

![Java](https://img.shields.io/badge/Java-17-blue?style=for-the-badge&logo=java)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.3.1-green?style=for-the-badge&logo=spring-boot)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue?style=for-the-badge&logo=postgresql)
![Maven](https://img.shields.io/badge/Maven-4.0.0-red?style=for-the-badge&logo=apache-maven)

**Status do Projeto:** Finalizado ✔️

## 📖 Descrição

O **LiterAlura** é uma aplicação de catálogo de livros interativa via console, desenvolvida como parte do Challenge de Java da Alura. A aplicação consome a API pública [Gutendex](https://gutendex.com/) para buscar e registrar livros e seus autores, armazenando os dados em um banco de dados PostgreSQL.

O objetivo é permitir que o usuário interaja com um vasto acervo de livros, realizando buscas, listando informações e consultando dados específicos, como autores vivos em um determinado ano ou livros por idioma.

---

## ✨ Funcionalidades

O menu interativo da aplicação oferece as seguintes opções:

1.  **Buscar Livro por Título:** Pesquisa por um livro na API Gutendex e o salva no banco de dados local.
2.  **Listar Livros Registrados:** Exibe todos os livros que foram salvos no banco de dados.
3.  **Listar Autores Registrados:** Exibe todos os autores que foram salvos no banco de dados.
4.  **Listar Autores Vivos em um Determinado Ano:** Permite ao usuário inserir um ano e exibe os autores que estavam vivos naquele período.
5.  **Listar Livros em um Determinado Idioma:** Exibe uma lista de livros disponíveis em um idioma específico (ex: `es` para espanhol, `en` para inglês).

---

## 🛠️ Tecnologias Utilizadas

Este projeto foi construído utilizando as seguintes tecnologias e bibliotecas:

* **Java 17:** Versão da linguagem Java utilizada.
* **Spring Boot:** Framework principal para a criação da aplicação stand-alone.
* **Spring Data JPA:** Para persistência de dados e comunicação com o banco de dados de forma simplificada.
* **PostgreSQL:** Sistema de gerenciamento de banco de dados relacional para armazenamento dos dados.
* **Maven:** Gerenciador de dependências e build do projeto.
* **Jackson:** Biblioteca para conversão de dados JSON (da API) para objetos Java.

---

## 🚀 Como Executar o Projeto

Siga os passos abaixo para configurar e executar o projeto em seu ambiente local.

### Pré-requisitos

* **JDK 17** ou superior instalado.
* **Maven** instalado e configurado.
* Um servidor **PostgreSQL** ativo.

### 1. Clone o Repositório

```bash
git clone [https://github.com/eliel2107/Challenge-LiterAlura.git](https://github.com/eliel2107/Challenge-LiterAlura.git)
cd Challenge-LiterAlura
2. Configure o Banco de Dados
Crie um banco de dados no PostgreSQL com o nome literalura.

Abra o arquivo src/main/resources/application.properties.

Altere as propriedades spring.datasource.username e spring.datasource.password com suas credenciais de acesso ao PostgreSQL.

Properties

spring.datasource.url=jdbc:postgresql://localhost:5432/literalura
spring.datasource.username=SEU_USUARIO_AQUI
spring.datasource.password=SUA_SENHA_AQUI
spring.jpa.hibernate.ddl-auto=update
3. Compile e Execute
Você pode executar a aplicação diretamente pela sua IDE (como IntelliJ ou Eclipse) ou utilizando o Maven no terminal.

Bash

# Para compilar e empacotar o projeto
mvn clean package

# Para executar o arquivo .jar gerado
java -jar target/Challenge-LiterAlura-0.0.1-SNAPSHOT.jar
Após a execução, o menu interativo será exibido no console e você poderá começar a usar a aplicação.

🕹️ Como Usar
Ao iniciar a aplicação, um menu será exibido no console com as opções disponíveis.
Basta digitar o número da opção desejada e pressionar Enter para interagir com o catálogo de livros.

*************************************************
Escolha um número no menu:
1- Buscar livro por título
2- Listar livros registrados
3- Listar autores registrados
4- Listar autores vivos em um determinado ano
5- Listar livros em um determinado idioma
0- Sair
*************************************************
👨‍💻 Autor
Desenvolvido por Eliel
