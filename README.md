# 🏗️ System Design Mastery: Building "Mini-Kafka"

> **Goal:** To transition from "Code User" to "System Architect" by building a distributed, persistent message queue from scratch in Python.
> **Philosophy:** "What I cannot create, I do not understand." - Richard Feynman

---

## 📅 The 5-Month Roadmap

### **Phase 1: The Storage Engine (Single Node)**
*Focus: Disk I/O, Memory Management, Data Structures*
- [ ] **Week 1: The Atomic Log**
    - [ ] Implement `LogManager` class.
    - [ ] Handle `os.fsync()` for durability (WAL - Write Ahead Log).
    - [ ] Build a binary file format (using `struct`).
- [ ] **Week 2: Indexing**
    - [ ] Implement an in-memory Hash Map (Offset -> File Position).
    - [ ] Handle sparse indexing for large logs.
- [ ] **Week 3: The Network**
    - [ ] Wrap the engine in a TCP Server (Socket Programming).
    - [ ] Implement a custom binary protocol (not HTTP/JSON).
- [ ] **Week 4: The Cleanup**
    - [ ] Implement Log Segmentation (Rolling files).
    - [ ] Implement Retention Policy (Delete old segments).

### **Phase 2: The Distributed Cluster**
*Focus: CAP Theorem, Sharding, Replication*
- [ ] **Week 5: The Discovery**
    - [ ] Implement a node registry (Who is alive?).
    - [ ] Implement Heartbeats (UDP/Gossip).
- [ ] **Week 6: Replication (Master-Slave)**
    - [ ] Implement "Leader" vs "Follower" roles.
    - [ ] Replicate writes from Leader to Followers.
- [ ] **Week 7: Consistency**
    - [ ] Handle "Split Brain" scenarios.
    - [ ] Implement Quorum Reads (R + W > N).
- [ ] **Week 8: Sharding**
    - [ ] Implement Consistent Hashing (The Ring).
    - [ ] Route keys to specific nodes.

### **Phase 3: The Intelligence Layer**
*Focus: AI Integration, Optimization*
- [ ] **Week 9: The Observer**
    - [ ] Build a metrics collector (Latency, Throughput).
    - [ ] Integrate a Local LLM (e.g., Llama-3) to analyze logs for anomalies.
- [ ] **Week 10: The Auto-Scaler**
    - [ ] Use AI to predict traffic spikes and trigger "Virtual Scaling".

---

## 🛡️ The Daily Ritual (Accountability)

**Commitment:** 2.5 Hours/Day. No Excuses.

| Time | Activity | Goal |
| :--- | :--- | :--- |
| **0 - 90m** | **The Build** | Coding "Mini-Kafka". (Deep Work) |
| **90 - 135m** | **The Theory** | Reading Internals (DDIA / Papers). |
| **135 - 150m** | **The Scout** | Exploratory Task (AI Trends / Tools). |

---

## 📚 The Library (Resources)
1.  **Book:** *Designing Data-Intensive Applications* (Martin Kleppmann) - The Bible.
2.  **Book:** *CPython Internals* (Anthony Shaw) - The Metal.
3.  **Course:** CMU 15-445/645 (Database Systems) - The Professor.
4.  **Paper:** *The Google File System (GFS)*.
5.  **Paper:** *Kafka: A Distributed Messaging System for Log Processing*.

---

## 🛠️ Project Structure
```text
/system-design-mastery
├── /mini-kafka          # The Source Code
│   ├── storage.py       # Disk I/O Logic
│   ├── network.py       # TCP Server
│   └── cluster.py       # Distributed Logic
├── /daily-logs          # My Accountability Journal
├── /RFCs                # Design Documents (Written BEFORE coding)
└── /tests               # Chaos Engineering Scripts
