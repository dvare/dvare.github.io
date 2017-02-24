## Table of Contents

   * [Introduction](#introduction)
   * [Installation](#installation)
      * [Dependency](#dependency)
      * [Configuration](#configuration)
   * [License](#license)

## Introduction

The dvare-framework is a model-based java expression language designed to describe business logic in [Dvare Rule Engine](#). The dvare-framework contains set of predefined which helps non-technical background peoples to describe business logic in the real domain.

## Installation

### Dependency
The artifact dvare-framework is published is a central repository. In order to use snapshot versions, you need to add the following maven repository in your `pom.xml`:

```xml
<repository>
    <id>ossrh</id>
    <url>https://oss.sonatype.org/content/repositories/snapshots</url>
</repository>
```


 Maven dependency:
```xml
<dependencies>
        <dependency>
            <groupId>org.dvare</groupId>
            <artifactId>dvare-framework</artifactId>
            <version>1.4</version>
        </dependency> 
</dependencies>      
```
### Configuration

 Java config:
```java
String functionsPackages=new String[]{"org.dvare.function"};
Boolean silentMode=false;
RuleConfiguration ruleConfiguration= new RuleConfiguration(functionsPackages,silentMode);
```

Spring config:
```xml
<!-- application-context.xml --> 
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xmlns="http://www.springframework.org/schema/beans"
        xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd">
    <bean id="ruleEngine" class="org.dvare.spring.DvareConfigFactoryBean">
        <property name="functions">
            <list>
                 <value>org.dvare.function</value>
            </list>
        </property>
        <property name="silentMode">false</property>
    </bean>
</beans>
```

```java
ApplicationContext context = new ClassPathXmlApplicationContext("application-context.xml");
RuleConfiguration ruleConfiguration = context.getBean(RuleConfiguration.class);
```

## License
Dvare Framework  is released under the [![MIT license](http://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat)](http://opensource.org/licenses/MIT).

```
The MIT License (MIT)

Copyright (c) 2016-2017 DVARE (Data Validation and Aggregation Rule Engine)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Sogiftware.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
