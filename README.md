# finaltask

1. Tabel Analisa

Syntax BigQuery Tabel Transaction:
SELECT * FROM `transaction-418906.kf_final_transaction.transaction` LIMIT 672460 

Penjelasan syntax: 
Mengambil semua kolom dari transaction dengan membatasi jumlah baris yaitu 672460 baris 

![alt text](https://github.com/nasywahdarraini20/finaltask/blob/main/transaction.png?raw=true)


Syntax BigQuery Tabel Kantor Cabang: 
SELECT * FROM `kantor-cabang-418907.kf_kantor_cabang.kantor_cabang` LIMIT 1728 

Penjelasan syntax: 
Mengambil semua kolom dari transaction dengan membatasi jumlah baris yaitu 1728 baris 

![alt text](https://github.com/nasywahdarraini20/finaltask/blob/main/kantor%20cabang.png?raw=true) 

2. Challenge

Syntax BigQuery Tabel Final Transaction: 
SELECT 
    rating,
    customer_name,
    product_id,
    price,
    discount_percentage,
    CASE 
        WHEN price <= 50000 THEN 0.1
        WHEN price > 50000 AND price <= 100000 THEN 0.15
        WHEN price > 100000 AND price <= 300000 THEN 0.2
        WHEN price > 300000 AND price <= 500000 THEN 0.25
        ELSE 0.3
    END AS persentase_gross_laba,
    price * (1 - discount_percentage) AS nett_sales,
    price * (1 - discount_percentage) * 
    CASE 
        WHEN price <= 50000 THEN 0.1
        WHEN price > 50000 AND price <= 100000 THEN 0.15
        WHEN price > 100000 AND price <= 300000 THEN 0.2
        WHEN price > 300000 AND price <= 500000 THEN 0.25
        ELSE 0.3
    END AS nett_profit,
    rating
FROM 
    `finaltransaction.transaction.finaltransaction`
LIMIT 672461;

Penjelasan Syntax: 
- Perintah SELECT digunakan untuk memilih kolom-kolom yang ingin ditampilkan dalam hasil query. Dalam kasus ini, kolom yang dipilih adalah rating, customer_name, product_id, price, dan discount_percentage
- terdapat penggunaan fungsi CASE untuk menentukan nilai dari kolom persentase_gross_laba dan nett_profit berdasarkan nilai dari kolom price.
- perintah LIMIT digunakan untuk membatasi jumlah baris hasil query yang ditampilkan, dalam hal ini 672461 baris.


