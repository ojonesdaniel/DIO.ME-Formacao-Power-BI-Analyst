# 🔗 **JOINS no SQL e Chaves Primária & Estrangeira**

## 📌 **O que é JOIN no SQL?**
O **JOIN** é um comando SQL utilizado para combinar registros de duas ou mais tabelas com base em uma **coluna em comum**. Ele é essencial para consultas que precisam de dados espalhados entre diferentes tabelas.

## 🔍 **Tipos de JOINS**

### 🔹 **INNER JOIN**
Retorna apenas os registros que possuem correspondência em ambas as tabelas.
```sql
SELECT A.Coluna, B.Coluna
FROM TabelaA A
INNER JOIN TabelaB B ON A.ID = B.ID;
```

### 🔹 **LEFT JOIN (ou LEFT OUTER JOIN)**
Retorna todos os registros da **tabela à esquerda** e os correspondentes da tabela à direita. Se não houver correspondência, retorna `NULL` nos campos da tabela direita.
```sql
SELECT A.Coluna, B.Coluna
FROM TabelaA A
LEFT JOIN TabelaB B ON A.ID = B.ID;
```

### 🔹 **RIGHT JOIN (ou RIGHT OUTER JOIN)**
Retorna todos os registros da **tabela à direita** e os correspondentes da tabela à esquerda. Se não houver correspondência, retorna `NULL` nos campos da tabela esquerda.
```sql
SELECT A.Coluna, B.Coluna
FROM TabelaA A
RIGHT JOIN TabelaB B ON A.ID = B.ID;
```

### 🔹 **FULL JOIN (ou FULL OUTER JOIN)**
Retorna **todos os registros** de ambas as tabelas. Se não houver correspondência, retorna `NULL` nos campos sem correspondência.
```sql
SELECT A.Coluna, B.Coluna
FROM TabelaA A
FULL JOIN TabelaB B ON A.ID = B.ID;
```

### 🔹 **CROSS JOIN**
Faz o **produto cartesiano** das tabelas, combinando todos os registros de uma com todos da outra.
```sql
SELECT A.Coluna, B.Coluna
FROM TabelaA A
CROSS JOIN TabelaB B;
```

---

## 🔑 **Chave Primária e Chave Estrangeira**

### **Chave Primária (Primary Key - PK)**
É um campo (ou conjunto de campos) que **identifica de forma única** cada registro em uma tabela.

✅ **Características:**
- Valores únicos
- Não pode ser `NULL`
- Cada tabela pode ter apenas **uma chave primária**

📌 **Exemplo:**
```sql
CREATE TABLE Clientes (
    ClienteID INT PRIMARY KEY,
    Nome VARCHAR(100)
);
```

### **Chave Estrangeira (Foreign Key - FK)**
É um campo em uma tabela que **faz referência** à chave primária de outra tabela, criando um relacionamento entre elas.

✅ **Características:**
- Garante a integridade referencial
- Permite conexões entre tabelas
- Pode conter valores repetidos ou `NULL` (dependendo da configuração)

📌 **Exemplo:**
```sql
CREATE TABLE Pedidos (
    PedidoID INT PRIMARY KEY,
    ClienteID INT,
    DataPedido DATE,
    FOREIGN KEY (ClienteID) REFERENCES Clientes(ClienteID)
);
```

Neste exemplo:
- `ClienteID` na tabela **Clientes** é a **chave primária**
- `ClienteID` na tabela **Pedidos** é uma **chave estrangeira**, conectando ambas as tabelas

---

Esses conceitos são fundamentais para trabalhar com bancos de dados relacionais e realizar consultas eficientes com SQL. 🚀

