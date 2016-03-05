# Logging with Tolerado #
This page explains how to switch on/off and control logging with Tolerado. Most of the times you won't need to enable logging for Tolerado. In case you are stuck with some issues and want deep dive, you can enable logging by plugging any logging framework of your choice. This is because Tolerado uses Apache Commons logging.  All the Tolerado framework classes are under "com.tgerm.tolerado" package. So use this package string to setup your logger.

# Log4j logging sample #
I was using log4j for logging, so I'm sharing the simple "DEBUG" console logging setup. I use this inside my Eclipse setup. You can copy the file contents below and create a log4j.properties file in classpath to see logging in action
```
log4j.rootLogger=ERROR, Console
log4j.logger.com.tgerm=DEBUG, Console
log4j.additivity.com.tgerm=false


log4j.appender.Console=org.apache.log4j.ConsoleAppender
log4j.appender.Console.layout=org.apache.log4j.PatternLayout

# Pattern to output the caller's file name and line number.
log4j.appender.Console.layout.ConversionPattern=%5p [%t] (%F:%L) - %m%n
```