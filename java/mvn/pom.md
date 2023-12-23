```xml
    <dependencies>
    <!-- https://mvnrepository.com/artifact/org.springframework.boot/spring-boot-starter-web -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
        <version>2.7.8</version>
    </dependency>

    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
        <version>2.7.8</version>
    </dependency>
    <!--        <dependency>-->
    <!--            <groupId>org.springframework</groupId>-->
    <!--            <artifactId>spring-test</artifactId>-->
    <!--            <scope>test</scope>-->
    <!--        </dependency>-->
    <dependency>
        <groupId>org.junit.jupiter</groupId>
        <artifactId>junit-jupiter-api</artifactId>
        <version>5.9.2</version>
        <scope>dev</scope>
    </dependency>
    <dependency>
        <groupId>org.junit.jupiter</groupId>
        <artifactId>junit-jupiter-engine</artifactId>
        <version>5.9.2</version>
        <scope>test</scope>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.mockito/mockito-core -->
    <dependency>
        <groupId>org.mockito</groupId>
        <artifactId>mockito-core</artifactId>
        <version>5.3.1</version>
        <scope>test</scope>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.mockito/mockito-junit-jupiter -->
    <dependency>
        <groupId>org.mockito</groupId>
        <artifactId>mockito-junit-jupiter</artifactId>
        <version>5.3.1</version>
        <scope>test</scope>
    </dependency>
    <!--mybatis-plus-->
    <!-- https://mvnrepository.com/artifact/com.baomidou/mybatis-plus-boot-starter -->
    <dependency>
        <groupId>com.baomidou</groupId>
        <artifactId>mybatis-plus-boot-starter</artifactId>
        <version>3.5.3</version>
    </dependency>

    <!--mybatis-plus 代码生成器-->
    <!-- https://mvnrepository.com/artifact/com.baomidou/mybatis-plus-generator -->
    <dependency>
        <groupId>com.baomidou</groupId>
        <artifactId>mybatis-plus-generator</artifactId>
        <version>3.5.3.1</version>
    </dependency>

    <!-- Mybatis Plus 代码生成器模板引擎,  -->
    <!-- https://mvnrepository.com/artifact/org.apache.velocity/velocity-engine-core -->
    <dependency>
        <groupId>org.apache.velocity</groupId>
        <artifactId>velocity-engine-core</artifactId>
        <version>2.3</version>
    </dependency>


    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>8.0.33</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/io.springfox/springfox-swagger2 -->
    <dependency>
        <groupId>io.springfox</groupId>
        <artifactId>springfox-swagger2</artifactId>
        <version>2.9.1</version>
    </dependency>
    <dependency>
        <groupId>com.zaxxer</groupId>
        <artifactId>HikariCP</artifactId>
        <version>4.0.3</version>
    </dependency>
    <dependency>
        <groupId>org.aspectj</groupId>
        <artifactId>aspectjweaver</artifactId>
        <version>1.9.19</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api -->
    <dependency>
        <groupId>org.apache.logging.log4j</groupId>
        <artifactId>log4j-api</artifactId>
        <version>2.20.0</version>
    </dependency>

    <!-- https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core -->
    <dependency>
        <groupId>org.apache.logging.log4j</groupId>
        <artifactId>log4j-core</artifactId>
        <version>2.20.0</version>
    </dependency>

    <!-- https://mvnrepository.com/artifact/org.projectlombok/lombok -->
    <dependency>
        <groupId>org.projectlombok</groupId>
        <artifactId>lombok</artifactId>
        <version>1.18.28</version>
        <scope>provided</scope>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.apache.commons/commons-dbcp2 -->
    <dependency>
        <groupId>org.apache.commons</groupId>
        <artifactId>commons-dbcp2</artifactId>
        <version>2.9.0</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.mybatis/mybatis -->

    <dependency>
        <groupId>com.alibaba</groupId>
        <artifactId>fastjson</artifactId>
        <version>1.2.78</version>
    </dependency>
</dependencies>
```

### junit


```text
### org.junit.jupiter:junit-jupiter-api

这个库包含了开发者用于编写JUnit Jupiter测试的API。它提供了用于编写测试用例的注解（如 `@Test`, `@BeforeEach`, `@AfterEach`, `@BeforeAll`, `@AfterAll` 等），断言库 (`Assertions`)，以及测试实例生命周期的相关API。简单来说，这个库让你能够编写测试用例，但它本身并不包含测试运行的功能。

### org.junit.jupiter:junit-jupiter-engine

这个库是JUnit Jupiter的测试引擎，是JUnit 5的核心之一。当你在构建工具（如 Maven 或 Gradle）中引入这个库时，它会提供真正执行测试用例的能力。这个测试引擎会在运行时查找使用JUnit Jupiter API编写的测试用例，并运行它们。换句话说，它负责测试执行的过程。

该测试引擎能够通过JUnit Platform Launcher API启动，这让IDEs（如Eclipse或IntelliJ IDEA）、构建工具（如Maven或Gradle），以及其他测试工具可以发现并且运行JUnit Jupiter测试用例。

在使用 Maven 或 Gradle 这样的构建系统时，`junit-jupiter-engine` 库会被添加到测试运行时持续集成过程中，而 `junit-jupiter-api` 会被用来在编码阶段提供必要的注解和API。
```

### include

通过引入这两个库，你可以完成 JUnit Jupiter 测试的编写和执行，并获得相应的测试报告和结果。
```
```xml
    <build>
        <!--                java '-Dfile.encoding=utf-8' -jar -->
        <!--                java -Dfile.encoding=utf-8 -jar -->
        <!--        项目打包时会将Java目录中的*.xml文件也进行打包-->
        <resources>
            <resource>
                <directory>src/main/java</directory>
                <includes>
                    <include>**/*.xml</include>
                </includes>
            <!--        上述XML片段是Maven的POM文件中关于资源过滤器（resource filtering）的配置。这段配置表明在构建项目时，
            会将src/main/java目录下的所有.xml文件包括到编译后的输出中，同时禁用资源过滤。
            对于每个被包含的.xml文件，Maven会执行过滤器的替换操作，将其中的占位符（如${variable}）替换为实际的值。但在这里，
            由于<filtering>false</filtering>配置了false，表示禁用了资源过滤，所以不会进行替换操作，直接将原始内容复制到输出目录中。
            这样做可以保留.xml文件中的特殊字符和变量占位符，适用于配置文件等需要保持原始内容的场景。
            如果你需要启用资源过滤器，你可以将<filtering>修改为true，这样在构建过程中就会按照Maven的默认规则对资源文件进行过滤替换操作。-->
                <filtering>false</filtering>
            </resource>
            <resource>
                <directory>src/main/resources</directory>
                <includes>
                    <include>*.yaml</include>
                    <include>*.xml</include>
                    <include>*.yml</include>
                </includes>
                <filtering>false</filtering>
            </resource>
        </resources>
    </build>
```


