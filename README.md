# flyway-springboot
使用flyway融合springboot进行数据库版本控制


参考文档： https://juejin.im/entry/5c948530f265da60ce37a62d


必须先创建一个数据库

CREATE database if NOT EXISTS `test` default character set utf8 collate utf8_general_ci;

当有历史表存在时，第一次执行 flyway 会向数据库创建一条 version=1的记录，然后再执行程序，会报错

update test.flyway_schema_history set success=1 where version=1

必须将版本号为1的状态变成成功，否则脚本会一样报错