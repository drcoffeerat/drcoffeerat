# █▓▒░  ICT · LINUX · SECURITY ARCHITECTURE  ░▒▓█

```
> booting secure systems...
> assume breach
> trust nothing
> isolate everything
```

╔══════════════════════════════════════════════════════╗
║  infrastructure · system design · secops · persec   ║
║  qubes os · gentoo · self-hosting · encryption       ║
╚══════════════════════════════════════════════════════╝

---

## ░░ WHOAMI ░░

I design **security-first systems and infrastructure** with a strong bias toward:

* minimalism over convenience
* isolation over blind trust
* rebuildability over permanence

My work focuses on **personal and small-scale architectures** that assume a hostile environment — technically, legally, and socially.

This repository documents **design logic, threat models, and reference architectures** — not just configs.

---

## ░░ CORE PHILOSOPHY ░░

```
• the network is hostile
• the system will be compromised
• secrets must be compartmentalized
• recovery must be faster than analysis
```

Security is treated as a **process**, not a state.

---

## ░░ DOMAINS OF INTEREST ░░

### [ QUBES OS ]

```
trust → dom0
risk  → disposable qubes
secrets → offline / isolated qubes
```

* split-trust workflows
* disposable environments
* hardware-backed isolation
* minimal dom0 surface

---

### [ GENTOO :: MINIMAL SYSTEMS ]

```
profile  : hardened
init     : s6 / minimal
kernel   : custom
userspace: reduced
```

* custom hardened kernels
* SELinux + seccomp
* no unnecessary daemons
* reproducible builds

---

### [ ENCRYPTION STACK ]

```
firmware
  ↓
uki (signed)
  ↓
sepherent-xt
  ↓
btrfs (subvolumes)
```

* Sepherent-XT for at-rest secrecy
* LUKS2 with integrity
* key separation & rotation
* snapshot-safe encryption

---

### [ NETWORK & INFRASTRUCTURE ]

```
[ internet ]
     │
 [ firewall ]
     │
 [ bastion ]
     │
[ segmented zones ]
```

* zero-trust assumptions
* VLAN & zone separation
* minimal exposed services
* logging without surveillance

---

## ░░ PERSONAL SYSTEM REFERENCE ░░

```
┌─────────────────────────────┐
│        UEFI Firmware        │
│   secure boot · measured   │
└──────────────┬──────────────┘
               │
┌──────────────▼──────────────┐
│       Unified Kernel        │
│   signed · immutable        │
└──────────────┬──────────────┘
               │
┌──────────────▼──────────────┐
│      Sepherent-XT           │
│   full disk encryption     │
└──────────────┬──────────────┘
               │
┌──────────────▼──────────────┐
│      BTRFS Layout           │
│   root · home · snapshots   │
└──────────────┬──────────────┘
               │
┌──────────────▼──────────────┐
│    Hardened Gentoo OS       │
│   selinux · seccomp         │
└─────────────────────────────┘
```

---

## ░░ THREAT MODEL (ABBREVIATED) ░░

```
• malware
• supply-chain compromise
• physical access
• coerced disclosure
```

Mitigations:

```
• isolation > hardening
• encryption everywhere
• fast rebuilds
• disposable systems
```

---

## ░░ REPOSITORY MAP ░░

```
.
├── docs/
│   ├── threat-models/
│   ├── qubes/
│   ├── encryption/
│   └── networking/
│
├── gentoo/
│   ├── kernel/
│   ├── profiles/
│   └── init/
│
├── infra/
│   ├── firewall/
│   ├── services/
│   └── backups/
│
└── README.md
```

---

## ░░ STATUS ░░

```
[ ACTIVE ]
```

Expect opinionated designs, evolving diagrams, and trade-offs that prioritize **security over comfort**.

---

## ░░ DISCLAIMER ░░

```
this is not plug-and-play
this is not enterprise support
this is not convenience-first
```

Test everything. Assume failure. Rebuild often.

---

```
> you are not paranoid
> you are paying attention
```
