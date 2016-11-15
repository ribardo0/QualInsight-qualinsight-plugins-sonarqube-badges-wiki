In order to use this plugin on your SonarQube server instance, you need first to install it. 

Installation of official releases of the plugin couldn't be simpler: the plugin is available in SonarQube's update center under the name "SVG Badges". Just search for the plugin, install it, restart yourSonarQube instance and that's it!

Release Candidate (RC) versions can be directly downloaded from the [project's GitHub releases page](https://github.com/QualInsight/qualinsight-plugins-sonarqube-badges/releases). If you want to install a RC version or a SNAPSHOT version built from source, you have to follow these steps:

1. Stop your SonarQube instance
2. Remove any previously installed version of SVG Badges from `<sonarqube_root_directory>/extensions/plugins`
3. Copy the new version of the plugin to `<sonarqube_root_directory>/extensions/plugins`
4. Start your SonarQube instance
