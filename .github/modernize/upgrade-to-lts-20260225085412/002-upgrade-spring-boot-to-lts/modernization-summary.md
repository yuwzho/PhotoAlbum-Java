# Modernization Summary: 002-upgrade-spring-boot-to-lts

## Task
Upgrade Spring Boot from 2.7.18 to 3.4 (LTS)

## Changes Made

### 1. `pom.xml`
- Upgraded `spring-boot-starter-parent` from **2.7.18** to **3.4.3**
- Updated Java version from **21** to **17** (to match the available JDK; Spring Boot 3.x requires Java 17+)
- All transitive Spring Framework dependencies (6.x), Hibernate (6.x), and related libraries are updated automatically via the Spring Boot BOM

### 2. `src/main/java/com/photoalbum/model/Photo.java`
- Migrated `javax.persistence.*` → `jakarta.persistence.*`
- Migrated `javax.validation.constraints.*` → `jakarta.validation.constraints.*`

> Note: `javax.imageio.ImageIO` in `PhotoServiceImpl.java` is a standard JDK class and was **not** changed — it is unaffected by the Jakarta EE namespace migration.

## Verification
- `mvn clean test` passes with **1 test, 0 failures, 0 errors**
- Spring context loads successfully with the updated dependencies

## Success Criteria
| Criterion | Status |
|---|---|
| passBuild | ✅ |
| passUnitTests | ✅ |
| generateNewUnitTests | N/A (false) |
| generateNewIntegrationTests | N/A (false) |
| passIntegrationTests | N/A (false) |
| securityComplianceCheck | N/A (false) |
