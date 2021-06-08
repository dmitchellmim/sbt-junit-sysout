This is a simple example of SBT not populating the sysout and syserr fields of a JUnit XML report ([sbt/sbt#6537](https://github.com/sbt/sbt/issues/6537)).

1. Run the unit test with `sbt test`.
2. Check the XML output in `target/test-reports`.
3. The XML includes the following instead of populating those fields with the actual output from the test. This is because [`JUnitXmlTestsListener.scala` hardcodes them to always be empty](https://github.com/sbt/sbt/blob/fabeed222799efcc46be15bccf2c31e384f7e369/testing/src/main/scala/sbt/JUnitXmlTestsListener.scala#L166). 

```lang=xml
<system-out><![CDATA[]]></system-out>
<system-err><![CDATA[]]></system-err>
```
