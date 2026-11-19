# Baozi Store - API REST

Trabalho de Desenvolvimento Web Back-End.
API simples para controlar clientes, produtos e pedidos de uma loja de pãozinho chinês (baozi).

**Tecnologias:** Java 17, Spring Boot 3, Spring Data JPA, MySQL, Postman

## Como rodar

1. Ter o Java 17 instalado (e Maven, ou usar o da IDE)
2. Abrir a pasta `baozi-store` no IntelliJ / Eclipse / VS Code
3. Rodar a classe `BaoziStoreApplication`
   - ou pelo terminal: `mvn spring-boot:run`
4. A API sobe em `http://localhost:8080`

O banco padrão é o MySQL(cria um arquivo em `./data`, não precisa instalar nada).
Dá pra ver o banco em `http://localhost:8080/h2-console`
(JDBC URL: `jdbc:h2:file:./data/baozidb`, user: `sa`, senha em branco).

## Endpoints

Valem para `/clientes`, `/produtos` e `/pedidos`:

| Método | URL | O que faz |
|--------|-----|-----------|
| POST | `/entidade` | cria |
| GET | `/entidade` | lista todos |
| GET | `/entidade/{id}` | busca por id |
| PUT | `/entidade/{id}` | atualiza (opcional) |
| DELETE | `/entidade/{id}` | apaga |

## Exemplos de JSON

Cliente:
```json
{ "nome": "SeuNome123456", "clienteDesde": "2026-11-19" }
```

Produto:
```json
{ "nome": "Baozi de Carne", "preco": 4.50, "estoque": true }
```

Pedido (o cliente e o produto precisam existir antes):
```json
{ "clienteId": 1, "produtoId": 1, "quantidade": 5 }
```

## Postman

Tem uma collection pronta no arquivo `Baozi_Store.postman_collection.json`
(Postman > Import). Ordem: criar cliente, criar produto, criar pedido, listar, buscar por id e deletar.
