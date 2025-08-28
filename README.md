Exercícios SQL
- 2607 - Cidades em Ordem Alfabética
    
   <img width="471" height="243" alt="Image" src="https://github.com/user-attachments/assets/08076d56-3184-4039-84fb-96243b4c417c" />
    
    ```sql
    select city
    from providers
    order by city asc;
    ```
    

---

- 2602 - Select Básico
    
    ![image.png](attachment:c2b59077-dede-43e7-bf18-5fffbe619bfb:image.png)
    
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
    
    ![image.png](attachment:72f9c5e8-1fbd-4996-9160-bb20bb7652b6:image.png)
    
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
    
    ![image.png](attachment:3bdd6ca0-8f60-4653-9a03-2c92a339efd7:image.png)
    
    ```sql
    select 
        max(price),
        min(price)
    from
        products;
    ```
    

---

- 2615 - Expandindo o Negocio
    
    ![image.png](attachment:5f62ee95-fdd4-4764-8597-ca0831c3f29b:image.png)
    
    ```sql
    select 
        city
    from customers;
    ```
    

---

- 2617 - Fornecedor Ajax SA
    
    ![image.png](attachment:e48b89b1-04d2-4d06-bad2-f46c50821ea5:fda0fce1-01ec-43f3-903a-e90c38bee66f.png)
    
    ```sql
    select products.name, providers.name
    from providers
    inner join products
        on products.id_providers = providers.id
    where providers.name = 'Ajax SA';
    ```
    

---

- 2604 - Menores que 10 ou Maiores que 100
    
    ![image.png](attachment:b7f6147c-8037-49d2-8a08-786e10f3ec6d:image.png)
    
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
    
    ![image.png](attachment:ade9b622-479f-4e2a-b137-ee89c8497fec:image.png)
    
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
    
    ![image.png](attachment:57a54793-83f8-4a8f-a3db-a6de5ef7bf7e:image.png)
    
    ```sql
    select
        ROUND(AVG (price), 2) AS Preçomedio
    from products;
    ```
    

---

- 2618 - Produtos Importados
    
    ![image.png](attachment:433bb1ea-c79b-4efd-9f31-122b9e491b9f:image.png)
    
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
    
    ![image.png](attachment:3186c73b-eac0-4f25-ba56-ac4d4ba0072c:image.png)
    
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
