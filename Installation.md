In order to use this plugin on your SonarQube server instance, you need first to install it. 

### Installing an official SVG Badges plugin release

Installation of official releases of the plugin couldn't be simpler: the plugin is available in SonarQube's update center under the name "SVG Badges". Just search for the plugin, install it, restart yourSonarQube instance and that's it!

### Installing RC or SNAPSHOT version

Release Candidate (RC) versions can be directly downloaded from the [project's GitHub releases page](https://github.com/QualInsight/qualinsight-plugins-sonarqube-badges/releases). If you want to install a RC version or a SNAPSHOT version built from source, you have to follow these steps:

0. Download the RC version of the plugin / or build a SNAPSHOT version of the plugin
1. Stop your SonarQube instance
2. Remove any previously installed version of SVG Badges from `<sonarqube_root_directory>/extensions/plugins`
3. Copy the new version of the plugin to `<sonarqube_root_directory>/extensions/plugins`
4. Start your SonarQube instance
