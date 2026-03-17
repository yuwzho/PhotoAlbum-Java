# Upgrade Plan

## Overview

Upgrade the Java project to the latest LTS versions: **Java 21** and **Spring Boot 3.4**.

## Tasks

See `tasks.json` for detailed task breakdown.

### 001 - Upgrade Java & Spring Boot

- **Target Java**: 21 (LTS)
- **Target Spring Boot**: 3.4
- **Target Spring Framework**: 6.x
- Migrate `javax.*` imports to `jakarta.*` where required
- Update all Spring ecosystem dependencies (Spring Security, Spring Data, etc.) to compatible versions
- Resolve deprecated APIs and breaking changes

## Success Criteria

| Criterion              | Required |
|------------------------|----------|
| Build passes           | Yes      |
| Unit tests pass        | Yes      |
| New unit tests         | No       |
| New integration tests  | No       |
| Integration tests pass | No       |
| Security compliance    | No       |
