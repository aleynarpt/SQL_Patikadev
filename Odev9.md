1. city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
```sql
SELECT city, country from city
INNER JOIN country ON city.country_id = country.country_id;
```
2. customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
```sql
SELECT payment_id, customer.first_name, customer.last_name FROM payment
INNER JOIN customer ON customer.customer_id = payment.customer_id;
```
3. customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
```sql
SELECT rental_id, customer.first_name, customer.last_name FROM rental
INNER JOIN customer ON customer.customer_id = rental.customer_id
```
