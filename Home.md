Welcome to the Spring-JdbcTemplate- wiki!


`jdbc data source:


jdbcDaoImpl:

JdbcTemplate  jdbcTemplate=new JdbcTemplate();

DataSource:

setter
getter

JdbcTemplate  

getter
setter

spring.xml:

<context:annotation-config/>
<bean id="datasource" class="org.apache.common.dcp.basicdatasource"/>
<property name="driverClassName" value="org.class.apache.derby."/>
<property name="url" value=""/>
<property name="initialSize" value="2"/>
<property name="maxAccess" value="5"/>\
</bean>






JDBCDemo.java:

main()
{
ApplicationContext ctx=new ClassPathXmlApplicationContext("Spring.xml");
JdbcDaoImpl dao=ctx.getBean("jdbcDaoImpl",jdbcdaoimpl.class);
}

`