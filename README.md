# seata-client-re-create-test

- For https://github.com/apache/shardingsphere/issues/29052 and https://github.com/apache/incubator-seata/issues/7039 .

- Verified unit test under Ubuntu 22.04.4 LTS with `SDKMAN!` and `Docker CE`.

```shell
sdk install java 23-open

git clone git@github.com:linghengqian/seata-client-re-create-test.git
cd ./seata-client-re-create-test/
sdk use java 23-open
./mvnw -T 1C clean test
```

- The log is as follows.


```shell
$ ./mvnw -T 1C clean test
[INFO] Scanning for projects...
[INFO] 
[INFO] Using the MultiThreadedBuilder implementation with a thread count of 16
[INFO] 
[INFO] ---------< io.github.linghengqian:seata-client-re-create-test >---------
[INFO] Building seata-client-re-create-test 1.0-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ seata-client-re-create-test ---
[INFO] Deleting /home/linghengqian/TwinklingLiftWorks/git/public/seata-client-re-create-test/target
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ seata-client-re-create-test ---
[INFO] skip non existing resourceDirectory /home/linghengqian/TwinklingLiftWorks/git/public/seata-client-re-create-test/src/main/resources
[INFO] 
[INFO] --- compiler:3.13.0:compile (default-compile) @ seata-client-re-create-test ---
[INFO] No sources to compile
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ seata-client-re-create-test ---
[INFO] Copying 4 resources from src/test/resources to target/test-classes
[INFO] 
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ seata-client-re-create-test ---
[INFO] Recompiling the module because of changed source code.
[INFO] Compiling 1 source file with javac [debug target 23] to target/test-classes
[INFO] 
[INFO] --- surefire:3.2.5:test (default-test) @ seata-client-re-create-test ---
[INFO] Using auto detected provider org.apache.maven.surefire.junitplatform.JUnitPlatformProvider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running io.github.linghengqian.SimpleTest
[ERROR] 2024-12-03 13:09:55.851 [main] o.a.s.config.ConfigurationFactory - failed to load non-spring configuration :not found service provider for : org.apache.seata.config.ConfigurationProvider
org.apache.seata.common.loader.EnhancedServiceNotFoundException: not found service provider for : org.apache.seata.config.ConfigurationProvider
[ERROR] 2024-12-03 13:09:58.387 [main] o.a.s.config.ConfigurationFactory - failed to load non-spring configuration :not found service provider for : org.apache.seata.config.ConfigurationProvider
org.apache.seata.common.loader.EnhancedServiceNotFoundException: not found service provider for : org.apache.seata.config.ConfigurationProvider
[ERROR] 2024-12-03 13:10:05.710 [main] o.a.s.config.ConfigurationFactory - failed to load non-spring configuration :not found service provider for : org.apache.seata.config.ConfigurationProvider
org.apache.seata.common.loader.EnhancedServiceNotFoundException: not found service provider for : org.apache.seata.config.ConfigurationProvider
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 15.13 s -- in io.github.linghengqian.SimpleTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  17.543 s (Wall Clock)
[INFO] Finished at: 2024-12-03T13:10:06+08:00
[INFO] ------------------------------------------------------------------------
```
