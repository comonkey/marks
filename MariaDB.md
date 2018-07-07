##1 复制innodb表不能使用的问题
前提：copy ibd、frm from one mariadb to the other

select * from t_user ;
ERROR 1932 (42S02): Table 'cemudb.t_user' doesn't exist in engine
