1. Test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.
* öncelikle PgAdmin içerisinde bulunan Databases kısmına sağ tıklayarak test isimli yeni bir database oluşturuyoruz. Sonra bu database'e sağ tıklayarak Query Tool'a tıklıyoruz.
* daha sonra oluşturmak istediğimiz tabloya ait bilgileri içeren aşağıdaki dizini yazıyoruz.
```sql
 CREATE TABLE employee (
	id INTEGER PRIMARY KEY,
	name VARCHAR(50) NOT NULL,
	birthday DATE,
	email VARCHAR(100)
);
```
* böylece tablomuz id, name, birthday ve email sütunlarını içerecek şekilde oluşturuluyor. 

2. oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.
* Mockaroo üzerinden istediğimiz sütun isimlerini ve o sütunlara ait veri tiplerini(row number, full name, datetime, email şeklinde) isteğimiz doğrultusunda SQL'e uygun olacak şekilde 50 veri ile sınırlı şekilde oluşturmasını istiyoruz.
* bize verdiği dizini kopyalayıp Query Tool üzerinde işlem yaptığımız yere yapıştırıyoruz.
* bize INSERT INTO anahtar kelimesini kullandırtarak bu verileri tabloya ekletiyor.
* örnek dizin:
```sql
insert into employee (id, name, birthday, email) values (50, 'Putnam Woodard', '1990-01-14', 'pwoodard1d@nbcnews.com');
```
3. Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
* birinci güncelleme: id numarası 1 olan satırın name'ini "aleyna rapata" olacak şekilde günceller.
  ```sql
  UPDATE employee
  SET name = 'Aleyna Rapata'
  WHERE id = 1;
  ```
* ikinci güncelleme: Aleyna Rapata isiminin bulunduğu satırda birthday'i "1997-11-21" olacak şekilde günceller.
  ```sql
  UPDATE employee
  SET birthday = '1997-11-21'
  WHERE name = 'Aleyna Rapata';
  ```
* üçüncü güncelleme: Aleyna Rapata isminin bulunduğu satırda email'i "aleyna@rapata.com" olacak şekilde günceller.
  ```sql
  UPDATE employee
  SET email = 'aleyna@rapata.com'
  WHERE name = 'Aleyna Rapata';
  ```
* dördüncü güncelleme: İsmi Torr ile başlayan satırlarda ismi "George Orwell" olarak günceller.
  ```sql
  UPDATE employee
  SET name = 'George Orwell'
  WHERE name LIKE 'Torr%';
  ```
* beşinci güncelleme: email'i "fkruschov3@apple.com" olan satırda birthday'i "1980-01-01" olacak şekilde günceller.
  ```sql
  UPDATE employee
  SET birthday = '1980-01-01'
  WHERE email = 'fkruschov3@apple.com';
  ```
4. Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.
* birinci silme işlemi: id numarası 1 olan satırı siler.
  ```sql
  DELETE FROM employee
  WHERE id = 1
  ```
* ikinci silme işlemi: id numarası 3, 5 ve 7 olan satırları siler.
  ```sql
  DELETE FROM employee
  WHERE id IN(3, 5, 7)
  ```
* üçüncü silme işlemi: adı "Judith Martell" olan satıra ait verileri siler.
  ```sql
  DELETE FROM employee
  WHERE name = 'Judith Martell'
  ``` 
* dördüncü silme işlemi: id numarası 45 ile 50 arasında olan verileri siler.
  ```sql
  DELETE FROM employee
  WHERE id BETWEEN 45 AND 50
  ```
* beşinci silme işlemi: ismi "C" harfi ile başlayan verileri siler.
  ```sql
  DELETE FROM employee
  WHERE name LIKE 'C%'
  ``
