##1 复制innodb表不能使用的问题
前提：copy ibd、frm from one mariadb to the other

select * from t_user ;
ERROR 1932 (42S02): Table 'cemudb.t_user' doesn't exist in engine


##2 ERROR 1130 (HY000): Host is not allowed to connect to this MySQL server.
无法远程访问。
Why you cannot connect to mysql remotely?
Your root account, and this statement applies to any account, may only have been added with localhost access (which is recommended).
You can check this with:
SELECT host FROM mysql.user WHERE User = 'root';


##3 add index （innodb bulk loading）

truncate <table>;

set autocommit = 0;

load data infile <path> into table <table>...

commit;
other optimisations you can use to boost load times:

set unique_checks = 0;
set foreign_key_checks = 0;
set sql_log_bin=0;
