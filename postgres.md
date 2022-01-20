<h2 align="center">Postgres helper</h2>

* Temporary tables:
```sql
CREATE TEMPORARY TABLE tb_codes_temp (cd_code VARCHAR(5));

INSERT INTO tb_codes_temp (cd_code) 
VALUES 
	('12884'),
	('12893');

SELECT * FROM tb_codes_temp;
```
