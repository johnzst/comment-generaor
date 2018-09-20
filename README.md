**mybatis 逆向工程 注释 1.0.0**
---

### pom 添加插件实例: ### 
    <plugin>
        <groupId>org.mybatis.generator</groupId>
        <artifactId>mybatis-generator-maven-plugin</artifactId>
        <version>1.3.6</version>
        <configuration>
            <verbose>true</verbose>
            <overwrite>true</overwrite>
            <configurationFile>generatorConfig.xml</configurationFile>
        </configuration>
        <dependencies>
            <dependency>
                <groupId>com.mycomment</groupId>
                <artifactId>comment-generator</artifactId>
                <version>1.0.0</version>
            </dependency>
        </dependencies>
    </plugin>

### 配置文件 修改: ### 
    contex下:
        <property name="javaFileEncoding" value="UTF-8"/>
         ......
        <commentGenerator type="MyCommentGenerator">
             <property name="suppressAllComments" value="true"/>
         </commentGenerator>
         

### 命令: ### 
    (-P mybatis-gen 只有在 pom 中有profile 配置 时 添加)
    mvn mybatis-generator:generate -e -P mybatis-gen