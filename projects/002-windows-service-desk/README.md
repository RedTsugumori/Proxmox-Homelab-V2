# Project 002 — Windows Service Desk Lab

**Status:** In progress — VM created; first boot and operating-system installation not yet verified.

## Objective
Build a personal Windows service desk practice environment and document reproducible troubleshooting exercises, support tickets, and verified results for an entry-level IT portfolio. This is personal lab experience, not professional employment.

## Scope and boundaries
- **VM 110 (LAB-WIN11-01)** is the Windows workstation for this project.
- **VM 102 (Win11-LTSC-RealCraft)** is an independent service and is **out of scope**. Do not modify it.
- The separate Raspberry Pi security lab and planned high-availability project are also out of scope.
- The existing bridge connects to the regular LAN; it is **not isolated**. Do not deploy lab DHCP or potentially disruptive services on this bridge. Design an isolated network before those exercises.

## Host baseline (reported from screenshots)
| Component | Observed configuration |
| --- | --- |
| Hypervisor | Proxmox VE 9.1.1 |
| Processor | AMD Ryzen 7 5700X, 8 cores / 16 threads |
| Memory | 62.72 GiB usable |
| Boot | UEFI with Secure Boot |
| Root filesystem | 93.93 GiB total |
| Swap | 8 GiB |
| SSDs | Samsung 860 EVO (~500 GB); Crucial BX500 (~1 TB) |
| Storage | local, local-lvm, bx500-thin |

Both SSDs displayed SMART **Passed**; observed wear indicators were 16% (Samsung) and 1% (Crucial). These observations do not establish comprehensive drive health. A historical screenshot showed bx500-thin as active and enabled with 980.07 GB total and 36.95 GB used; these are not current measurements. Backup arrangements and repository configuration remain uninvestigated.

## Workstation VM configuration (reported created)
| Setting | Value |
| --- | --- |
| VM ID and name | 110 — LAB-WIN11-01 |
| Machine and firmware | q35; OVMF / UEFI |
| EFI disk | bx500-thin; pre-enrolled keys enabled |
| TPM | v2.0; bx500-thin |
| CPU | 1 socket; 4 cores; host CPU type |
| Memory | 8192 MiB; ballooning disabled |
| Disk | 80 GiB SCSI on bx500-thin; VirtIO SCSI single; discard, SSD emulation and I/O thread enabled; default cache |
| Network | VirtIO on vmbr0; no VLAN specified; VM firewall checkbox enabled |
| QEMU guest agent | Not enabled during VM creation |
| Start at boot | Unchecked |

Windows 11 IoT Enterprise LTSC **evaluation** installation media and VirtIO driver ISO were attached (reported on ide2 and ide0 respectively). Evaluation licensing and expiration must be considered before longer-term use.

## Verified progress and outstanding checks
- **Reported complete:** Proxmox VM creation wizard finished and VM 110 created.
- **Not verified:** First successful boot, Windows Setup, OS installation, guest drivers, user accounts, network configuration, or any support exercise.
- **Not investigated:** Host backups and enterprise subscription/repository notice.

## Next immediate step
Open VM 110's Proxmox console, start the VM, press a key if prompted to boot from installation media, and inspect the first Windows Setup screen. Record the actual observed outcome before proceeding.

## Planned future exercises (not completed)
- Windows Server evaluation VM for Active Directory, test accounts, groups, and shared-folder permissions.
- Ticketing system, potentially hosted on Linux.
- Six support tickets, three troubleshooting articles, a lab diagram, and a detailed case study.
- Initial case: **Employee cannot access a shared folder**.
- Other candidates: account sign-in or lockout, user provisioning, DNS troubleshooting, application failure, and Microsoft web-app sharing using a free account (no assumed Microsoft 365 or tenant admin access).

For each completed case, document symptom, questions, evidence, investigation, fix, verification, and customer-facing closure.

## Learning approach
Work in small steps, explain why settings matter, ask prediction questions with hints, and have the operator perform and verify changes. Avoid repeated quizzes on concepts already demonstrated. Never represent planned work as completed.

## Privacy
Do not commit IP addresses, MAC addresses, host-specific management URLs, serial numbers, credentials, screenshots containing sensitive metadata, or other identifying infrastructure details.
