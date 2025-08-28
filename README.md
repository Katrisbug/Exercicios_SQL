### _Exercícios SQL_ ###
- 2607 - Cidades em Ordem Alfabética
    
   <img width="471" height="243" alt="Image" src="https://github.com/user-attachments/assets/08076d56-3184-4039-84fb-96243b4c417c" />
    
    ```sql
    select city
    from providers
    order by city asc;
    ```
    

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
    

---

- 2615 - Expandindo o Negocio
    
    <img width="408" height="241" alt="Image" src="https://github.com/user-attachments/assets/83d543ec-d062-4dba-9853-ec86347a2933" />
    
    ```sql
    select 
        city
    from customers;
    ```
    

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
    

---

- 2610 - Valor Médio dos Produtos
    
    <img width="483" height="303" alt="Image" src="https://github.com/user-attachments/assets/894aca04-688d-4126-8513-515ba179368c" />
    
    ```sql
    select
        ROUND(AVG (price), 2) AS Preçomedio
    from products;
    ```
    

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
    

---
