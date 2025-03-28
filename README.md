# Mavenリポジトリ
GitHub Packagesを使ったMavenリポジトリです。
https://maven.pitan76.net/ に設置しているMavenリポジトリとは独立したものです。
maven.pitan76.netの方はミラーとして使おうと考えています。

## repositories
### Gradle
- build.gradle
```build.gradle
repositories {
    maven {
        url "https://maven.pkg.github.com/PTOM76/maven"
        credentials {
            username = project.findProperty("gpr.user") ?: System.getenv("GITHUB_ACTOR")
            password = project.findProperty("gpr.key") ?: System.getenv("GITHUB_TOKEN")
        }
    }
}
```

### Maven
- pom.xml
```pom.xml
  <repositories>
    <repository>
      <id>github-packages</id>
      <url>https://maven.pkg.github.com/PTOM76/maven</url>
    </repository>
  </repositories>
```

- settings.xml
```settings.xml
<settings>
  <servers>
    <server>
      <id>github-packages</id>
      <username>${env.GITHUB_ACTOR}</username>
      <password>${env.GITHUB_TOKEN}</password>
      <configuration>
        <httpHeaders>
          <property>
            <name>Authorization</name>
            <value>Basic ${base64 username:token}</value>
          </property>
        </httpHeaders>
      </configuration>
    </server>
  </servers>
</settings>
```
