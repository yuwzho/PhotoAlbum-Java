# Upgrade Progress

  ### ✅ Generate Upgrade Plan
  - [[View Log]](logs\1.generatePlan.log)

  ### ✅ Confirm Upgrade Plan
  - [[View Log]](logs\2.confirmPlan.log)

  ### ✅ Setup Development Environment
  - [[View Log]](logs\3.setupEnvironment.log)

  ### ✅ PreCheck
  - [[View Log]](logs\4.precheck.log)
  
  <details>
      <summary>[ click to toggle details ]</summary>
  
  - ###
    ### ✅ Precheck - Build project
    - [[View Log]](logs\4.1.precheck-buildProject.log)
    
    <details>
        <summary>[ click to toggle details ]</summary>
    
    #### Command
    `mvn clean test-compile -q -B -fn`
    </details>
  
    ### ✅ Precheck - Validate CVEs
    - [[View Log]](logs\4.2.precheck-validateCves.log)
    
    <details>
        <summary>[ click to toggle details ]</summary>
    
    #### CVE issues
    - Dependency `commons-io:commons-io:2.11.0` has **1** known CVEs:
      - [CVE-2024-47554](https://github.com/advisories/GHSA-78wr-2p64-hpwj): Apache Commons IO: Possible denial of service attack on untrusted input to XmlStreamReader
        - **Severity**: **HIGH**
        - **Details**: Uncontrolled Resource Consumption vulnerability in Apache Commons IO.
          
          The `org.apache.commons.io.input.XmlStreamReader` class may excessively consume CPU resources when processing maliciously crafted input.
          
          
          This issue affects Apache Commons IO: from 2.0 before 2.14.0.
          
          Users are recommended to upgrade to version 2.14.0 or later, which fixes the issue.
    - Dependency `com.h2database:h2:2.1.214` has **1** known CVEs:
      - [CVE-2022-45868](https://github.com/advisories/GHSA-22wj-vf5f-wrvj): Password exposure in H2 Database 
        - **Severity**: **HIGH**
        - **Details**: The web-based admin console in H2 Database Engine through 2.1.214 can be started via the CLI with the argument -webAdminPassword, which allows the user to specify the password in cleartext for the web admin console. Consequently, a local user (or an attacker that has obtained local access through some means) would be able to discover the password by listing processes and their arguments. NOTE: the vendor states "This is not a vulnerability of H2 Console ... Passwords should never be passed on the command line and every qualified DBA or system administrator is expected to know that."
    </details>
  
    ### ✅ Precheck - Run tests
    - [[View Log]](logs\4.3.precheck-runTests.log)
    
    <details>
        <summary>[ click to toggle details ]</summary>
    
    #### Test result
    | Total | Passed | Failed | Skipped | Errors |
    |-------|--------|--------|---------|--------|
    | 1 | 1 | 0 | 0 | 0 |
    </details>
  </details>

  ### ✅ Upgrade project to use `Java 21`
  
  
  <details>
      <summary>[ click to toggle details ]</summary>
  
  - ###
    ### ✅ Upgrade using Agent
    - [[View Log]](logs\5.1.upgradeProjectUsingAgent.log)
    
    - 4 files changed, 9 insertions(+), 9 deletions(-)
    
    <details>
        <summary>[ click to toggle details ]</summary>
    
    #### Code changes
    - Upgrade Java version from 8 to 21
      - Update pom.xml java.version, maven.compiler.source, and maven.compiler.target to 21
    - Modernize code syntax for Java 21
      - Replace !Optional.isPresent() with Optional.isEmpty() in DetailController, PhotoFileController, and PhotoServiceImpl
      - Replace String.format() with String.formatted() in PhotoServiceImpl
      - Replace List.get(0) with List.getFirst() in PhotoServiceImpl
    </details>
  
    ### ✅ Build Project
    - [[View Log]](logs\5.2.buildProject.log)
    
    - Build result: 100% Java files compiled
    
    <details>
        <summary>[ click to toggle details ]</summary>
    
    #### Command
    `mvn clean test-compile -q -B -fn`
    </details>
  </details>

  ### ⏳ Validate & Fix ...Running
  
  
  - ###
    ### ✅ Validate CVEs
    - [[View Log]](logs\6.1.validateCves.log)
    
    <details>
        <summary>[ click to toggle details ]</summary>
    
    #### Checked Dependencies
      - java:*:21
    </details>
  
    ### ⏳ Validate And Fix Code Behavior Changes ...Running