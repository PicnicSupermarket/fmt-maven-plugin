## Usage

### Standard pom.xml

Add to your pom.xml

```
    <build>
        <plugins>
            <plugin>
                <groupId>com.coveo</groupId>
                <artifactId>fmt-maven-plugin</artifactId>
                <version>1.0-SNAPSHOT</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>format</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
``` 

`sourceDirectory` represents the directory where your Java sources that need to be formatted are contained. It defaults to `${project.build.sourceDirectory}`

`testSourceDirectory` represents the directory where your test's Java sources that need to be formatted are contained. It defaults to `${project.build.testSourceDirectory}`

`additionalSourceDirectories` represents a list of additional directories that contains Java sources that need to be formatted. It defaults to an empty list.

`verbose` is whether the plugin should print a line for every file that is being formatted. It defaults to `false`.

### Full pom.xml


pom.xml with all available parameters:

```
    <build>
        <plugins>
            <plugin>
                <groupId>com.coveo</groupId>
                <artifactId>fmt-maven-plugin</artifactId>
                <version>1.0-SNAPSHOT</version>
                <configuration>
                    <sourceDirectory>some/source/directory</sourceDirectory>
                    <testSourceDirectory>some/test/directory</testSourceDirectory>
                    <verbose>true</verbose>
                    <additionalSourceDirectories>
                        <param>some/dir</param>
                        <param>some/other/dir</param>
                    </additionalSourceDirectories>
                </configuration>
                <executions>
                    <execution>
                        <goals>
                            <goal>format</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
``` 

### Command line

You can also use it on the command line

`mvn com.coveo:fmt-maven-plugin:format`

You can pass parameters via standard `-D` syntax.
`mvn com.coveo:fmt-maven-plugin:format -Dverbose=true`