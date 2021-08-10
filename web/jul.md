# JUL是JDK提供的log日志工具

## JUL 转 logback 配置

### 必要的jar包
`    <dependency>
      <groupId>org.slf4j</groupId>
      <artifactId>jul-to-slf4j</artifactId>
    </dependency>
`

### 启动日志配置
`
static {
        LogManager.getLogManager().reset();
        SLF4JBridgeHandler.removeHandlersForRootLogger();
        SLF4JBridgeHandler.install();
    }
`

### logback.xml配置
`
<configuration>
  <contextListener class="ch.qos.logback.classic.jul.LevelChangePropagator">
    <resetJUL>true</resetJUL>
  </contextListener>
</configuration>  
`

### 增加对使用JUL对应jar的放开
`
  <logger name="oracle.ucp" level="TRACE" additivity="false">
    <appender-ref ref="${log.appender:-FILE}" />
    <appender-ref ref="CONSOLE" />
  </logger>
`
