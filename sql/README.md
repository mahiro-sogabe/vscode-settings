# sql

## 前提

本ディレクトリの設定はVSCodeの拡張機能([Prettier SQL VSCode](https://marketplace.visualstudio.com/items?itemName=inferrinizzard.prettier-sql-vscode))を使用します。

## 適用例

### 例1

```sql
--
-- some_table
--
CREATE TABLE
    IF NOT EXISTS some_table (
        some_column_a CHARACTER VARYING(64)
      , some_column_b TIMESTAMP(6) WITHOUT TIME zone DEFAULT NULL
      , some_column_c INTEGER DEFAULT NULL
      , PRIMARY KEY (some_column_a)
    );
COMMENT ON TABLE some_table IS 'SOME_TABLE';
COMMENT ON COLUMN some_table.some_column_a IS 'SOME_COLUMN_A';
COMMENT ON COLUMN some_table.some_column_b IS 'SOME_COLUMN_B';
COMMENT ON COLUMN some_table.some_column_c IS 'SOME_COLUMN_C';
```

### 例2

```sql
UPDATE some_table
SET
    some_column_a = "aaa"
    AND some_column_c = 12
WHERE
    some_column_a = "AAA"
    AND some_column_c < 10;
```

### 例3

```sql
INSERT INTO
    some_table (some_column_a, some_column_b, some_column_c)
VALUES
    ("AAA", NULL, 1);
```