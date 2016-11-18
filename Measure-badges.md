## Usage

In order to generate a badge that displays any measure related to a project or view analysed by your SonarQube instance, call the following REST webservice:

``/api/badges/measure?key=<project or view key>&metric=<metric key>``

## Possible output

The badge displays the name of the metric in the left part of the badge with the measured value in the right part of the badge.

If the measure impacts the quality gate of the project, the badge is colorized depending on the condition that has been set (requires version `3.0.0`.)

If no measure is available for the metric, or if no metric with this ``<metric key>`` exists, then ``N/A`` will be displayed in the right part of the badge.

# Example

Here are example live badges displaying the current value of some metrics measured on the SVG Badges plugin codebase taken from SonarQube.com:

![Lines Of Code](https://sonarqube.com/api/badges/measure?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges&metric=ncloc)
![New Bugs](https://sonarqube.com/api/badges/measure?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges&metric=new_bugs)
![New Vulnerabilities](https://sonarqube.com/api/badges/measure?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges&metric=new_vulnerabilities)
![New Code Smells](https://sonarqube.com/api/badges/measure?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges&metric=new_code_smells)
![Public Documented API density](https://sonarqube.com/api/badges/measure?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges&metric=public_documented_api_density)
![Test Success Density](https://sonarqube.com/api/badges/measure?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges&metric=test_success_density)
![Overall Coverage](https://sonarqube.com/api/badges/measure?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges&metric=overall_coverage)
![Technical Debt Ratio](https://sonarqube.com/api/badges/measure?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges&metric=sqale_debt_ratio)

## Available options

As for quality gate status badges, the plugin generates by default badges with rounded corners. If you want to generate flat badges instead, add the optional parameter ``template`` with value ``FLAT`` as follows: 

``/api/badges/measure?key=<project or view key>&metric=<metric key>&template=FLAT`` (requires version `3.0.0`.)

If you want the badge to be blinking if the displayed measure causes the quality gate's `ERROR` status, add the optional parameter ``blinking`` with value ``true`` as follows: 

``/api/badges/measure?key=<project or view key>&metric=<metric key>&blinking=true``  (requires version `3.0.0`.)

SonarQube's [CoreMetrics class](https://github.com/SonarSource/sonarqube/blob/master/sonar-plugin-api/src/main/java/org/sonar/api/measures/CoreMetrics.java) file lists all `metric keys` that can be used. For even more details, see the [SonarQube Metric Definitions](http://docs.sonarqube.org/display/SONAR/Metric+Definitions). I have listed the ones you may need to display as a badge in the following table :

| Metric key | Description |
|------------|-------------|
| ncloc | # of lines of code (excluding comments and empty lines) |
| comment_lines_density | Percentage of comments |
| public_documented_api_density | Percentage of documented API |
| function_complexity | Complexity by function |
| tests_errors | # of tests that have stopped due to an error |
| tests_failures | # of tests whose assertions have failed |
| skipped_tests | # of ignored tests |
| test_success_density | %age of tests that have succeeded |
| coverage | UT coverage %age |
| new_coverage | UT coverage %age on new code |
| it_coverage | IT coverage %age |
| new_it_coverage | IT coverage %age on new code |
| overall_coverage | Overall coverage %age |
| new_overall_coverage | Overall coverage %age on new code |
| duplicated_lines_density | lines duplication %age |
| blocker_violations | # of blocker issues |
| critical_violations | # of new critical issues |
| new_blocker_violations | # of blocker issues |
| new_critical_violations | # of new critical issues |
| code_smells | # of code smells |
| new_code_smells | # of new code smells |
| bugs | # of bugs |
| new_bugs | # of new bugs |
| vulnerabilities | # of vulnerabilities |
| new_vulnerabilities | # of new vulnerabilities |
| sqale_debt_ratio | technical debt ratio |
| new_sqale_debt_ratio | new technical debt ratio |

*Note*: Some `metric keys` are not usable "as is" as they return values that need interpretation (such as time, effort or ratings.) This explains why I haven't added them to the table yet.

## Display the Measure badge on a web page

As for Quality Gate badges, you can use HTML or markdown as follows:

### HTML Link:

```
<a href="<serverBaseURL>/dashboard/index/<project or view key>"><img src="<serverBaseURL>/api/badges/measure?key=<project or view key>&metric=<core metric key>"/></a>
```

Example:

```
<a href="http://localhost:9000/dashboard/index/com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges"><img src="http://localhost:9000/api/badges/measure?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges&metric=coverage"/></a>
```

### Markdown Link:

```
[![Quality Gate](<serverBaseURL>/api/badges/gate?key=<project or view key>&metric=<core metric key>)](<serverBaseURL>/dashboard/index/<project or view key>)
```

Example:

```
[![Quality Gate](http://localhost:9000/api/badges/measure?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges&metric=coverage)](http://localhost:9000/dashboard/index/com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges)
```