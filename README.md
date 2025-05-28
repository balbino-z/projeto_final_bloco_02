Projeto Farmácia - Backend com Spring Boot
1. Descrição do Projeto
O Projeto Farmácia é uma API RESTful desenvolvida com Spring Boot, projetada para simular o backend de um sistema de comércio eletrônico de uma farmácia. Esta aplicação foca no gerenciamento eficiente de categorias de produtos e produtos, incluindo funcionalidades essenciais como controle de estoque, precificação e classificação de medicamentos por categorias.

2. Sobre a API
Esta API foi construída utilizando Java e Spring Boot, seguindo os princípios da arquitetura REST e as melhores práticas de organização de código. Ela oferece um conjunto robusto de endpoints para a manipulação dos recursos Categoria e Produto, permitindo operações CRUD (Create, Read, Update, Delete) completas e a associação entre produtos e suas respectivas categorias.

2.1. Principais Funcionalidades:
Cadastro, busca, edição e exclusão de produtos.

Cadastro, busca, edição e exclusão de categorias.

Associação de produtos a categorias.

Controle de estoque e preços de produtos.

Documentação automática da API com Swagger (SpringDoc).

3. Diagrama de Classes
classDiagram
class Categoria {
  - id : Long
  - nome : String
  - descricao : String
  - produtos : List~Produto~
}

class Produto {
  - id : Long
  - nome : String
  - descricao : String
  - preco : BigDecimal
  - quantidade : int
  - categoria : Categoria
}

Categoria "1" --> "0..*" Produto : possui

4. Diagrama Entidade-Relacionamento (DER)
erDiagram
    tb_categoria ||--o{ tb_produto : possui
    tb_categoria {
        bigint id PK
        varchar nome
        varchar descricao
    }
    tb_produto {
        bigint id PK
        varchar nome
        varchar descricao
        decimal preco
        int quantidade
        bigint categoria_id FK
    }

5. Tecnologias Utilizadas
Item

Descrição

Servidor

Tomcat

Linguagem

Java 17

Framework

Spring Boot

ORM

JPA + Hibernate

Banco de Dados

MySQL

Documentação API

Swagger (SpringDoc)

6. Requisitos
Para executar o projeto localmente, você precisará ter instalado:

Java JDK 17+

Banco de dados MySQL

Spring Tool Suite (STS) - ou outra IDE compatível com Spring Boot

Maven

Insomnia ou Postman (para testar os endpoints da API)

7. Como Executar o Projeto no STS
7.1. Importando o Projeto
Clone o repositório do Projeto Farmácia:

git clone https://github.com/balbino-z/farmacia.git

Abra o Spring Tool Suite (STS) e selecione a pasta do Workspace.

No menu superior do STS, clique em: File ➜ Import...

Na janela Import, selecione: Maven ➜ Existing Maven Projects e clique em Next.

No campo Root Directory, clique em Browse... e selecione a pasta do projeto clonado.

Marque o projeto e clique em Finish.

7.2. Configurando o Banco de Dados
Crie um banco de dados MySQL com o nome db_farmacia.

Atualize as credenciais de acesso ao banco de dados no arquivo src/main/resources/application.properties:

spring.datasource.url=jdbc:mysql://localhost:3306/db_farmacia
spring.datasource.username=root
spring.datasource.password=root

7.3. Executando o Projeto
Clique com o botão direito no projeto no STS.

Selecione Run As ➜ Spring Boot App.

Acompanhe a inicialização da aplicação no console.

Após a inicialização, acesse a documentação interativa do Swagger em seu navegador:

http://localhost:8080/swagger-ui/index.html

8. Contribuição
Este projeto foi desenvolvido para fins educacionais e é um convite à colaboração. Contribuições são muito bem-vindas! Se você tiver sugestões, melhorias ou encontrar algum problema, por favor:

Crie uma issue.

Envie um pull request.

Compartilhe com outros desenvolvedores!

9. Autor
Desenvolvido por Vinícius Balbino
