# sc-repository
how to do


 <?xml version="1.0" encoding="UTF-8" ?> 
- <beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:p="http://www.springframework.org/schema/p" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
- <bean id="dataSource" class="org.apache.commons.dbcp.BasicDataSource">
  <property name="driverClassName" value="oracle.jdbc.driver.OracleDriver" /> 
  <property name="url" value="jdbc:oracle:thin:@localhost:1521:xe" /> 
  <property name="username" value="system" /> 
  <property name="password" value="oracle" /> 
  </bean>
- <bean id="mysessionFactory" class="org.springframework.orm.hibernate3.LocalSessionFactoryBean">
  <property name="dataSource" ref="dataSource" /> 
- <property name="mappingResources">
- <list>
  <value>employee.hbm.xml</value> 
  </list>
  </property>
- <property name="hibernateProperties">
- <props>
  <prop key="hibernate.dialect">org.hibernate.dialect.Oracle9Dialect</prop> 
  <prop key="hibernate.hbm2ddl.auto">update</prop> 
  <prop key="hibernate.show_sql">true</prop> 
  </props>
  </property>
  </bean>
- <bean id="template" class="org.springframework.orm.hibernate3.HibernateTemplate">
  <property name="sessionFactory" ref="mysessionFactory" /> 
  </bean>
- <bean id="d" class="com.javatpoint.EmployeeDao">
  <property name="template" ref="template" /> 
  </bean>
  </beans>
