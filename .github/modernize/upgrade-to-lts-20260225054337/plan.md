# Upgrade Plan: Migrate to Latest LTS Versions

## Overview

This plan upgrades the Java project to the latest Long-Term Support (LTS) versions:
- **Java 21** (latest LTS)
- **Spring Boot 3.4** (latest stable with Spring Framework 6.x)
- **Compatible dependencies** for the upgraded ecosystem

## Tasks

The upgrade is structured in three sequential tasks:

1. **Java Version Upgrade** - Migrate to Java 21 LTS
2. **Spring Boot Upgrade** - Migrate to Spring Boot 3.4 (includes javax → jakarta namespace migration)
3. **Dependency Updates** - Update all third-party libraries to compatible versions

See `tasks.json` for detailed task breakdown, requirements, and success criteria.

## Key Changes

- Java language level: **21**
- Spring Boot: **3.4.x**
- Spring Framework: **6.x**
- Namespace migration: **javax.*** → **jakarta.***
- All dependencies updated for compatibility

## Execution

Tasks must be executed in order due to dependencies. Each task includes validation criteria to ensure build success and test compatibility.
