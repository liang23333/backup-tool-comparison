# Backup and Disaster Recovery Tool Comparison

A comprehensive comparison and reliability evaluation of open-source backup and disaster recovery solutions for business infrastructure.

## Evaluated Tools

- **[Restic](https://github.com/restic/restic)**: Fast, secure, multi-cloud backup program (Go).
- **[BorgBackup](https://github.com/borgbackup/borg)**: Deduplicating archiver with compression and encryption (Python/C).
- **[Velero](https://github.com/velero-io/velero)**: Kubernetes cluster disaster recovery and volume migration (Go).
- **[Duplicati](https://github.com/duplicati/duplicati)**: Web UI client for cloud backups (C# / .NET).
- **[Kopia](https://github.com/kopia/kopia)**: Modern cross-platform deduplicating backup engine with repository server mode (Go).

## Full Analysis

👉 **Read the complete evaluation report: [COMPARISON.md](COMPARISON.md)**

### Key Highlights

- **Safest General-Purpose Tool:** **Restic** (Zero database corruption risk, direct S3/B2 support, append-only ransomware protection via `rest-server` or S3 Object Lock).
- **Best for Dedicated Linux/SSH Infrastructure:** **BorgBackup 1.4** (with Borgmatic). *Warning: Avoid Borg 2.0 beta for production workloads.*
- **Best for Kubernetes / Containers:** **Velero** (CSI volume snapshots and cluster state migration).
- **High Risk / Not Recommended for Business DR:** **Duplicati** (Due to recurrent SQLite database locking, out-of-sync states, and recreation failures during disaster recovery).
