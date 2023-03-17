# cp1-jpa

![image](https://user-images.githubusercontent.com/101119026/225845435-3c339df6-53b2-40dd-b365-f31b0c58040e.png)

![image](https://user-images.githubusercontent.com/101119026/225845583-20b317d8-c695-469e-a917-67c1e47e8f21.png)

![image](https://user-images.githubusercontent.com/101119026/225845636-57f59038-d9a2-429f-b358-58713541c7b2.png)

![image](https://user-images.githubusercontent.com/101119026/225845699-185a8e58-0d08-41fb-a8f1-6900128369f5.png)

![image](https://user-images.githubusercontent.com/101119026/225845760-83eece88-4243-48c3-976e-9b9ac1bb7b48.png)

![image](https://user-images.githubusercontent.com/101119026/225845842-343b4eaf-757a-494a-b3a9-ca4dec29a84a.png)



![image](https://user-images.githubusercontent.com/101119026/225845891-e4e3441d-373e-4f6d-a217-940a1bbb63bd.png)

![image](https://user-images.githubusercontent.com/101119026/225846639-76cc9f5b-0d15-4663-ad05-6f14f8d07618.png)

![image](https://user-images.githubusercontent.com/101119026/225846705-ef5642cf-13f4-468c-8711-535e877fe12e.png)

![image](https://user-images.githubusercontent.com/101119026/225846773-98485a8a-6423-42c5-97c6-cfb23481ae6e.png)

![image](https://user-images.githubusercontent.com/101119026/225846824-95c5ed39-5b94-4cc5-b3b1-710a2def7eec.png)

![image](https://user-images.githubusercontent.com/101119026/225846876-dd06a8e5-df4f-4aa2-b798-1340e72e7d5c.png)



```js
  <properties>
    <maven.compiler.source>11</maven.compiler.source>
    <maven.compiler.target>11</maven.compiler.target>
  </properties>
  ```
  
  ```js
    <dependencies>

		<!-- https://mvnrepository.com/artifact/org.hibernate/hibernate-core -->
		<dependency>
			<groupId>org.hibernate</groupId>
			<artifactId>hibernate-core</artifactId>
			<version>5.6.7.Final</version>
		</dependency>

		<!-- https://mvnrepository.com/artifact/org.hibernate/hibernate-entitymanager -->
		<dependency>
			<groupId>org.hibernate</groupId>
			<artifactId>hibernate-entitymanager</artifactId>
			<version>5.6.7.Final</version>
		</dependency>

		<!-- https://mvnrepository.com/artifact/mysql/mysql-connector-java -->
		<dependency>
			<groupId>mysql</groupId>
			<artifactId>mysql-connector-java</artifactId>
			<version>8.0.28</version>
		</dependency>

		<!-- oracle -->
		<dependency>
			<groupId>com.oracle.database.jdbc</groupId>
			<artifactId>ojdbc8</artifactId>
			<version>21.1.0.0</version>
		</dependency>
		<!-- Fim oracle -->

		<!-- https://mvnrepository.com/artifact/com.oracle/ojdbc14 -->
		<!-- <dependency>
			<groupId>com.oracle</groupId>
			<artifactId>ojdbc14</artifactId>
			<version>9.0.2.0.0</version>
		</dependency> -->

	</dependencies>
 ```
```js
	<?xml version="1.0" encoding="UTF-8"?>
<persistence xmlns="http://xmlns.jcp.org/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence
    http://xmlns.jcp.org/xml/ns/persistence/persistence_2_1.xsd" version="2.1">

	<persistence-unit name="exemplo-jpa" transaction-type="RESOURCE_LOCAL">

		<properties>

			<!-- mysql -->
			<property name="javax.persistence.jdbc.url" value="jdbc:mysql://localhost/aulajpa?useSSL=false&amp;serverTimezone=UTC" />
			<property name="javax.persistence.jdbc.driver" value="com.mysql.jdbc.Driver" />
			<property name="javax.persistence.jdbc.user" value="root" />
			<property name="javax.persistence.jdbc.password" value="" />
			<property name="hibernate.hbm2ddl.auto" value="update" />
			<property name="hibernate.dialect" value="org.hibernate.dialect.MySQL8Dialect" />
			<!-- Fim -->

			<!-- oracle 
			<property name="hibernate.show_sql" value="true" />
			<property name="hibernate.format_sql" value="true" />
			<property name="hibernate.hbm2ddl.auto" value="update" />
			<property name="hibernate.dialect" value="org.hibernate.dialect.Oracle12cDialect" />
			<property name="javax.persistence.jdbc.driver" value="oracle.jdbc.OracleDriver" />
			<property name="javax.persistence.jdbc.user" value="rm93611" />
			<property name="javax.persistence.jdbc.password" value="240203" />
			<property name="javax.persistence.jdbc.url" value="jdbc:oracle:thin:@oracle.fiap.com.br:1521:orcl" />
			Fim -->

		</properties>

	</persistence-unit>

</persistence>
```
![image](https://user-images.githubusercontent.com/101119026/225852662-42205cfd-38ba-44f2-9191-50ffa6172483.png)

dominio/Pessoa = implements Serializable / private static final long serialVersionUID = 1l; / atributos / gere construtores / getters and setters / override toString/ não esquecer das anotations: @Entity acima da classe

aplicacao/Programa = métedo main / estancie objetos / chame o EntityManagerFactory emf = Persistence.createEntittyManagerFactory(**nome do persistence unit name**); /  chame o EntityManager em = emf.createEntityManager(); para persistir o obj >> em.persist(obj1); 
