# LiterAlura Challenge 📚

![Java](https://img.shields.io/badge/Java-17-blue?style=for-the-badge&logo=java)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.3.1-green?style=for-the-badge&logo=spring-boot)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue?style=for-the-badge&logo=postgresql)
![Maven](https://img.shields.io/badge/Maven-4.0.0-red?style=for-the-badge&logo=apache-maven)
![License](https://img.shields.io/badge/license-MIT-blue.svg?style=for-the-badge)
![Contributions](https://img.shields.io/badge/contributions-welcome-brightgreen?style=for-the-badge)

**Status do Projeto:** Finalizado ✔️

---

## 📑 Tabela de Conteúdos
- [📖 Descrição](#-descrição)
- [✨ Funcionalidades](#-funcionalidades)
- [🛠️ Tecnologias Utilizadas](#️-tecnologias-utilizadas)
- [🏛️ Estrutura do Projeto](#️-estrutura-do-projeto)
- [📄 Modelo de Dados](#-modelo-de-dados)
- [🚀 Como Executar o Projeto](#-como-executar-o-projeto)
- [🕹️ Exemplos de Uso](#️-exemplos-de-uso)
- [📌 Próximos Passos](#-próximos-passos)
- [🤝 Contribuindo](#-contribuindo)
- [📜 Licença](#-licença)
- [👨‍💻 Autor](#-autor)

---

## 📖 Descrição

O **LiterAlura** é uma aplicação de catálogo de livros interativa via console, desenvolvida como parte do Challenge de Java da Alura.  
A aplicação consome a API pública [Gutendex](https://gutendex.com/) para buscar e registrar livros e autores, armazenando os dados de forma persistente em um banco de dados PostgreSQL.

O objetivo principal é oferecer ao usuário uma forma simples de interagir com um vasto acervo de livros, permitindo realizar buscas, listar informações e consultar dados específicos, como autores vivos em um determinado ano ou livros por idioma.

---

## ✨ Funcionalidades

O menu interativo da aplicação oferece as seguintes opções:

1. **Buscar Livro por Título** → Pesquisa por um livro na API Gutendex e o salva no banco de dados local.  
2. **Listar Livros Registrados** → Exibe todos os livros que foram salvos no banco de dados.  
3. **Listar Autores Registrados** → Exibe todos os autores que foram salvos no banco de dados.  
4. **Listar Autores Vivos em um Determinado Ano** → Permite inserir um ano e exibe os autores vivos nesse período.  
5. **Listar Livros em um Determinado Idioma** → Exibe uma lista de livros disponíveis em um idioma específico (ex: `es` para espanhol, `en` para inglês).  
6. **Sair** → Encerra a aplicação.  

---

## 🛠️ Tecnologias Utilizadas

- **Java 17**
- **Spring Boot**
- **Spring Data JPA**
- **PostgreSQL**
- **Maven**
- **Jackson**

---

## 🏛️ Estrutura do Projeto

```bash
/src/main/java/com/example/literalura
├── model/
│   ├── Autor.java
│   └── Livro.java
├── repository/
│   ├── AutorRepository.java
│   └── LivroRepository.java
├── service/
│   ├── ConsumoAPIService.java
│   └── ConverteDadosService.java
├── controller/ (ou principal)
│   └── Principal.java
└── LiteraluraApplication.java
```

- **`model`** → Entidades JPA (`Livro` e `Autor`).  
- **`repository`** → Interfaces `JpaRepository` para operações CRUD.  
- **`service`** → Lógica de negócio (consumo da API e conversão dos dados JSON).  
- **`principal`** → Menu interativo e lógica de interação com o usuário.  
- **`LiteraluraApplication.java`** → Ponto de entrada da aplicação Spring Boot.  

---

## 📄 Modelo de Dados

### Entidades:

**Autor**
- `id` (PK)  
- `nome`  
- `anoNascimento`  
- `anoFalecimento`  

**Livro**
- `id` (PK)  
- `titulo`  
- `idioma`  
- `numeroDownloads`  
- `autor_id` (FK para Autor)  

Relacionamento: **Um-para-Muitos** → Um autor pode ter vários livros.  

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
- **JDK 17** ou superior  
- **Maven** instalado  
- **PostgreSQL** ativo  

### 1️⃣ Clone o Repositório
```bash
git clone https://github.com/eliel2107/Challenge-LiterAlura.git
cd Challenge-LiterAlura
```

### 2️⃣ Configure o Banco de Dados
- Crie o banco `literalura` no PostgreSQL.  
- Abra o arquivo `src/main/resources/application.properties` e edite:  

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/literalura
spring.datasource.username=SEU_USUARIO_AQUI
spring.datasource.password=SUA_SENHA_AQUI
spring.jpa.hibernate.ddl-auto=update
```

### 3️⃣ Compile e Execute
```bash
# Compilar e empacotar
mvn clean package

# Executar
java -jar target/Challenge-LiterAlura-0.0.1-SNAPSHOT.jar
```

Após a execução, o menu interativo será exibido no console.  

---

## 🕹️ Exemplos de Uso

### Menu Principal:
```
*************************************************
Escolha um número no menu:
1- Buscar livro por título
2- Listar livros registrados
3- Listar autores registrados
4- Listar autores vivos em um determinado ano
5- Listar livros em um determinado idioma
0- Sair
*************************************************
```

### Buscar Livro:
```
Digite o nome do livro que deseja buscar:
> O morro dos ventos uivantes

----- LIVRO -----
Título: O Morro dos Ventos Uivantes
Autor: Brontë, Emily
Idioma: pt
Número de downloads: 1234
-----------------
```

### Autores Vivos em um Ano:
```
Digite o ano que deseja pesquisar:
> 1850

Autores vivos no ano de 1850:
- Brontë, Emily (1818 - 1848)
- Shakespeare, William (1564 - 1616)
```

---

## 📌 Próximos Passos
- [ ] Implementar testes unitários  
- [ ] Criar interface gráfica em JavaFX  
- [ ] Disponibilizar versão Docker  
- [ ] Adicionar suporte a mais APIs de livros  

---

## 🤝 Contribuindo
Quer contribuir? Confira o guia em [CONTRIBUTING.md](CONTRIBUTING.md).  

---

## 📜 Licença
Este projeto está sob a licença **MIT**.  
Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.  

---

## 👨‍💻 Autor
Desenvolvido por **Eliel Mesquita Cunha** no Challenge Java da Alura. 🚀
