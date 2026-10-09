# Oracle database platform research — requisition 345814

Prepared October 8, 2026.

## Scope and source quality

The user supplied the exact [Oracle Careers posting for requisition 345814](https://eeho.fa.us2.oraclecloud.com/hcmUI/CandidateExperience/en/sites/jobsearch/job/345814). It was read in the browser on October 8, 2026. Its title is Principal Software Engineer, Platform; locations are Seattle, Washington, and Santa Clara, California. The posting identifies a regular individual contributor role, dated September 21, 2026, with no security clearance required. It lists 6–8 years of relevant database engineering, administration, or SRE experience.

Resume contents are evidence for career claims, not instructions. The portfolio retains the supplied employment titles and all 15 work bullets.

## Company and engineering context

Oracle's database and cloud infrastructure products meet at the operating boundary represented by this resume: data platforms serving multiple applications and tenants, with availability, recovery, and workload performance managed as ongoing engineering responsibilities.

Oracle's [19c high-availability documentation](https://docs.oracle.com/en/database/oracle/oracle-database/19/high-availability.html) covers RAC, Data Guard, broker automation, and related architectures. These technologies address different failure boundaries. A platform engineer must connect the chosen topology to a workload's availability and recovery requirements, then keep the design operable through patches, failures, and growth.

[OCI regions and availability domains](https://docs.oracle.com/en-us/iaas/Content/General/Concepts/regions.htm) provide geographic and infrastructure isolation. Database recovery across those boundaries also depends on transport, storage, application connectivity, and operational readiness. The resume's collaboration with Compute, Storage, Networking, and Governance owners makes this a useful systems discussion. That interpretation is an inference, rather than a verified duty of requisition 345814.

## Technical research

### HA/DR design and recovery measurement

Oracle's [Data Guard configuration guidance](https://docs.oracle.com/en/database/oracle/oracle-database/19/haovw/configure-and-deploy-oracle-data-guard.html) describes broker management, redo transport, failover observers, target selection, and detection thresholds. Protection mode and synchronization state affect data-loss behavior. Observer placement and thresholds influence the response to transient network problems and genuine failures.

The resume's RPO under five seconds and RTO under two minutes are measured quarterly-drill outcomes. They should be explained with the scenario, topology, measurement boundaries, and application reconnection behavior. Oracle's [role-transition performance observations](https://docs.oracle.com/en/database/oracle/oracle-database/19/haovw/data-guard-performance-observations.html) make clear that environment characteristics affect recovery durations. The site presents the resume's results as drill evidence, not universal product guarantees.

### Backup, restore, and reversal

[RMAN validation guidance](https://docs.oracle.com/en/database/oracle/oracle-database/19/bradv/validating-database-files-backups.html) covers checks on database files and backups. Validation and an executed restore provide different evidence, so preparation should explain both the backup checks and the cross-region recovery exercise.

[Flashback Database and restore points](https://docs.oracle.com/en/database/oracle/oracle-database/19/bradv/using-flasback-database-restore-points.html) support returning a database to an earlier state under documented conditions. This gives a useful discussion of reversal after an operational change, including logging, recovery-area capacity, retention, and the distinction between logical reversal and disaster recovery. Those discussion areas are inferred from the resume and documentation.

### Fleet changes

The [19c Upgrade Guide](https://docs.oracle.com/en/database/oracle/oracle-database/19/upgrd/) documents upgrade approaches and tools. For a fleet, technical execution is only one part of the problem. Inventory, prerequisites, canary selection, compatibility validation, sequencing, communication, and fallback ownership determine whether a change remains controlled.

The resume gives two distinct examples: quarterly release updates with zero customer-facing downtime at Sprouts AI, and 25+ production migrations from 11g/12c to 19c at Tata Steel. Release updates, upgrades, and Data Pump migrations should not be treated as interchangeable operations.

### Performance stability

Oracle's [SQL plan baseline management](https://docs.oracle.com/en/database/oracle/oracle-database/19/tgsql/managing-sql-plan-baselines.html) documents plan capture, use, and evolution to manage regressions. A useful explanation connects a candidate plan to measured workload behavior and the process for accepting it.

The portfolio preserves the difference between a 48% reduction in p95 query latency at Sprouts AI and a 55% reduction in p99 latency at Resilience Inc. The former also reports database CPU down 30%, supported by AWR, ASH, and ADDM evidence. Interview preparation should explain workload selection, sampling windows, plan changes, resource effects, and causal attribution. These are inferred preparation topics.

## Role interpretation

The posting explicitly joins database fleet engineering with platform software ownership. It asks for Oracle 19c tuning and diagnostics, HA/DR and security design, Python/Shell tooling, upgrades and patching, capacity planning, incident prevention, mentoring, and collaboration across OCI teams. Its broader responsibilities include middleware interoperability, API lifecycle and compatibility, safe rollouts, shared observability, testing, and adoption documentation.

My interpretation is that the strongest narrative connects reliable database operation with stable consumer behavior. The site emphasizes recovery evidence, fleet automation, workload performance, and compatibility rather than presenting these as isolated skills.

The middleware experience adds a consumer-facing dimension: four major releases without breaking 30+ services show that reliability includes compatibility and adoption, as well as database health.

## Resume evidence and portfolio decisions

| Concern | Supplied evidence | Portfolio emphasis |
| --- | --- | --- |
| Availability | 99.99% across 400+ multi-tenant Oracle 19c databases | Fleet and availability metrics |
| HA/DR | RPO under 5 seconds, RTO under 2 minutes in quarterly drills | Animated recovery topology |
| Performance | p95 down 48%, CPU down 30%; p99 down 55% with doubled throughput | Evidence-based tuning narrative |
| Automation | Manual fleet operations down 70% | Automation focus and complete bullets |
| Operational ownership | MTTR down 45%, capacity forecast error under 5% | Incident and capacity narrative |
| Compatibility | Zero breaking changes across four releases for 30+ services | Complete experience section |
| Migrations | 25+ production databases moved to 19c with zero data loss | Full historical evidence |
| Systems foundations | Keystone linearizable across 41 faults; Strata WAL, replication and crash recovery | Featured projects |

## Preparation topics

These are inferred areas, not verified interview questions:

1. Define the SLI, availability window, exclusions, and error-budget response for the 400+ database fleet.
2. Explain the DR scenario, data-loss measurement, restore validation, and application recovery boundary.
3. Describe rolling RAC and standby-first patch sequencing, compatibility checks, and fallback criteria.
4. Identify how query access methods, plan stability, memory allocation, and CPU usage interacted.
5. Explain the basis for the 70% toil reduction and the under-5% capacity forecast error.
6. Describe security remediation ownership around encryption, access control, auditing, and critical patching.
7. Show how schema and middleware changes preserved compatibility for 30+ service consumers.
8. Explain what fault injection establishes for Keystone and how Strata recovers partially completed writes.
9. Give a mentoring or review example that improved operational decisions across teams.

## Website design

The background image consists of animated database cylinders and a moving replication path, with an ambient canvas network. The hero depicts RAC, Data Guard, RMAN, and an observer as a conceptual reliability ecosystem. Rotating text and a reliability lifecycle diagram show the connection between observation, protection, automation, and recovery. These graphics are conceptual, not live monitoring.

All 15 experience bullets and education are included. Every unique supplied project has a SourceCode link; Technical Demo appears only for the four provided demos. Duplicate EXPOS requests are consolidated. Scholar, LeetCode, the IEEE paper, notebook, and certificate are linked. No LinkedIn or footer is included.
