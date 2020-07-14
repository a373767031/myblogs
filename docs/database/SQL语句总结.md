# SQL语句总结

### **select**

查询

### **from** 

cp整个表创建为临时表

### **where 查询条件**

根据查询条件，截取满足条件的部分，创建为新的临时表

### **group** by 字段

根据字段分组，根据满足条件的部分，创建新的临时表

### **having**

对上一个临时表里不满足条件的进行删除

这个查询语句是唯一一个不创建新的临时表的语句

与where不同之处在于，

 1. 无法单独出现，相当于和group by绑定的where，而where可以单独出现
 2. 出现的位置，where在group by前面，而having只能在group by 后出现
 3.  WHERE命令每次只能操作临时表中一个数据行，HAVING命令每次只能操作一个临时表
 4.  WHERE命令后面，不能使用聚合函数，HAVING命令后面，【可以/必须】使用聚合函数统计当前临时表信息是否满足条件

### **odrer by**

order by 专门对SELECT生成的临时表数据行进行排序。
   将排序后的数据行存入到一个全新的临时表中

### **limit**

​	对表进行截取，

​	分页查询情景下

​	**select \* from table limit (start-1)\*pageSize,pageSize;** 其中**start**是页码，**pageSize**是每页显示的条数

### **join on**

### **distinct  消除重复**