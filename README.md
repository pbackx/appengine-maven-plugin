# appengine-maven-plugin
Fork of official appengine-maven-plugin that supports configuration of server through settings.xml

To use it, you will need to build and host the plugin in your repository and configure it like this in your pom.xml

	<plugin>
		<groupId>com.arcbees.appengine</groupId>
		<artifactId>appengine-maven-plugin</artifactId>
		<version>1.9.19-SNAPSHOT</version>
		<configuration>
			<port>${gae.port}</port>
			<oauth2>false</oauth2>
			<serverId>appengine.google.com</serverId>
	  </configuration>
	</plugin>

And put a settings section in your Maven ~/.m2/settings.xml

  <settings>
    <servers>
      <server>
        <id>appengine.google.com</id>
        <username>your.email@domain.com</username>
        <password>yourpassword</password>
      </server>
    </servers>
  </settings>

Deploy (you'll need to use the FQM of the plugin):

  mvn com.arcbees.appengine:appengine-maven-plugin:update
