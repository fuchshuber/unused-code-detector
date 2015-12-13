**Finds and reports unused code in Jenkins api** (including in latest published plugins and potential usage in jelly files, except getters, setters and fields, except deprecated classes and methods, except api used in WEB-INF/lib/*.jar, except unit tests)

Current results in summary:
* 1114 plugins
* 614 public, protected or package Jenkins methods are not used in the latest published plugins and in core

See details in this [example of output](../blob/master/Output_example.html).

To be sure that a method is never used, you can [grep all sources](https://wiki.jenkins-ci.org/display/JENKINS/Grepping+all+sources) or [search in github](https://github.com/search?type=Code&q=user%3Ajenkinsci+SomeClass.staticMethod) directly, in particular because some methods are used only in jelly views.

See also:
* Unused deprecated classes, methods and fields are listed in the [deprecated-usage-in-plugins job](https://ci.jenkins-ci.org/view/Infrastructure/job/infra_deprecated-usage-in-plugins/ws/target/output.html#deprecatedApiNotUsed) using [this tool](https://github.com/jenkins-infra/deprecated-usage-in-plugins)
* [Jenkins policy for API deprecation](https://issues.jenkins-ci.org/browse/JENKINS-31035)

To run the tool yourself : Checkout and run with "mvn clean compile exec:java".
Note: it is quite long to download all the plugins the first time (1.8 GB).

[License MIT](../blob/master/LICENSE.txt)

Author Emeric Vernat