Use the ``/api/badges/gate?key=<project or view key>`` URL in order to generate a badge that displays the quality gate status of a project or view. Depending on the project's status and SonarQube configuration, one of the following image types will be generated :

* [Passing](images/gate_rounded_passing.svg) indicates that the project passes the quality gate (QG)
* [Warning](images/gate_rounded_warning.svg) indicates that the project does not pass the quality gate due to QG warnings
* [Failing](images/gate_rounded_failing.svg) indicates that the project does not pass the quality gate due to QG errors
* [No Gate](images/gate_rounded_notset.svg) indicates that no quality gate has been set for the specified project
* [Not Found](images/gate_rounded_notfound.svg) indicates that the project / view could not be found

By default, the plugin generates badges with rounded corners. If you want to generate flat badges instead, add the optional parameter ``template`` with value ``FLAT`` as follows: ``/api/badges/gate?key=<project or view key>&template=FLAT`` (requires version `2.1.0`.)

If you want the badge to be blinking if the quality gate is in `ERROR` status, add the optional parameter ``blinking`` with value ``true`` as follows: ``/api/badges/gate?key=<project or view key>&blinking=true`` (requires version `2.1.0`.)

#### Display the Quality Gate badge on a web page

You can display Quality Gate badges using HTML or Markdown as follows.

*Note 1*: The plugin is currently installed on SonarQube.com public instance. If you want to display a badge for a project analyzed on SonarQube.com, just use ``https://sonarqube.com`` as ``<serverBaseURL>``.

##### HTML Link:

```
<a href="<serverBaseURL>/dashboard/index/<project or view key>"><img src="<serverBaseURL>/api/badges/gate?key=<project or view key>"/></a>
```

Example:

```
<a href="http://localhost:9000/dashboard/index/com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges"><img src="http://localhost:9000/api/badges/gate?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges"/></a>
```

##### Markdown Link:

```
[![Quality Gate](<serverBaseURL>/api/badges/gate?key=<project or view key>)](<serverBaseURL>/dashboard/index/<project or view key>)
```

Example:

```
[![Quality Gate](http://localhost:9000/api/badges/gate?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges)](http://localhost:9000/dashboard/index/com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges)
```
