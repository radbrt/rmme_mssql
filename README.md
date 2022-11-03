# Testing target-mssql

Scripts to populate test table in postgres:

```
 CREATE TABLE badges (
id SERIAL PRIMARY KEY,
User_id VARCHAR(64) NULL,
name VARCHAR(64) NULL,
date DATE NULL,
class INTEGER NULL
 );

INSERT INTO badges (User_id, name, date, class, main_docs) (
    SELECt upper(substr(md5(random()::text), 0, 3)),
    lower(substr(md5(random()::text), 0, 25)),
    CURRENT_DATE,
    2
);

```