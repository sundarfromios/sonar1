Disclamer: The plugin is still in an early phase of development and it is not intended to be used as is. Use it at your own risk.

### Install Sonar
Please follow the instructions from the official Sonar website: [Sonar Installation](http://www.sonarsource.org/screencasts/installation-of-sonar/)

### Download the plugin from sources
* Using git: `git clone https://github.com/fhelg/sonar-objective-c.git /path/to/plugin/sources`
* Without git: Download the repo as a ZIP. Follow these instructions from [this StackOverflow question](http://stackoverflow.com/questions/2751227/how-to-download-source-from-github) for detailed explanations.

### Build the plugin with Maven
Verify that you have Maven installed on your system by running `mvn -v` in a Terminal.
If you see something like `Apache Maven 3.0.3 (r1075438; 2011-02-28 18:31:09+0100)`
`Maven home: /usr/share/maven`
`Java version: 1.7.0_04, vendor: Oracle Corporation`
`...`

You are good. Then run: `mvn clean package`.
This command will generate a JAR file (`sonar-objective-c-plugin-0.0.1-SNAPSHOT.jar`) in the `/path/to/plugin/sources/target` directory.

### Copy the Plugin in Sonar
Copy the `sonar-objective-c-plugin-0.0.1-SNAPSHOT.jar` jar file in the `$SONAR_HOME/extensions/plugins` folder.

### Run Sonar 
Run `sonar.sh start` in `$SONAR_HOME/bin/your_arch/`

### Check
If the Sonar dashboard shows up when navigating to `http://localhost:9000` (the default configuration) you are good.