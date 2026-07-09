# RaftKV
*A fault-tolerant distributed key-value store built from scratch in Java using the Raft Consensus Algorithm.*

> **Status:** 🚧 In Development

---

## Overview

Modern distributed systems need to remain available even when machines fail, networks partition, or messages are delayed. One of the fundamental problems behind this is **distributed consensus**—how multiple machines agree on a single sequence of operations while remaining consistent.

This project is my attempt to understand that problem from first principles by implementing a distributed key-value store based on the **Raft Consensus Algorithm**.

Rather than relying on existing distributed frameworks, the goal is to build every core component myself, understand why it exists, and document the engineering decisions made throughout the process.

---

## Project Goals

The primary objectives of this project are:

- Implement the Raft consensus algorithm from scratch
- Build a replicated distributed log
- Support automatic leader election
- Implement fault-tolerant log replication
- Guarantee consistency using majority consensus
- Expose a client-facing API for interacting with the cluster
- Simulate node failures and recovery
- Gain a deep understanding of distributed systems, concurrency, networking, and synchronization

---

## Why This Project?

Consensus algorithms are the backbone of systems like:

- etcd
- Consul
- CockroachDB
- TiKV
- Kubernetes Control Plane
- Apache Kafka (earlier versions via ZooKeeper)

Building one from scratch provides practical exposure to concepts that appear frequently in backend engineering, distributed systems, and systems design interviews.

This repository is intended to be both a learning resource and an engineering portfolio project.

---

# Planned Architecture

```
                  Client
                     │
                     ▼
             REST / TCP API
                     │
        ┌────────────┴────────────┐
        │                         │
        ▼                         ▼
   Leader Node              Follower Nodes
        │                         │
        ├────────────┬────────────┤
        ▼            ▼            ▼
      Replicated Raft Log (Consensus)
                     │
                     ▼
              Key-Value State Machine
```

---

# Features Roadmap

## Phase 1 — Understanding Raft

- [ ] Read the Raft paper
- [ ] Study MIT 6.824 lectures
- [ ] Design project architecture

---

## Phase 2 — Core Raft

- [ ] Server states
    - [ ] Follower
    - [ ] Candidate
    - [ ] Leader

- [ ] Persistent state
- [ ] Volatile state

- [ ] Leader Election
- [ ] Heartbeats
- [ ] RequestVote RPC
- [ ] AppendEntries RPC

---

## Phase 3 — Log Replication

- [ ] Log entries
- [ ] Log consistency
- [ ] Commit Index
- [ ] Match Index
- [ ] Next Index
- [ ] Majority Commit

---

## Phase 4 — Distributed KV Store

- [ ] PUT operation
- [ ] GET operation
- [ ] DELETE operation
- [ ] Apply committed entries
- [ ] State machine execution

---

## Phase 5 — Networking

- [ ] Node-to-node communication
- [ ] Client communication
- [ ] Request serialization
- [ ] Cluster discovery

---

## Phase 6 — Fault Tolerance

- [ ] Node crashes
- [ ] Leader failover
- [ ] Network partitions (simulation)
- [ ] Recovery after restart

---

## Future Work

After completing the core implementation, I plan to explore:

- Snapshotting
- Log compaction
- Dynamic cluster membership
- Persistent storage
- Performance optimizations
- Metrics & monitoring
- Docker deployment
- Kubernetes deployment

---

# Tech Stack

- Java
- Maven
- Java Concurrency
- TCP/HTTP Networking
- JUnit
- Git & GitHub

Future additions may include:

- Spring Boot (API layer)
- Docker
- Kubernetes
- Prometheus
- Grafana

---

# Learning Objectives

This project is primarily about understanding:

- Distributed Systems
- Consensus Algorithms
- Fault Tolerance
- Leader Election
- Replicated Logs
- Concurrency
- Synchronization
- RPC Communication
- State Machines
- Event-driven Systems

---

# References

- Diego Ongaro, *In Search of an Understandable Consensus Algorithm*
- MIT 6.824 Distributed Systems
- Designing Data-Intensive Applications — Martin Kleppmann

---

# Repository Progress

| Component | Status |
|-----------|--------|
| Research | 🚧 In Progress |
| Architecture | ⏳ Planned |
| Leader Election | ⏳ Planned |
| Log Replication | ⏳ Planned |
| KV Store | ⏳ Planned |
| Fault Recovery | ⏳ Planned |

---

# Project Philosophy

This repository is not intended to be a copy of an existing implementation.

Every major component will be implemented incrementally, documented, tested, and accompanied by notes explaining both *how* it works and *why* it exists.

The objective is to build intuition for distributed systems—not just produce working code.

---