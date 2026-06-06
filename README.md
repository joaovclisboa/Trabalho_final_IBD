# Trabalho Prático 2 - Introdução a Banco de Dados (UFMG)

**Universidade Federal de Minas Gerais (UFMG)** **Instituto de Ciências Exatas (ICEx) - Departamento de Ciência da Computação (DCC)** **Disciplina:** Introdução a Banco de Dados  

---

## Sobre o Projeto
Este repositório contém os artefatos (projetos conceitual e lógico, scripts SQL e relatório de desempenho) referentes ao Trabalho Prático 2 da disciplina. O objetivo é projetar, implementar e avaliar o desempenho de um banco de dados relacional para um sistema focado no **Mercado Global de Jogos**, englobando estúdios desenvolvedores, catálogo de jogos, vendas regionais e biblioteca de jogadores.

## Modelagem de Dados

O esquema do banco de dados foi derivado de um modelo Entidade-Relacionamento (ER) projetado para capturar as nuances do sistema financeiro e de catálogo da plataforma.

### Entidades
1. **Jogos:** `ID` (PK), `Nome`, `Genero` *(Atributo Multivalorado)*.
2. **País:** `ID` (PK), `Nome`, `PIB`.
3. **Estúdio:** `ID` (PK), `Nome`, `Número de funcionários`.
4. **Funcionário da Empresa:** `CPF` (PK), `Nome`, `Data Nasc.`, `Cargo`, `Salário`.
5. **Cliente:** `ID` (PK), `Nome de Usuário`, `Data criação conta`.

### Relacionamentos
* **Vendas (N:M):** Relaciona `Jogos` e `País`.  
  *Atributos da Relação:* `Preço`, `Unidades vendidas`.
* **Catálogo (N:M):** Relaciona `Cliente` e `Jogos`.  
  *Atributos da Relação:* `Tempo de jogo`.
* **Desenvolveu (1:N):** Relaciona `Estúdio` e `Jogos`.  
  *Atributos da Relação:* `Verba`.
* **Pertence (1:N):** Relaciona `Cliente` e `País`.

---

## Checklist de Requisitos do TP2

Nosso modelo atende a todas as especificações básicas exigidas pelo enunciado:
- [x] Pelo menos 4 tipos de entidade (Temos 5).
- [x] Pelo menos 3 tipos de relacionamento (Temos 4).
- [x] Pelo menos 1 relacionamento com cardinalidade M:N (Temos 2: *Vendas* e *Catálogo*).
- [x] Todas as entidades possuem chave (ID/CPF) e pelo menos dois outros atributos.
- [x] Pelo menos um atributo multivalorado (Atributo `Genero` na entidade *Jogos*).
- [x] Relacionamento M:N com pelo menos um atributo (`Preço` e `Unidades vendidas` em *Vendas*; `Tempo de jogo` em *Catálogo*).

---

## Consultas e Avaliação de Desempenho (Work in Progress)

Para a fase de testes, o banco de dados será populado com um grande volume de dados sintéticos (utilizando ferramentas como Spawner ou scripts customizados) para evitar o *"cold start"* e aferir o tempo médio de execução real. 

Serão implementadas **10 consultas SQL** seguindo a matriz de requisitos abaixo. Cada consulta terá duas variações (ex: com/sem JOIN, subqueries, criação de índices) para comparação de performance.

- [ ] 2 consultas com apenas operações de seleção e projeção.
- [ ] 3 consultas envolvendo a junção (JOIN) de duas relações.
- [ ] 3 consultas envolvendo a junção (JOIN) de três ou mais relações.
- [ ] 2 consultas envolvendo funções de agregação (SUM, AVG, COUNT, etc.) sobre o resultado da junção de pelo menos duas relações.

---

## Ferramentas Utilizadas
* **Projeto Lógico/Conceitual:** MySQL Workbench
* **SGBD:** MySQL
* **Geração de Dados:** [Informar a ferramenta, ex: Spawner / Python Faker]

---

## Cronograma de Entregas
* **29/05:** Constituição do grupo e tema (Realizado).
* **08/06:** Entrega do Diagrama ER via Moodle.
* **24/06:** Entrega do relatório final impresso e postagem do vídeo de apresentação (Wiki do Moodle).
