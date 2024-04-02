
# Exemplo de API Spring Boot

Este projeto é um exemplo simples de uma API construída usando Spring Boot, seguindo os princípios da Clean Architecture para garantir que o design do sistema seja robusto, testável e fácil de manter.

## Clean Architecture

![Clean Architecture](image.png)

A Clean Architecture é organizada em camadas concêntricas, cada uma representando diferentes áreas de responsabilidade:

- **Entities**: No núcleo estão as Entidades, que representam os objetos de domínio e as regras de negócio que são independentes do framework utilizado.
- **Use Cases**: Em torno das Entidades, temos os Casos de Uso (Use Cases), que contêm a lógica de aplicação específica e as regras de negócio.
- **Interface Adapters**: Esta camada contém adaptadores que convertem dados do formato mais conveniente para os casos de uso e entidades, para o formato mais conveniente para algum agente externo como o Banco de Dados (DB) ou a Interface do Usuário (UI).
- **Frameworks & Drivers**: A camada mais externa é composta por frameworks e drivers que incluem a UI, o banco de dados, e qualquer outra ferramenta como servidores web ou frameworks de dispositivos.

As dependências entre essas camadas seguem uma regra de dependência externa, significando que as camadas internas não dependem das camadas externas, mas as externas podem depender das internas.

## Tecnologias Utilizadas

- **Spring Boot**: Framework para facilitar o bootstrapping e desenvolvimento de novas aplicações Spring.
- **Spring Web**: Para construir web APIs RESTful.
- **Spring Data JPA**: Para persistência de dados em SQL stores com Java Persistence API.
- **Lombok**: Para minimizar a quantidade de código boilerplate Java.
- **H2 Database**: Banco de dados SQL em memória para facilitar o desenvolvimento e testes.

## Como Executar

Para executar o projeto, você precisa ter o JDK 11 ou superior instalado em sua máquina.

1. Clone o repositório para a sua máquina local:

```bash
git clone https://github.com/seuusuario/seuprojeto.git
```

2. Entre no diretório do projeto:

```bash
cd seuprojeto
```

3. Execute o projeto com o Maven:

```bash
./mvnw spring-boot:run
```

A aplicação estará disponível em `http://localhost:8080`.

## Endpoints da API

Aqui estão alguns dos endpoints disponíveis:

- `GET /api/entidade`: Lista todas as entidades.
- `POST /api/entidade`: Cria uma nova entidade.
- `GET /api/entidade/{id}`: Busca uma entidade pelo seu ID.
- `PUT /api/entidade/{id}`: Atualiza uma entidade existente pelo seu ID.
- `DELETE /api/entidade/{id}`: Exclui uma entidade pelo seu ID.

Substitua `entidade` pelo nome real da entidade usada em seu projeto.

## Configuração

Este projeto utiliza o H2 Database, que é configurado para iniciar automaticamente com a aplicação. Você pode acessar o console do H2 em `http://localhost:8080/h2-console` e conectar-se ao banco de dados usando a URL JDBC `jdbc:h2:mem:testdb`, com `sa` como username e sem senha.

## Licença

Este projeto é distribuído sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

