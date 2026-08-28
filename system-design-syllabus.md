# System Design Learning Syllabus

A step-by-step path from fundamentals to full system design interviews.
Check off each item as you complete it.

---

## Stage 1: Foundations (Week 1)

### Topics
- [ ] Client-server model
- [ ] DNS (Domain Name System)
- [ ] HTTP / HTTPS basics
- [ ] TCP vs UDP
- [ ] What happens when you type a URL in a browser

### Practice
- [ ] Build a simple client-server app (basic HTTP server in Python/Node)
- [ ] Trace the full request lifecycle manually (DNS lookup → TCP handshake → HTTP request → response)

---

## Stage 2: Networking & Communication (Week 2)

### Topics
- [ ] REST APIs
- [ ] REST vs GraphQL — practical use-cases for each
- [ ] API Versioning — best practices for evolving APIs
- [ ] Pagination and Filtering — strategies for efficiently fetching data
- [ ] WebSockets
- [ ] gRPC
- [ ] Load balancers (L4 vs L7)
- [ ] Reverse proxies (Nginx, HAProxy)

### Practice
- [ ] Build a REST API with 2-3 endpoints
- [ ] Add pagination and a versioned route (e.g. `/v1/`, `/v2/`) to the API
- [ ] Run 2 instances of the API locally
- [ ] Put Nginx in front as a load balancer

---

## Stage 3: Databases (Weeks 3-4)

### Topics
- [ ] SQL vs NoSQL — know when to use relational vs. NoSQL databases
- [ ] Indexing — primary vs. secondary indexes, covering indexes
- [ ] Normalization
- [ ] Partitioning — vertical vs. horizontal (sharding), and their trade-offs
- [ ] Consistency Models — strong, eventual, causal
- [ ] Replication (master-slave / read replicas)
- [ ] Write Scaling — challenges with partitioning for writes, leader election
- [ ] ACID vs BASE
- [ ] CAP Theorem — consistency, availability, or partition tolerance may be compromised

### Practice
- [ ] Set up a Postgres DB with proper indexing; measure query speed with/without index
- [ ] Set up primary-replica replication locally (Docker); simulate read/write split
- [ ] Manually shard a table (e.g. by user ID range) and query across shards

---

## Stage 4: Caching & Performance (Week 5)

### Topics
- [ ] Client-side vs. Server-side Cache — understand where caching should happen
- [ ] Cache-aside pattern
- [ ] Write-through pattern
- [ ] Write-back pattern
- [ ] Write-around pattern
- [ ] Cache Eviction Policies — LRU, LFU, etc.
- [ ] Redis / Memcached basics
- [ ] Cache invalidation strategies

### Practice
- [ ] Add Redis caching to your Stage 2 API
- [ ] Cache a slow DB query and measure the speedup
- [ ] Implement a simple LRU cache from scratch

---

## Stage 5: Scalability & Reliability (Weeks 6-7)

### Topics
- [ ] Horizontal vs vertical scaling
- [ ] Consistent hashing
- [ ] Message queues (Kafka / RabbitMQ) — queues vs. streams
- [ ] Event-Driven Architecture — decoupling, event sourcing
- [ ] Task Queues — delayed jobs, retries
- [ ] Rate limiting — token bucket, leaky bucket algorithms
- [ ] Redundancy — active-passive vs. active-active configurations
- [ ] Health Checks
- [ ] Retries and Circuit Breakers — protecting against cascading failures

### Practice
- [ ] Implement a rate limiter from scratch (token bucket algorithm)
- [ ] Build a producer-consumer system with RabbitMQ or Kafka
- [ ] Simulate a service failure and implement a circuit breaker around the call

---

## Stage 6: Distributed Systems Concepts (Week 8)

### Topics
- [ ] Consensus Algorithms — Paxos, Raft
- [ ] Conflict Resolution — Last Write Wins (LWW)
- [ ] CRDTs (Conflict-free Replicated Data Types)
- [ ] Vector clocks for data reconciliation

### Practice
- [ ] Walk through a Raft leader-election simulation (diagram or use an existing visualizer)
- [ ] Implement a simple LWW register or counter CRDT

---

## Stage 7: CDNs (Content Delivery Networks) (Week 8)

### Topics
- [ ] Static Content Delivery — why use a CDN, how it works
- [ ] Caching at the Edge — how CDNs improve latency for end users

### Practice
- [ ] Put a static site or asset behind a CDN (e.g. Cloudflare) and measure latency before/after

---

## Stage 8: Search Systems (Week 9)

### Topics
- [ ] Indexing — building and maintaining indexes for fast search
- [ ] Full-Text Search Engines — ElasticSearch, Azure AI Search
- [ ] Ranking and Relevance — how scoring works

### Practice
- [ ] Stand up ElasticSearch locally and index a sample dataset
- [ ] Run full-text queries and compare relevance scoring for different queries

---

## Stage 9: Monitoring, Observability and Security (Week 9)

### Topics
- [ ] Metrics Collection — Prometheus, Grafana
- [ ] Distributed Tracing — OpenTelemetry, Sentry
- [ ] Centralized Logging
- [ ] Authentication and Authorization — OAuth, JWT
- [ ] Encryption — data in transit vs. data at rest

### Practice
- [ ] Add Prometheus + Grafana dashboards to your Stage 2 API
- [ ] Add distributed tracing (OpenTelemetry) across two services
- [ ] Implement JWT-based auth on your API

---

## Stage 10: Full System Design Practice (Weeks 10+)

For each problem below, follow this framework:
1. Clarify requirements
2. Capacity estimation
3. High-level diagram
4. Deep dive on 1-2 bottlenecks

### Problems (in order of difficulty)
- [ ] URL Shortener
- [ ] Rate Limiter (as a distributed service)
- [ ] Pastebin / Google Docs (simplified)
- [ ] Chat App (WhatsApp-style) — WebSockets, message delivery guarantees
- [ ] News Feed (Twitter/Instagram-style) — fan-out strategies
- [ ] Distributed Cache (build your own mini-Redis)
- [ ] Search Autocomplete / Search Engine (indexing + ranking)
- [ ] Ride-sharing / Uber-style — geospatial indexing

---

## Notes
- Don't just read — draw diagrams for every concept.
- Practice explaining designs out loud, interview-style.
- Start simple, then add complexity (single server → +DB → +cache → +load balancer → +sharding).
- Stages 6-9 (distributed systems, CDNs, search, observability) are often skipped by beginners but come up frequently in mid-to-senior interviews — don't skip them just because they feel "extra."