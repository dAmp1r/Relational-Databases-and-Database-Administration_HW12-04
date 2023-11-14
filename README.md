# Relational-Databases-and-Database-Administration_HW12-04

*SQL. Часть 2 - Горбунов Д.Н.*

Задание 1.

```select concat(st.last_name, ' ', st.first_name) as staf, ci.city, count(c.customer_id) as cust from customer c inner join staff st on st.store_id = c.store_id inner join store s on s.manager_staff_id = st.staff_id inner join address a on a.address_id = st.address_id inner join city ci on ci.city_id = a.city_id group by ci.city_id having cust > 300 ;```

Задание 2.

```select count(title) as amount_film from film where length > (select avg(length) from film);```

Задание 3.

```select date_format(payment_date, '%m %Y') as date, count(r.rental_id) as amount_rental from payment p inner join rental r on p.rental_id = r.rental_id group by date order by sum(amount) desc limit 1;```
