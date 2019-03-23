# [log4net的配置文件详解](http://www.cnblogs.com/dragon/archive/2005/03/24/124254.html)

## 主要理解：
  ### 1. Logger，appender的区别，一个logger里面可以配置多个不同的appender。
   appender里面包括了:
   ```xml
    <appender name="LogInfoAppender" type="log4net.Appender.RollingFileAppender" >
      <file value="log/infofile/" />
      <!--多线程时采用最小锁定-->
      <lockingModel type="log4net.Appender.FileAppender+MinimalLock"/>
      <appendToFile value="true" />
      <rollingStyle value="Composite" />
      <staticLogFileName value="false" />
      <datePattern value="yyyyMMddHHMM'.log'" />
      <maxSizeRollBackups value="100" />
      <maximumFileSize value="5MB" />
      <layout type="log4net.Layout.PatternLayout">
        <conversionPattern value="%message%newline" />
      </layout>
      <filter type="log4net.Filter.LevelRangeFilter">
        <levelMin value="INFO" />
        <levelMax value="INFO" />
      </filter>
    </appender>
   ```
   使用lockingModel标签来控制log4net使用多线程机制。
   
   ### 2. 注意log的日志级别
   
   从低到高：ALL->DEBUG->INFO->WARN->ERROR->FATAL->OFF
   
   
   
   ### 3. aps.netcore 使用log4net的方式
   [.NET Core log4net 使用](https://www.cnblogs.com/linezero/p/log4net.html)
