# Spring-JdbcTemplate

Welcome to the Spring-JdbcTemplate- wiki!

* create database query
* create pojo class
* create jdbcTemaplate Execute query:
* create application Context.xml with database connection:
* create main java class

```
create table employee(id number(10),name varchar(100),salary number(10));
```


##### employee java:

```
public class Employee{
private int id;
private String name;
Private float salary;
getter setter methos
} 
```

#### private JdbcTemplate JdbcTemplate:


```
public int Save(Employee e){
String Query="insert into employee vales(
"+e.getId()+","+e.getName+",salary=+e.getsalary()+"'";
return jdbcTemplate.update(query);

public int deletQuery(Employeee){
String query="delete from employee where id="+e.getId()+"";
return jdbcTemplate.update(delete);
}

```

#### application contect.xml:
```
<bean id="ds" class="org.spring.framework.jdbc.datasource.DriverManagerDataSource">
<property name="driverclass" value="oracle.jdbc.driver.oracleDriver">
<property name="url" value="localjost:1522:xe:/>
<property name="username" value="system"/>
<property name="password" value="oracle"/>
</bean>

<bean id="jdbctemplate" class="org.spring.jdbc.core.JdbcTemplate">
<property name="datasource" red="ds"></property>
</bean>

<bean id="edao" class="com.javatpoint.EmployeeDao">
<property name="jdbcTemplate" ref="jdbcTemplate">
</bean>

</beans>

```
#### test.java:

```
Applicationcontext ctx=new ClassPathXmlApplcationContext("applicationContext.xml");

EmployeeDao dao=(EmployeeDao).getBean("dao");
int status=dao.saveEmployee(new Employee(102,"amit",35000));
system.out.printlnt(status);

```
#### preparedstatement:

```
boolean saveEmployeeByPrearedStatement(final Employeee e)
{
String query="insert into employee values(?,?,?)";
return jdbcTemplate.execute(query,new PreparedStatementCallBack<Boolean>(){

public Boolean doInPreparedStatement(PreparedStatement ps){

ps.setInt(1,e.getId());
ps.setString(2,e.getName());
ps.setFloat(3,e.getSalary());

return ps.execute();
}}
```

#### prepared statement:

```
ps.setId(1,e.getId());
ps.setString(2,e.getName());
ps.setFloat(3,e.getsalary());

fetching record from JDBCTemplate:
template.query
template.
->easily fetch records from database using query method

public list<Employee> getAllEmployee(){
return template.query("select * from employee");
List<Employee> list=new ArrayList<Employee>();
while(rs.next()){
Employee e=new Employee();
e.setId(rs.getInt(1));
e.setName(rs.getString(2));
e.setSalary(rs.getInt(3));
list.add(e);
}
return list;
}
  
  
  ```


main class:

```
employee dao=(EmployeeDao)ctx.getBean("edao");
dao.saveEmployeeByPreparedStatement(new Employee(108,"Amit",35000));
```




#### Jdbc data source:


### JdbcDaoImpl:

JdbcTemplate  jdbcTemplate=new JdbcTemplate();

DataSource:

setter
getter

JdbcTemplate  

getter
setter

#### spring.xml:

```
<context:annotation-config/>
<bean id="datasource" class="org.apache.common.dcp.basicdatasource"/>
<property name="driverClassName" value="org.class.apache.derby."/>
<property name="url" value=""/>
<property name="initialSize" value="2"/>
<property name="maxAccess" value="5"/>\
</bean>
```

#### JDBCDemo.java:

```
main()
{
ApplicationContext ctx=new ClassPathXmlApplicationContext("Spring.xml");
JdbcDaoImpl dao=ctx.getBean("jdbcDaoImpl",jdbcdaoimpl.class);
}
```
`

`https://www.youtube.com/watch?v=0LYqy0wvS20`
