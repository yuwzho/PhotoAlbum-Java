# Upgrade Plan

## Overview
Upgrade the Java project to the latest LTS versions: Java 21 and Spring Boot 3.4.

## Tasks
See tasks.json for the detailed task breakdown.

### 001 - Upgrade Java and Spring Boot
- Upgrade JDK to Java 21
- Upgrade Spring Boot to 3.4 and Spring Framework to 6.x
- Migrate javax.* to jakarta.* namespaces where applicable
- Update build configuration (Maven/Gradle) to target Java 21
- Resolve any breaking API changes introduced by the new versions
