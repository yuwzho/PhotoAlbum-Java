# Java Upgrade Plan - Latest LTS Versions

## Overview

This plan upgrades the Java project to the latest Long-Term Support (LTS) versions:
- **Java 21** (latest LTS)
- **Spring Boot 3.4** (latest stable with Spring Framework 6.x)
- **Updated dependencies** (compatible with Java 21 and Spring Boot 3.4)

## Migration Strategy

The upgrade is structured in three sequential phases:

1. **Java Version Upgrade** - Migrate to Java 21, update build configurations
2. **Spring Boot Upgrade** - Upgrade to Spring Boot 3.4, migrate javax.* to jakarta.* packages
3. **Dependency Updates** - Update third-party libraries to latest compatible versions with security compliance

## Tasks

See `tasks.json` for the detailed task breakdown, dependencies, success criteria, and execution requirements.

## Notes

- Tasks must be executed in sequence due to dependencies
- Each task uses the `java-version-upgrade` builtin skill
- All tasks include build and unit test validation as success criteria
- Security compliance check is enabled for the final dependency update task
