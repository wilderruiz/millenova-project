# What is published here

This repository is the **public engineering, architecture, experiments, and development record for Millenova**.

It is intentionally separate from the private implementation repository:

- **Private implementation authority:** `wilderruiz/millenova`
- **Public engineering/publication authority:** `wilderruiz/millenova-project`

The public repository is not an automatic mirror of the private source tree. Material is reviewed, rewritten where necessary, and published deliberately.

## Core rule

> **Architecture is public. Exploitable configuration is private.**

Millenova's architecture, engineering decisions, state models, subsystem responsibilities, performance constraints, failure analysis, experiments, and development history may be documented here in substantial technical detail.

The publication boundary is security, privacy, and operational safety — not an attempt to hide how the system works.

## What may be published

Subject to review, this repository may include:

- platform architecture diagrams;
- subsystem and module responsibilities;
- logical service relationships;
- control-plane and data-plane models;
- media lifecycle and rendition models;
- native-player and queue semantics;
- feed virtualization and scroll-governor models;
- search/discovery design;
- creator Studio and upload workflows;
- moderation and governance design;
- distributed-media-provider design;
- HOME_MEDIA / VPS_MEDIA logical provider concepts;
- replication, integrity, failover, recovery, and health-check concepts;
- public-safe database/entity models;
- state machines;
- API concepts and capability boundaries at a level safe for publication;
- technology choices and trade-offs;
- benchmarks and performance findings after review;
- failure reports and rejected approaches;
- production lessons that do not expose exploitable details;
- implementation-plan summaries;
- screenshots with sensitive information removed;
- engineering logs;
- public milestones;
- selected code excerpts when explicitly reviewed and safe to publish;
- educational write-ups explaining how and why a system was engineered.

## What must remain private

Do not publish:

- passwords, access tokens, API keys, signing keys, cookies, session material, SSH private keys, or credentials of any kind;
- production environment files or real secret-bearing configuration;
- exact private IP addresses, private hostnames, private tunnel endpoints, or security-sensitive network coordinates;
- unrestricted production filesystem paths;
- exact firewall rules where publication would weaken security;
- SSH commands/configuration when they expose operational access details;
- database passwords, connection strings, secret schema data, or personal records;
- private user data, moderation evidence, reports, account identifiers, or personal information;
- OAuth client secrets or other provider secrets;
- capability-signing secrets or token-generation secrets;
- security implementation details whose publication materially lowers the cost of attacking the live platform;
- abuse-prevention thresholds or bypass details where disclosure would help evade controls;
- internal administrative credentials or privileged endpoints that should not be discoverable publicly;
- unreleased third-party confidential material;
- copyrighted media files that are not cleared for public repository distribution;
- local-machine personal paths, usernames, or machine-specific data unless explicitly sanitized and useful.

## Architecture publication rule

Architecture itself is not considered secret merely because it is complex.

Public documentation may show, for example:

```text
Browser / client
      ↓
Millenova application
      ↓
media identity + policy
      ↓
provider routing
   ┌──┴───────────┐
   ↓              ↓
HOME_MEDIA     VPS_MEDIA
preferred      fallback
```

It may explain that provider health, integrity state, replication, playback authorization, and fallback exist.

It should **not** expose the production address, credential, private port mapping, exact SSH access command, signing secret, or other operational detail that turns an architectural explanation into an attack aid.

## Public-safe code rule

Code may be published only when one of these conditions is true:

1. it already exists in a public repository;
2. it is a deliberately created educational example that does not expose private implementation;
3. it is a reviewed excerpt whose publication does not weaken production security, disclose secrets, or reveal private data;
4. Wilder Ruiz explicitly approves it for publication.

When a diagram or explanation is sufficient, prefer that over copying private production code.

## Public-safe security rule

Security engineering may be discussed at the level of principles and boundaries, for example:

- short-lived capability authorization;
- server-owned authority decisions;
- scoped access;
- integrity verification;
- least privilege;
- health-aware failover;
- bounded retries;
- explicit ownership boundaries;
- moderation and abuse-control layers.

Do not publish enough operational detail to provide a practical bypass or intrusion recipe.

## Public-safe infrastructure rule

Infrastructure experiments are welcome here because they are part of Millenova's engineering story.

Examples include the Distributed Media Node work, where a privately owned home media node can contribute storage/processing capacity while a VPS remains an independent fallback.

Public documentation may explain:

- why the experiment exists;
- logical provider roles;
- control plane vs data plane;
- replication semantics;
- failover and recovery;
- checksums and replica state;
- bandwidth/storage economics;
- future CDN/edge evolution;
- measured outcomes.

Do not publish production access credentials, secret tunnel configuration, private network coordinates, or exact security-sensitive deployment commands.

## Public/private authority

If the public repository and the private implementation differ:

- the **private repository** is authoritative for current implementation behavior;
- the **public repository** is authoritative for what has been deliberately published;
- differences may be intentional;
- never automatically synchronize private implementation into this repository.

## Review-first workflow

Every substantial new public document follows this sequence:

```text
private implementation / current evidence
              ↓
agent research + public-safe draft
              ↓
Wilder review
              ↓
correction / clarification
              ↓
Wilder approval
              ↓
mark implementation-plan step complete
              ↓
move to next public document
```

A document is not considered complete merely because an agent created it.

## Agent rules

Agents working on this repository must:

1. read this file before drafting or modifying public technical documentation;
2. read `MILLENOVA_PUBLIC_FACADE_IMPLEMENTATION_PLAN.md` before starting a planned publication step;
3. use the private `wilderruiz/millenova` repository only as the factual source for current engineering reality;
4. distinguish implemented behavior from planned, experimental, queued, rejected, or superseded work;
5. preserve dates/status when they materially establish engineering history;
6. never infer that a private implementation detail is safe to publish merely because it is technically interesting;
7. prefer architecture, state models, diagrams, tables, measured outcomes, and engineering rationale over raw private source;
8. stop and flag anything that may contain credentials, sensitive production details, private user data, or exploitable security information;
9. avoid marketing exaggeration and unsupported claims;
10. wait for Wilder's review/approval before marking a planned publication step complete.

## ZGitPet and multi-project development

This public repository is maintained alongside multiple active private and public projects.

**ZGitPet** is used as a development accelerator and repository guardian to reduce context switching while working across those projects. It helps surface repository state, incoming/outgoing changes, review boundaries, project switching, and deliberate publication workflows.

ZGitPet does not change the publication rule:

> **Speed up the workflow, never bypass review.**

Public Millenova documentation remains deliberate even when local and remote agents, GitHub, and multiple repositories are being used concurrently.

## Publication principle

The goal of this repository is to make Millenova unusually educational and technically transparent while keeping the live system secure.

The guiding rule is:

> **Show the engineering. Protect the secrets. Review before release.**
