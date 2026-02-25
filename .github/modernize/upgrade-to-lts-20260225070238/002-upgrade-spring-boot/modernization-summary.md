# Task 002 - Upgrade Spring Boot to 3.4.x

## Summary

Upgraded Spring Boot from **3.3.5** to **3.4.7** (latest stable in the 3.4.x line).

## Changes Made

### `pom.xml`
- Updated `spring-boot-starter-parent` version from `3.3.5` → `3.4.7`

## Namespace Migration

The `jakarta.*` namespace migration was already complete (done in a prior step):
- All JPA and validation annotations in `Photo.java` already use `jakarta.persistence.*` and `jakarta.validation.*`
- The `javax.imageio.ImageIO` import in `PhotoServiceImpl.java` is part of the Java SE standard library (`java.desktop` module) and is **not** subject to the Jakarta EE namespace migration; it correctly remains as `javax.imageio`

## Spring Boot 3.4.x Notable Changes Handled

| Area | Status |
|---|---|
| `jakarta.*` namespace | Already migrated |
| Spring Framework 6.x compatibility | Inherited via Spring Boot 3.4.7 parent |
| Hibernate 6.6.x | No code changes required |
| HikariCP 5.x | No code changes required |
| Multipart/validation config properties | No deprecated properties found |
| `spring.jpa.open-in-view` warning | Existing warning; no action required for this task |

## Verification

- **Build**: `mvn clean package -DskipTests` → ✅ SUCCESS
- **Unit Tests**: `mvn test` → ✅ 1 test run, 0 failures, 0 errors
