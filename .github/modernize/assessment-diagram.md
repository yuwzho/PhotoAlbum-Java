# Photo Album Application - Architecture Diagram

## Application Architecture

```mermaid
flowchart TD
    Browser["Browser\nUser Interface"]

    subgraph AppLayer["Application - Spring Boot 2.7 / Java 8"]
        subgraph Presentation["Presentation Layer"]
            Templates["Thymeleaf Templates\nindex.html, detail.html, layout.html"]
            Static["Static Assets\nCSS, JavaScript"]
        end

        subgraph Controllers["Web Layer - Spring MVC Controllers"]
            HomeCtrl["HomeController\nGET / - gallery view\nPOST /upload - upload photos"]
            DetailCtrl["DetailController\nGET /photo - photo detail"]
            FileCtrl["PhotoFileController\nGET /photo/file - serve photo data"]
        end

        subgraph Services["Business Logic Layer"]
            PhotoSvc["PhotoService\nUpload validation\nImage processing\nCRUD operations"]
        end

        subgraph DataAccess["Data Access Layer - Spring Data JPA"]
            PhotoRepo["PhotoRepository\nJpaRepository\nNative Oracle SQL queries"]
        end
    end

    subgraph Storage["Data Storage"]
        OracleDB[("Oracle Database\ngvenzl/oracle-free\nStores photo BLOBs\nPort 1521")]
        LocalFS["Local File System\nstatic/uploads/\nRelative paths"]
    end

    Browser -->|"HTTP GET/POST"| HomeCtrl
    Browser -->|"HTTP GET"| DetailCtrl
    Browser -->|"HTTP GET"| FileCtrl
    HomeCtrl -->|"renders"| Templates
    DetailCtrl -->|"renders"| Templates
    Templates -->|"serves"| Static
    HomeCtrl --> PhotoSvc
    DetailCtrl --> PhotoSvc
    FileCtrl --> PhotoSvc
    PhotoSvc --> PhotoRepo
    PhotoRepo -->|"JDBC ojdbc8\nJPA/Hibernate"| OracleDB
    PhotoSvc -->|"file upload path"| LocalFS
```

## Technology Stack

| Layer | Technology |
|-------|-----------|
| Language | Java 8 |
| Framework | Spring Boot 2.7.18 |
| Web | Spring MVC |
| Templating | Thymeleaf |
| ORM | Spring Data JPA / Hibernate |
| Database | Oracle Database (ojdbc8) |
| File I/O | Apache Commons IO |
| Build | Maven |
| Container | Docker / Docker Compose |

## Assessment Findings Summary

The AppCAT assessment identified the following areas for cloud migration consideration:

| Finding | Rule | Description |
|---------|------|-------------|
| Relative file path | azure-file-system-02000 | Application uses relative paths for file storage which is not suitable for cloud deployments |
| Hardcoded password | azure-password-01000 | Passwords found in configuration files should be stored in a secrets manager |
| Static content | spring-boot-to-azure-static-content-01000 | Static content should be served from a CDN or blob storage in cloud deployments |

## Deployment Architecture

```mermaid
flowchart LR
    subgraph Docker["Docker Compose Environment"]
        App["photoalbum-java-app\nSpring Boot\nPort 8080"]
        DB[("photoalbum-oracle\nOracle Free 23ai\nPort 1521")]
        App -->|"jdbc:oracle:thin"| DB
    end
    Client["Client"] -->|"HTTP :8080"| App
```
