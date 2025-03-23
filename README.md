# Mavenリポジトリ
GitHub Packagesを使ったMavenリポジトリです。
https://maven.pitan76.net/ に設置しているMavenリポジトリとは独立したものです。
maven.pitan76.netの方はミラーとして使おうと考えています。

## repositories
- build.gradle
```build.gradle
    maven { url "https://maven.pkg.github.com/PTOM76/maven" }
```

- pom.xml
```pom.xml
        <repository>
          <id>github</id>
          <url>https://maven.pkg.github.com/OWNER/REPOSITORY</url>
          <snapshots>
            <enabled>true</enabled>
          </snapshots>
        </repository>
```
