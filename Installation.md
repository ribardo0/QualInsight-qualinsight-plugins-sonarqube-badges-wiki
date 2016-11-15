In order to use this plugin on your SonarQube server instance, you need first to install it. The plugin is available in SonarQube's update center under the name "SVG Badges". 

Release Candidate (RC) versions can be directly downloaded from the [project's GitHub releases page](https://github.com/QualInsight/qualinsight-plugins-sonarqube-badges/releases).

### Requirements and Compatibility Matrix

| SVG Badges Plugin | SonarQube             | Main Features                                               |
|-------------------|-----------------------|-------------------------------------------------------------| 
| 3.0.x             | 5.6.x LTS and above   | CE Activity Badges, Flat badges, Blinking and color effects |
| 2.0.x             | 5.5.x and above       | Measures Badges                                             |
| 1.2.x             | 4.5.4 LTS up to 5.1.x | Quality Gate Badges                                         |

## Configuration

By default, the plugin is configured as follows: 

* quality gate badges webservice is activated 
* measures badges webservice is activated 
* compute engine activity badges webservice is activated 

You can modify this configuration on SonarQube's administration page ("SVG Badges" section.)

![Configuration screen](images/configuration.png)
