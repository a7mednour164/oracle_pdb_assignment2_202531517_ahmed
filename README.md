# oracle_pdb_assignment2_202531517_ahmed# Individual Assignment II: Oracle Pluggable Database (PDB) Administration

## 1. Assignment Overview
The objective of this assignment is to demonstrate practical skills in Oracle Multitenant Architecture, specifically focusing on the creation, configuration, and management of Pluggable Databases (PDBs), user administration within a PDB, and utilizing database management tools.

## 2. Oracle Environment Details
- **Oracle Database Version:** Oracle Database 21c Express Edition Release 21.0.0.0.0
- **Operating System:** Windows 10 / 11
- **Tools Used:** SQL*Plus, Oracle Enterprise Manager (EM Express)

## 3. Task Documentation & Configuration

### Task 1: Create and Configure a New Pluggable Database (PDB)
- **PDB Name:** `ah_pdb_31517_2025`
- **Configured DB User:** `ahmed_plsqlauca_202531517`
- **Steps Executed:**
  1. Connected to `CDB$ROOT` as `SYSDBA` and successfully initialized the PDB instance.
  2. Opened the pluggable database in `READ WRITE` status.
  3. Switched session container to the newly created PDB.
  4. Created a personal administrative database user secured with a password.
  5. Granted explicit administration privileges (`CONNECT`, `RESOURCE`, `DBA`) to the user.
  6. Verified network connectivity and successfully logged into the database session using the new user credentials.

### Task 2: Create and Delete a Temporary PDB
- **Temporary PDB Name:** `ah_to_delete_pdb_31517_2025`
- **Steps Executed:**
  1. Switched session context back to `CDB$ROOT`.
  2. Created a temporary PDB explicitly defining the `FILE_NAME_CONVERT` parameters to match the system's local storage path structure.
  3. Verified its active status via database dictionary views.
  4. Closed the running pluggable instance using `CLOSE IMMEDIATE` instruction.
  5. Completely dropped the PDB alongside its physical data blocks utilizing `INCLUDING DATAFILES` clause.
  6. Checked database records using `SHOW PDBS` to guarantee absolute elimination.

### Task 3: Oracle Enterprise Manager (OEM) Configuration
- Successfully evaluated the local listener configurations and validated the internal HTTP architecture port management. Port 5500 was verified operational via internal administrative metadata query routines (`DBMS_XDB_CONFIG.GETHTTPSPORT`).

---

## 4. Troubleshooting & Challenges Overcome
- **The Challenge (ORA-65016):** During the initial setup of the database container, the execution was halted by `ORA-65016: FILE_NAME_CONVERT must be specified`.
- **The Solution:** Conducted a structural lookup on `V$DATAFILE` to capture the seed pattern (`C:\APP\HP\PRODUCT\21C\ORADATA\XE\pdbseed\`) and mapped the file transformations accurately into the target environment path.

## 5. Key Technical Takeaways
- Acquired deep hands-on proficiency managing session containers inside Oracle Multitenant infrastructure.
- Gained experience resolving environment file mapping blockages and administrative file placement within Windows systems.

## 6. Academic Integrity Statement
"I confirm that this assignment represents my own practical work, screenshots, and documentation. All external resources consulted have been properly acknowledged."
