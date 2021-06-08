This is a simple example of SBT not populating the sysout and syserr fields of a JUnit XML report.

1. Run the unit test with `sbt test`.
2. Check the XML output in `target/test-reports`.
3. The XML includes the following instead of populating those fields with the actual output from the test.

```lang=xml
<system-out><![CDATA[]]></system-out>
<system-err><![CDATA[]]></system-err>
```