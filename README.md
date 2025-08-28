# _🐝Exercícios SQL-BEECROWD_ #

<img width="959" height="311" alt="Image" src="https://github.com/user-attachments/assets/86492f1c-de02-4d91-b134-7e1d694110a0" />

---
## Atividades nível 1 ##
- 2607 - Cidades em Ordem Alfabética
    
   <img width="471" height="243" alt="Image" src="https://github.com/user-attachments/assets/08076d56-3184-4039-84fb-96243b4c417c" />
    
    ```sql
    select city
    from providers
    order by city asc;
    ```

Em todos os meses a empresa pede um relatório das cidades que os fornecedores estão cadastrados. 

Para isso teremos que fazer uma consulta no Banco de Dados que retorne todas as cidades dos fornecedores, mas em ordem alfabética.

### _OBS: Não podendo mostrar cidades repetidas._ ###

---

- 2603 - Endereço dos Clientes
    
    <img width="411" height="218" alt="Image" src="https://github.com/user-attachments/assets/2d5a6439-51b2-4d46-90f0-fc537a619c41" />
    
    ```sql
    select 
        name,
        street
    from 
        customers
    where
        city like '%Porto Alegre%';
    ```

Uma empresa fará um evento comemorando os 20 anos de mercado, e para isso fará uma grande comemoração na cidade de Porto Alegre. Onde Querem também convidar todos os seus clientes que estão cadastrados nessa cidade.

Então precisamos passar os nomes e os endereços dos clientes que moram em 'Porto Alegre'.

---

- 2608 - Maior e Menor Preço
    
    <img width="417" height="275" alt="Image" src="https://github.com/user-attachments/assets/6149b9af-c3b2-4c28-9ecc-23c1f95297b5" />
    
    ```sql
    select 
        max(price),
        min(price)
    from
        products;
    ```

O setor financeiro de uma empresa, está querendo saber os menores e maiores valores dos produtos, que vendem.

Para isso, precisamos exibir somente o maior e o menor preço da tabela produtos.

---

- 2615 - Expandindo o Negocio
    
    <img width="408" height="241" alt="Image" src="https://github.com/user-attachments/assets/83d543ec-d062-4dba-9853-ec86347a2933" />
    
    ```sql
    select 
        city
    from customers;
    ```

A locadora tem objetivos de criar várias franquias espalhadas pelo Brasil. Para isso querem saber em quais cidades os clientes moram.

Para isso precisamos selecionar o nome de todas as cidades onde a locadora tem clientes. 

## _OBS: Não repetindo o nome da cidade._ ##

---

- 2617 - Fornecedor Ajax SA
    
    <img width="578" height="320" alt="Image" src="https://github.com/user-attachments/assets/81af718c-c751-429b-86ef-fdaea661f23f" />
    
    ```sql
    select products.name, providers.name
    from providers
    inner join products
        on products.id_providers = providers.id
    where providers.name = 'Ajax SA';
    ```

O setor financeiro encontrou alguns problemas na entrega de um dos fornecedores, a entrega dos produtos não condiz com a nota fiscal.

Nosso trabalho é exibir o nome dos produtos e o nome do fornecedor, para os produtos fornecidos pelo fornecedor ‘Ajax SA’.

---
 
## Atividades nível 2 ##
---

- 2604 - Menores que 10 ou Maiores que 100
    
    <img width="558" height="295" alt="Image" src="https://github.com/user-attachments/assets/a5311e21-2e9a-41ef-93f3-0f5b97469778" />
    
    ```sql
    select
        id,name
    from 
        products
    where
        price <10 or price >100;
    ```

O setor financeiro da empresa precisa de um relatório que mostre o código e o nome dos produtos cujo preço são menores que 10 ou maiores que 100.

---

- 2613 - Filmes em Promoção
    
    <img width="548" height="301" alt="Image" src="https://github.com/user-attachments/assets/87aa53ab-1c47-456e-933e-5a125f887d6f" />
    
    ```sql
    select 
       movies.id, movies.name 
    from
        movies
    INNER join prices
        on movies.id_prices = prices.id
    where value < 2.00;
    ```
Antigamente a locadora fez um evento em que vários filmes estavam em promoção e querem saber que filmes eram esses.

Nosso trabalho para ajudá-los é selecionar o ID e o nome dos filmes cujo preço for menor que 2.00.

---

## Atividades nível 3 ##

---
- 2610 - Valor Médio dos Produtos
    
    <img width="483" height="303" alt="Image" src="https://github.com/user-attachments/assets/894aca04-688d-4126-8513-515ba179368c" />
    
    ```sql
    select
        ROUND(AVG (price), 2) AS Preçomedio
    from products;
    ```

Numa empresa está sendo feito um levantamento sobre os valores dos produtos que são comercializados.

Para ajudar o setor que está fazendo esse levantamento devemos calcular e exibir o valor médio do preço dos produtos.

## _OBS: Mostrando o valor com dois números após o ponto._ ##

---

- 2618 - Produtos Importados
    
    <img width="520" height="314" alt="Image" src="https://github.com/user-attachments/assets/3940a593-39d7-4d20-85e0-ed3d325524f6" />
    
    ```sql
    select
        products.name, providers.name, categories.name
    from
        products
    INNER JOIN providers
        on products.id_providers = providers.id
    INNER JOIN categories
        on products.id_categories = categories.id
    where 
        providers.name = 'Sansul SA'
        and categories.name = 'Imported';
    ```

O setor de importação da empresa precisa de um relatório sobre a importação de produtos do  fornecedor Sansul.

Nossa tarefa é exibir o nome dos produtos, o nome do fornecedor e o nome da categoria, para os produtos fornecidos pelo fornecedor ‘Sansul SA’ e cujo nome da categoria seja 'Imported'.

---

## Atividade nível 4 ##
---

- 2602 - Select Básico
    
    <img width="398" height="234" alt="Image" src="https://github.com/user-attachments/assets/b2753734-5c01-469d-98d4-de40949c0547" />
    
    ```sql
    select 
        name 
    from 
        customers
    where 
        state like '%RS%';
    ```
A empresa está fazendo um levantamento de quantos clientes estão cadastrados nos estados, porém, faltou levantar os dados do estado do Rio Grande do Sul.

Então devemos exibir o nome de todos os clientes cujo estado seja ‘RS’.

---
## Atividade nível 5 ##
---

- 2616 - Nenhuma Locação
    
    <img width="431" height="302" alt="Image" src="https://github.com/user-attachments/assets/77b8ee7f-f8c8-4217-89a6-06f5a729103a" />
    
    ```sql
    select
        customers.id, customers.name
    from
        customers
    LEFT JOIN locations
        on customers.id = locations.id_customers
    where
        locations.id_customers IS NULL;
    ```
    
A locadora pretende fazer uma promoção para os clientes que ainda não fizeram nenhuma locação.

Nosso trabalho é entregar o ID e o nome dos clientes que não realizaram nenhuma locação. Ordenando a saída por ID.

---
