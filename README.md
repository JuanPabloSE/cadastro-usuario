<h1 align="center">🧍‍♂️ Cadastro de Usuário - CRUD com Spring Boot</h1>

<p align="center">
  <b>Aplicação CRUD completa para cadastro, atualização, busca e exclusão de usuários.</b><br/>
  Desenvolvida em <b>Java 25 + Spring Boot</b>, com persistência em <b>H2 Database</b>.
</p>

---

<p align="center">
  <img src="https://img.shields.io/badge/Java_25-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring_Data_JPA-0078D7?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/H2_Database-003B57?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Lombok-A42E2B?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Maven-C71A36?style=for-the-badge"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Build-Passing-brightgreen?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/Status-Em%20Desenvolvimento-yellow?style=flat-square"/>
</p>

---

## 📖 Sobre o Projeto

O **Cadastro de Usuário** é um sistema **CRUD (Create, Read, Update, Delete)** desenvolvido com **Spring Boot**.  
Seu objetivo é permitir o gerenciamento completo de usuários — incluindo cadastro, busca, atualização e exclusão —  
utilizando um banco **H2 em memória** para persistência dos dados.

O projeto foi estruturado com **arquitetura em camadas**, boas práticas de **injeção de dependência** e **mapeamento JPA**.

---

## 🧩 Estrutura do Projeto

```
src
└── main
├── java
│ └── com.javanauta.cadastro_usuario
│ ├── controller
│ │ └── UsuarioController.java # Endpoints REST
│ ├── business
│ │ └── UsuarioService.java # Regras de negócio
│ └── infrastructure
│ ├── entitys
│ │ └── Usuario.java # Entidade JPA
│ └── repository
│ └── UsuarioRepository.java # Interface de persistência
└── resources
└── application.properties # Configurações da aplicação
```

---

## ⚙️ Funcionalidades Principais

✅ Cadastrar usuário  
✅ Buscar usuário por e-mail  
✅ Atualizar usuário por ID  
✅ Deletar usuário por e-mail  

---

## 🧠 Principais Conceitos Aplicados

- **Arquitetura em camadas (Controller → Service → Repository → Entity)**  
- **Injeção de dependência** com `@RequiredArgsConstructor`  
- **Spring Data JPA** para persistência  
- **Banco de dados H2 (em memória)**  
- **Lombok** para redução de código boilerplate  
- **Tratamento de exceções** básico com `RuntimeException`  

---

## 📡 Endpoints da API

| Método | Endpoint | Parâmetros | Descrição |
|:-------:|:----------|:------------|:------------|
| `POST` | `/usuario` | `@RequestBody Usuario` | Cria um novo usuário |
| `GET` | `/usuario?email={email}` | `@RequestParam email` | Busca um usuário pelo e-mail |
| `PUT` | `/usuario?id={id}` | `@RequestParam id`, `@RequestBody Usuario` | Atualiza os dados de um usuário |
| `DELETE` | `/usuario?email={email}` | `@RequestParam email` | Deleta um usuário pelo e-mail |

---

## 🧩 Modelo da Entidade

```java
@Entity
@Table(name = "usuario")
@Getter
@Setter
@AllArgsConstructor
@NoArgsConstructor
@Builder
public class Usuario {

    @Id
    @GeneratedValue(strategy = GenerationType.AUTO)
    private Integer id;

    @Column(name = "email", unique = true)
    private String email;

    @Column(name = "nome")
    private String nome;
}
```
## 📦 Exemplo de Requisições (Postman)
🔹 Criar Usuário (POST)
```
POST /usuario
{
  "nome": "Juan Pablo",
  "email": "juan@exemplo.com"
}
```

🔹 Atualizar Usuário (PUT)
```
PUT /usuario?id=1
{
  "nome": "Juan Pablo"
}
```
🔹 Buscar Usuário por E-mail (GET)
```
GET /usuario?email=juan@exemplo.com
```

🔹 Deletar Usuário (DELETE)
```
DELETE /usuario?email=juan@exemplo.com
```

## ▶️ Como Executar o Projeto
```
Clone o repositório:
git clone https://github.com/JuanPabloSE/cadastro-usuario.git

Acesse a pasta:

cd cadastro-usuario

Execute com Maven:

mvn spring-boot:run

Acesse o H2 Console:

http://localhost:8081/h2-console

JDBC URL: jdbc:h2:mem:testdb

User: sa

Password: (vazio)
```
## 🧑‍💻 Autor

👨‍💻 Juan Pablo de Santana Ramos

💼 Desenvolvedor Back-End | Java | Spring Boot | APIs REST

🔹 LinkedIn: https://www.linkedin.com/in/juanpablose/

