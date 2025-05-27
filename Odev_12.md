_**GENEL TEKRAR**_

__________
1. film tablosundan 'K' karakteri ile başlayan en uzun ve replacement_cost'u en düşük 4 filmi sıralayınız.
```sql
SELECT title, length, replacement_cost FROM film
WHERE title LIKE 'K%'
ORDER BY length DESC, replacement_cost ASC
LIMIT 4;
```
2. film tablosunda içerisinden en fazla sayıda film bulunduran rating kategorisi hangisidir?
```sql
SELECT rating, COUNT(rating) FROM film
GROUP BY rating
ORDER BY COUNT(rating) DESC
LIMIT 1;
```
3. customer tablosunda en çok alışveriş yapan müşterinin adı nedir?
```sql
SELECT customer.customer_id, customer.first_name, customer.last_name FROM customer
INNER JOIN payment ON customer.customer_id = payment.customer_id
GROUP BY customer.customer_id
ORDER BY COUNT(payment_id) DESC
LIMIT 1;
```
4. category tablosundan kategori isimlerini ve kategori başına düşen film sayılarını sıralayınız.
```sql
SELECT category.name, COUNT(film_category.film_id) FROM category
JOIN film_category ON category.category_id = film_category.category_id
GROUP BY category.name
ORDER BY COUNT(film_category.film_id) DESC;
```
5. film tablosunda isminde en az 4 adet 'e' veya 'E' karakteri bulunan kç tane film vardır?
```sql
SELECT title FROM film
WHERE title ILIKE '%e%e%e%e%'
```

