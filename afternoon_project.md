PERSON

  1.
    create table person(
      person_id serial primary key,
      name varchar(200),
      age integer,
      height integer,
      city varchar(200),
      favorite_color varchar(200)
      );


  2.
    insert into person (
      name, age, height, city, favorite_color
    ) values (
      'Andy', 25, 73, 'Vineyard', 'green'
    );

    insert into person (
      name, age, height, city, favorite_color
    ) values (
      'Tori', 23, 70, 'Vineyard', 'green'
    );

    insert into person (
      name, age, height, city, favorite_color
    ) values (
      'Matt', 25, 73, 'American Fork', 'blue'
    );

    insert into person (
      name, age, height, city, favorite_color
    ) values (
      'Claire', 24, 68, 'Springville', 'pink'
    );

    insert into person (
      name, age, height, city, favorite_color
    ) values (
      'Casey', 25, 68, 'American Fork', 'red'
    );


  3. select * from person
    order by height desc;

    
  4. select * from person
    order by height asc;


  5. select * from person
    order by age desc;


  6. select * from person
  where age > 20;


  7. select * from person
  where age = 18;


  8. select * from person
  where age < 20
  and age > 30;

  9. select * from person
  where age != 27;

  10. select * from person
  where favorite_color != 'red';

  11. select * from person
  where favorite_color != 'red'
  and favorite_color != 'blue';

  12. select * from person
  where favorite_color = 'orange'
  or favorite_color = 'green';

  13. select * from person
  where favorite_color in('orange','green', 'blue');

  14. select * from person
  where favorite_color in('yellow', 'purple');

ORDERS

  1. create table orders(
    order_id serial primary key, 
    person_id integer, 
    product_name varchar(200), 
	  product_price numeric,
    quantity integer
  );

  2. 
    insert into orders(
      person_id, product_name, product_price, quantity
    ) values (
      1, 'vitamin C', 5.99, 2
    );

    insert into orders(
      person_id, product_name, product_price, quantity
    ) values (
      2, 'vitamin D', 4.99, 3
    );

    insert into orders(
      person_id, product_name, product_price, quantity
    ) values (
      3, 'lawn chair', 15.99, 6
    );

    insert into orders(
      person_id, product_name, product_price, quantity
    ) values (
      3, 'firepit', 59.99, 1
    );

    insert into orders(
      person_id, product_name, product_price, quantity
    ) values (
      4, 'tiny house', 80000, 1
    );

  3. select * from orders

  4. select sum(quantity) from orders

  5. select sum(product_price) from orders

  6. select sum(product_price) from orders
     where person_id = 3   

ARTIST

  1. 
    insert into artist(
      name
    ) values(
      'Rezz'
    )

    insert into artist(
      name
    ) values(
      'San Holo'
    ) 

    insert into artist(
      name
    ) values(
      'Illenium'
    ) 

    2. select * from artist
    order by name desc
    limit 10;

    3. select * from artist
    order by name asc
    limit 5;

    4. select * from artist
    where name like 'Black%'

    5. select * from artist
    where name like '%Black%'

EMPLOYEE
  
  1. select * from employee
where city = 'Calgary';

  2. select * from employee
order by birth_date desc
limit 1;

  3. select * from employee
order by birth_date asc
limit 1;

  4. select * from employee
where reports_to = 2;

  5. select count( city) from employee
where city =  'Lethbridge';


INVOICE

  1. select count (billing_country) from invoice
where billing_country = 'USA';

  2. select * from invoice
order by total desc
limit 1;

  3. select * from invoice
order by total asc
limit 1;

  4. select * from invoice
where total > 5;

  5. select count(total) from invoice
where total <5;

  6. select count(billing_state) from invoice
where billing_state in ('CA', 'TX', 'AZ');

  7. select avg(total) from invoice;

  8. select sum(total) from invoice;