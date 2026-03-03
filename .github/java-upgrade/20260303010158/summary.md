
# Upgrade Java Project

## 🖥️ Project Information
- **Project path**: C:\code\samples\repos\photo-album-java-fork
- **Java version**: 21
- **Build tool type**: Maven
- **Build tool path**: C:\Users\yuwzho\.maven\maven-3.9.12\bin

## 🎯 Goals

- Upgrade Spring Boot to 3.4.x

## 🔀 Changes

### Test Changes
|     | Total | Passed | Failed | Skipped | Errors |
|-----|-------|--------|--------|---------|--------|
| Before | 1 | 1 | 0 | 0 | 0 |
| After | 1 | 1 | 0 | 0 | 0 |
### Dependency Changes


#### Upgraded Dependencies
| Dependency | Original Version | Current Version | Module |
|------------|------------------|-----------------|--------|
| org.springframework.boot:spring-boot-starter-web | 2.7.18 | 3.4.5 | photo-album |
| org.springframework.boot:spring-boot-starter-thymeleaf | 2.7.18 | 3.4.5 | photo-album |
| org.springframework.boot:spring-boot-starter-data-jpa | 2.7.18 | 3.4.5 | photo-album |
| com.oracle.database.jdbc:ojdbc8 | 21.5.0.0 | 23.5.0.24.07 | photo-album |
| org.springframework.boot:spring-boot-starter-validation | 2.7.18 | 3.4.5 | photo-album |
| org.springframework.boot:spring-boot-starter-json | 2.7.18 | 3.4.5 | photo-album |
| org.springframework.boot:spring-boot-starter-test | 2.7.18 | 3.4.5 | photo-album |
| com.h2database:h2 | 2.1.214 | 2.3.232 | photo-album |
| org.springframework.boot:spring-boot-devtools | 2.7.18 | 3.4.5 | photo-album |

### Code commits

All code changes have been committed to branch `appmod/java-upgrade-20260303010158`, here are the details:
4 files changed, 13 insertions(+), 7 deletions(-)

- a426304 -- Upgrade Spring Boot to 3.3.13, migrate javax.* to jakarta.* namespace

- 7cacfdd -- Upgrade Spring Boot to 3.4.5
### Potential Issues

#### CVEs
- commons-io:commons-io:2.11.0:
  - [**HIGH**][CVE-2024-47554](https://github.com/advisories/GHSA-78wr-2p64-hpwj): Apache Commons IO: Possible denial of service attack on untrusted input to XmlStreamReader
