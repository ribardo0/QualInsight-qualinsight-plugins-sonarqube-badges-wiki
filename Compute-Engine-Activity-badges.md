## Usage

Use the ``/api/badges/ce_activity?key=<project or view key>`` URL in order to generate a badge that displays the compute engine activity status of a project or view (available since version 3.0.0) 

## Possible output

Depending on the project's status and SonarQube configuration, one of the following image types will be generated :

* [Success] indicates that last compute engine activity resulted in a success
* [Failed] indicates that last compute engine activity resulted in a failure
* [In Progress] indicates that the last compute engine activity is still in progress
* [Pending] indicates that the last compute engine activity is still pending
* [Canceled] indicates that the last compute engine activity was canceled
* [Not Found] indicates that the project / view could not be found

# Example

Here is a live badge displaying the status of the last analysis (compute engine execution) of the SVG Badges plugin on SonarQube.com:

![Lines Of Code](https://sonarqube.com/api/badges/ce_activity?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges)

## Available options

By default, the plugin generates badges with rounded corners. If you want to generate flat badges instead, add the optional parameter ``template`` with value ``FLAT`` as follows: 

``/api/badges/ce_activity?key=<project or view key>&template=FLAT`` (requires version `3.0.0`.)

If you want the badge to be blinking if the compute engine is in `FAILED` status, add the optional parameter ``blinking`` with value ``true`` as follows: 

``/api/badges/ce_activity?key=<project or view key>&blinking=true`` (requires version `3.0.0`.)

## Display the Compute Engine Activity badge on a web page

You can display Compute Engine Activity badges using HTML or Markdown as follows.

*Note 2*: The plugin is currently installed on SonarQube.com public instance. If you want to display a badge for a project analyzed on SonarQube.com, just use ``https://sonarqube.com`` as ``<serverBaseURL>``.

### HTML Link:

```
<a href="<serverBaseURL>/dashboard/index/<project or view key>"><img src="<serverBaseURL>/api/badges/ce_activity?key=<project or view key>"/></a>
```

Example:

```
<a href="http://localhost:9000/dashboard/index/com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges"><img src="http://localhost:9000/api/badges/ce_activity?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges"/></a>
```

### Markdown Link:

```
[![Quality Gate](<serverBaseURL>/api/badges/ce_activity?key=<project or view key>)](<serverBaseURL>/dashboard/index/<project or view key>)
```

Example:

```
[![Quality Gate](http://localhost:9000/api/badges/ce_activity?key=com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges)](http://localhost:9000/dashboard/index/com.qualinsight.plugins.sonarqube:qualinsight-plugins-sonarqube-badges)
```