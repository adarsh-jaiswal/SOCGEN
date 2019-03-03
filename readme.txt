Mysql script :- create TABLE STOCKS(  
   STOCK_DATE DATE,
   SYMBOL varchar(10) NOT NULL,
   
STOCK_OPEN FLOAT(10, 5),
   STOCK_CLOSE FLOAT(10, 5),
   LOW FLOAT(10, 5),
  
 HIGH FLOAT(10, 5),
   VOLUME INT,
   PRIMARY KEY (STOCK_DATE, SYMBOL)  
);

Server configuration :-
Add to server.xml-

<Resource auth="Container" driverClassName="com.mysql.jdbc.Driver" 
factory="org.apache.tomcat.jdbc.pool.DataSourceFactory" 
maxActive="10" maxIdle="5" maxWait="10000" minEvictableIdleTimeMillis="55000"
 minIdle="2" name="jdbc/DataSource" password="yourPassword" 
type="javax.sql.DataSource" 
url="jdbc:mysql://your db url" username="your userName" validationQuery="SELECT 1"/>

Add to context.xml-
<ResourceLink global="jdbc/DataSource" name="jdbc/DataSource" type="javax.sql.DataSource"/>

Dump Save:-
copy the dump data under resources folder with file name - stock_prices.csv
