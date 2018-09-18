```xml
  <!-- Լ���������� -->
  
  <configuration>

    <properties resource="jdbc.properties"/>
	<properties resource="jdbc.properties2"/>
	
	<properties	 >
        <!-- ���̺�ģ������ -->
     
        <property  name="projectName" value="icy-web"></property >		
        <property  name="projectDir" value="e://myproject"></property > //../
        <property  name="templateDir" value="src/main/resources/template/"> </property >  //"src/main/resources/lu/template/
        <property  name="exportMode;" value="in"></property > //in [out,zipout]
        <property  name="exportDir" value="e:/out"></property > //home 
        <property  name="override" value="true"></property >	//false 
      </properties>
      
      
        <!-- ���ݿ��������� -->
        <jdbcConnection driverClassName="${jdbc.driverClassName}" 
                        url="${jdbc.url}" 
                        username="${jdbc.username}" 
                        password="${jdbc.password}">
        </jdbcConnection>

	
	<templates>	//package="" file=="{{name}}"    />
		<template 
                  name="controller" 
                  package="com.sxt.controller�� 
                  file="${className}Controller.java"     />
		<template name="service" package="com.sxt.service file="${className}Service.java"     />
		<template name="serviceImpl" package="com.sxt.service.impl file="${className}ServiceImpl.java"     />
		<template name="dao" package="com.sxt.dao" file="${className}dao.java"     />
		<template name="mapper" package="com.sxt.mapper" file="${className}mapper.java"     />		
		<template name="entity" package="com.sxt.entity" file="${className}.java"     />
     <template name="custom" package="com.sxt.custom" file="${className}Custom.java"     />                                                                            
	</templates>	

    <modules>
		<!-- ���isSubΪfalse������moduleNameΪ�գ���ʾ������ģ��WW -->
		<module isSub="false" 				//false
			moduleName="myIn" 
			sourceDir="src/main/java" 			//src/main/java
			resourceDir="src/main/resource" 	//src/main/resource
			templates="controller,service,serviceImpl,dao,mapper,entity"  //*
		/>
	<modules>

    <tables>
			<!-- ���������moduleName,Ĭ��ʹ��modules�ĵ�һ��module���� -->
			<!-- ������Ҫ���ɴ�����࣬tableName������; className������ -->
            <table tableName="icy_user" className="User" ></table>
            <table tableName="icy_role" className="Role" ></table>
            <table tableName="icy_funcright" className="Funcright" ></table>
            <table tableName="icy_menu" className="Menu" ></table>-->
            <table tableName="icy_user" className="User" ></table>
            <table tableName="icy_depart" className="Depart" ></table>

    </tables>
                                                            
 
</configuration>                                                           
```



����



��ǰtable��

tableConfig                 [key=propName , value= propValue]



propertiesConfig    [key=prop@propName,value= propVelue ]

jdbcConnectionConfig	 [key=jdbc@PropName,value= jdbcPropValue]

templateConfig		 [key=tpl@{tplName}.key,value= value]

moduleConfig		 [key=mod@{tplName}.key,value= value]





config			

 [key=prop@allKey , value= allValue]

 [key=jdbc@allKey , value= allValue]

 [key=tpl@allKey , value= allValue]

 [key=mod@allKey , value= allValue]



## ģ�����


tableName

className

entityName

**table**

table.tableName   	����

table.catalog;

table.schema;

table.comment

table.remark;

table.hasPk

table.columns

table.pkColumns

table.notPkColumns

table.className  	����������ĸ��д

table.entityName 	bean��������ĸСд



**package**

controller.package

service.package

mapper.package

dao.package

entity.package






column ����

- columnName
- fieldName
- columnName?upper_case
- remark
- decimalDigits;
- javaType
- sqlType
- javaTypeName
- sqlTypeName
- defaultValue
- comment 
- remark
- columnSize
- isIndex
- isUnique
- isNullable
- isPk
- siFk
- autoIncrement



other

- date  ʱ��
- author ����

## ģ������


** properties**



**template**

name

file

package

type = 1:source ,2:  rescource 

Ĭ��
template name=controller file="${table}.java"   package=��com.sxt��
template name=service 
template name=ServiceImpl
template name=mapper
template name=dao
template name=entity


�Զ���template�� 
template name= MyTemplate  type=resource package=��com.mytempalte��



template�Զ����ɲ�����

module����

service.package

mappe.rpackage

dao.package

entity.package

MyTemplate.package


�Զ��������

MyTemplate.package




**common**

genType 	���ɷ�ʽ: 1���ɵ����̣� 2���������ļ� .3 ���ɵ�ҳ��

override

projectName

projectDir

templateDir

jdbc.driverClassName

jdbc.url

jdbc.username

jdbc.password

�Զ�������

**module**

isSubModule

moduleName

sourceDir

resourceDir

templates = [ 
ServiceImpl.package , 
controllerTemplate  
serviceTemplate , 
ServiceImplTemplate ,
mapperTemplate,
myTemplate,

]



**table**  

moduleName

tableName

className



