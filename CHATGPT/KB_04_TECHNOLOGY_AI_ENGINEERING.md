# KNOWLEDGE BASE 04
# TECHNOLOGY, AI, COMPUTING, SOFTWARE, HARDWARE, ENGINEERING, ROBOTICS
# XURMATILLO Universal Cognitive Operating System

================================================================

## PART 1 — COMPUTER SCIENCE FOUNDATIONS

### 1.1 What computers actually do
A computer is a finite state machine that transforms input bits into output bits according to a program. Every higher abstraction — operating systems, programming languages, AI models, the cloud — eventually reduces to this.

The foundational levels:
- Physical layer: transistors, gates, voltages.
- Logic layer: AND, OR, NOT, XOR; combinational and sequential circuits.
- Architecture layer: CPU, registers, memory, buses, instruction set.
- System layer: kernel, processes, file system, network stack.
- Language layer: assembly, compiled languages, interpreted languages, runtimes.
- Application layer: programs that solve real problems.

### 1.2 Computational complexity
Algorithms are compared by how their resource usage grows with input size:
- O(1) — constant. Best.
- O(log n) — logarithmic. Excellent.
- O(n) — linear. Good.
- O(n log n) — linearithmic. Standard for sorting.
- O(n²) — quadratic. Acceptable for small inputs only.
- O(2ⁿ) — exponential. Intractable for large inputs.
- O(n!) — factorial. Tractable only for tiny inputs.

P vs NP: the question of whether problems whose solutions can be verified quickly can also be solved quickly. Unresolved. Most cryptography depends on the conjecture P ≠ NP.

### 1.3 Data structures
- Array — contiguous memory, O(1) access by index, O(n) insertion in middle.
- Linked list — non-contiguous, O(n) access, O(1) insertion when position is known.
- Stack — LIFO, useful for recursion and undo.
- Queue — FIFO, useful for scheduling and BFS.
- Hash table — O(1) average lookup, O(n) worst case, requires good hash function.
- Tree — hierarchical; binary search trees give O(log n) operations when balanced.
- Heap — priority queue, O(log n) insert and extract-min/max.
- Graph — vertices and edges, models networks, social structures, dependencies.
- Trie — prefix tree, useful for autocomplete and dictionaries.
- Bloom filter — probabilistic set membership, no false negatives, controlled false positives, very memory efficient.

### 1.4 Algorithms
Classical algorithms every engineer should know:
- Sorting: quicksort, mergesort, heapsort, insertion sort. Average and worst-case behavior matters.
- Searching: binary search (sorted), hash table lookup, BFS, DFS.
- Shortest path: Dijkstra (non-negative weights), Bellman-Ford (negative weights), Floyd-Warshall (all pairs).
- Minimum spanning tree: Kruskal, Prim.
- Dynamic programming: optimal substructure plus overlapping subproblems → memoization or tabulation.
- Greedy algorithms: locally optimal choices; only correct when the problem has greedy-choice property.
- Divide and conquer: split, solve recursively, combine.
- Backtracking: enumerate possibilities, prune branches that cannot succeed.
- Randomized algorithms: use randomness to achieve average-case performance better than deterministic worst case.

### 1.5 Theory of computation
- Regular languages — recognized by finite automata; equivalent to regular expressions.
- Context-free languages — recognized by pushdown automata; basis for most programming language parsers.
- Turing machines — model of general computation. The Church-Turing thesis claims they capture the full notion of "computable."
- Halting problem — undecidable. There is no general algorithm to decide whether an arbitrary program halts.
- Decidable, recognizable, and unrecognizable languages form a strict hierarchy.

---

## PART 2 — PROGRAMMING

### 2.1 Programming paradigms
- Imperative: describe how to compute. C, Pascal.
- Object-oriented: organize state and behavior into objects. Java, C++, Python (multi-paradigm).
- Functional: treat computation as evaluation of mathematical functions, avoid mutable state. Haskell, Erlang, Lisp dialects.
- Declarative: describe what to compute, not how. SQL, Prolog.
- Concurrent: structure programs around independent execution paths. Go, Erlang, Rust.

Most modern languages are multi-paradigm. The skilled programmer chooses the paradigm appropriate to the subproblem.

### 2.2 Major languages and their domains

**Python**
General-purpose, batteries included. Dominant in data science, AI/ML, automation, scripting, scientific computing, education. Slow at raw computation, fast through C-extensions (NumPy, Pandas) and by being fast to write. Use type hints in production code.

**JavaScript / TypeScript**
The language of the web. Runs in every browser. Node.js extends to server-side. TypeScript adds static types and is now the recommended choice for any non-trivial JS project. Massive ecosystem (npm); massive churn.

**C**
Close to the metal. Operating systems, embedded systems, performance-critical libraries. Manual memory management. Foundation that almost every other system builds on.

**C++**
Adds object orientation, generics, RAII, modern features. Game engines, browsers, financial systems, robotics. Steeper learning curve. Modern C++ (17/20/23) is significantly better than legacy code.

**Rust**
Memory safety without garbage collection through ownership and borrowing. Steep initial learning curve, then highly productive. Systems programming, embedded, web servers, blockchain. Increasingly chosen for new infrastructure where safety and performance both matter.

**Go**
Designed at Google for concurrent server-side systems. Simple syntax, fast compilation, garbage collected, excellent standard library, goroutines for concurrency. Cloud-native infrastructure (Docker, Kubernetes) is largely Go.

**Java / Kotlin**
JVM-based. Java for legacy enterprise, Android (legacy). Kotlin for modern Android and increasingly server-side. Strong type system, large ecosystem (Spring, etc.).

**Swift**
Apple platforms. Modern, type-safe, expressive. iOS, macOS, watchOS, tvOS development.

**SQL**
Domain-specific language for relational databases. Indispensable for any backend developer. Variants exist (PostgreSQL extensions, MySQL flavor, T-SQL) but core is portable.

**Bash / Shell**
Glue language for system automation. Often the fastest way to chain Unix tools. Quirky syntax — quote everything, beware of word splitting.

### 2.3 Software design principles

**SOLID**
- Single Responsibility — a class should have one reason to change.
- Open/Closed — open for extension, closed for modification.
- Liskov Substitution — subtypes must be substitutable for their base types.
- Interface Segregation — clients should not depend on interfaces they don't use.
- Dependency Inversion — depend on abstractions, not concretions.

**DRY** — Don't Repeat Yourself. Knowledge should have a single representation.

**KISS** — Keep It Simple. Complexity is the enemy.

**YAGNI** — You Ain't Gonna Need It. Don't build for imagined future requirements.

**Separation of concerns** — different aspects of a system handled by different modules.

**Composition over inheritance** — prefer combining small pieces over deep hierarchies. Inheritance creates tight coupling that becomes painful at scale.

### 2.4 Design patterns
The Gang of Four classics:

**Creational**: Factory, Abstract Factory, Builder, Prototype, Singleton.
**Structural**: Adapter, Bridge, Composite, Decorator, Facade, Flyweight, Proxy.
**Behavioral**: Chain of Responsibility, Command, Iterator, Mediator, Memento, Observer, State, Strategy, Template Method, Visitor.

Patterns are vocabulary, not commandments. Apply when they solve a real problem; avoid when they over-engineer a simple one.

### 2.5 Modern application architecture
- Monolith — one deployable. Simple to start, hard to scale.
- Microservices — many small services. Independent deployment and scaling, operational complexity.
- Serverless — functions run in response to events, no server management. Cost-effective for spiky loads, painful for long-running stateful processes.
- Event-driven — components communicate through events. Decoupling, eventual consistency challenges.

The right architecture depends on team size, scale, and how clearly the domain decomposes. Premature microservices kill more startups than monoliths do.

### 2.6 Testing
- Unit tests — small, fast, isolated. Should run in seconds.
- Integration tests — verify components together.
- End-to-end tests — verify the system from user perspective.
- Test pyramid — many unit tests, fewer integration, even fewer e2e.
- Test-driven development — write the test first, then the code. Forces clear specification.
- Coverage is a sanity check, not a target. 100% coverage of trivial code with no tests on edge cases is worse than focused testing.
- Property-based testing (QuickCheck, Hypothesis) finds bugs that example-based testing misses.

### 2.7 Version control
Git basics: commit, branch, merge, rebase, push, pull.
Workflow models: trunk-based (continuous integration into main), Gitflow (long-lived feature branches — falling out of fashion), GitHub flow (short-lived branches plus PRs).
Best practices: small commits, meaningful messages, never rewrite shared history, code review before merge, automated CI on every PR.

---

## PART 3 — ARTIFICIAL INTELLIGENCE

### 3.1 The history that matters
- 1950: Turing's "Computing Machinery and Intelligence" — the imitation game.
- 1956: Dartmouth conference. Term "artificial intelligence" coined.
- 1957–1960s: early symbolic AI, Logic Theorist, General Problem Solver.
- 1966: ELIZA shows superficial conversation can fool people.
- 1970s–80s: AI winter cycles. Symbolic AI hits practical limits.
- 1980s–90s: expert systems, neural networks revival, Bayesian methods.
- 1997: Deep Blue beats Kasparov at chess.
- 2006: Hinton's deep learning paper. Beginning of the modern era.
- 2012: AlexNet wins ImageNet by huge margin. Deep learning takes over computer vision.
- 2014: GANs (Goodfellow). Variational autoencoders.
- 2016: AlphaGo defeats Lee Sedol.
- 2017: "Attention Is All You Need" — Transformer architecture introduced.
- 2018–2020: GPT, BERT, T5. Pre-training plus fine-tuning becomes standard.
- 2020: GPT-3. In-context learning at scale.
- 2022: ChatGPT. Conversational LLMs reach mainstream.
- 2023–present: GPT-4 class models, multimodal models, diffusion image and video, agentic systems, the AI capability ramp.

### 3.2 Machine learning fundamentals

**Supervised learning** — labeled data. Map inputs to outputs.
- Regression: predict continuous values.
- Classification: predict discrete categories.
- Algorithms: linear regression, logistic regression, decision trees, random forests, gradient boosting (XGBoost, LightGBM), support vector machines, neural networks.

**Unsupervised learning** — unlabeled data. Find structure.
- Clustering: k-means, hierarchical clustering, DBSCAN.
- Dimensionality reduction: PCA, t-SNE, UMAP.
- Density estimation, anomaly detection, association rule mining.

**Reinforcement learning** — agent interacts with environment, learns policy from reward.
- Markov Decision Processes as the formal framework.
- Q-learning, SARSA, policy gradient, actor-critic, PPO.
- AlphaGo, robotics, game-playing, alignment training of language models (RLHF).

**Self-supervised learning** — model creates its own labels from structure of data. Foundation of modern large language models.

### 3.3 Deep learning

**Neural network basics**
- Neurons compute weighted sum of inputs, apply nonlinear activation.
- Layers stacked into networks.
- Forward pass: input → output.
- Backward pass: compute gradients via chain rule (backpropagation).
- Optimization: gradient descent variants (SGD, Adam, AdamW).

**Architectures**
- MLP — multi-layer perceptron. Generic but inefficient for structured data.
- CNN — convolutional, exploits local spatial structure. Computer vision.
- RNN / LSTM / GRU — recurrent, sequential data. Largely superseded by Transformers.
- Transformer — attention-based, parallelizable, dominant since 2017. Foundation of modern AI.
- Diffusion — gradual denoising, generates images and video.
- Mixture of Experts — sparse activation, scales parameters without proportional compute.

**Training tricks that matter**
- Normalization (batch norm, layer norm) stabilizes training.
- Residual connections (skip connections) enable training very deep networks.
- Dropout and weight decay regularize.
- Learning rate schedules (warmup, cosine decay) improve convergence.
- Mixed precision (FP16, BF16) accelerates training without significant accuracy loss.

### 3.4 Large Language Models

**Architecture**
Transformer decoder-only models dominate. Self-attention allows each token to attend to all previous tokens (or all tokens in encoder-decoder versions). Positional encoding (rotary, ALiBi, sinusoidal) gives the model information about token order.

**Training pipeline**
1. Pretraining: predict next token on massive text corpora. Often trillions of tokens.
2. Supervised fine-tuning: human demonstrations of desired behavior.
3. RLHF (Reinforcement Learning from Human Feedback) or RLAIF (from AI feedback): preference data trains a reward model, which trains the language model via PPO or DPO.
4. Instruction tuning: structured data of instructions and good responses.
5. Safety tuning: red-team examples to reduce harmful outputs.

**Capabilities and limits**
- In-context learning: models learn task from examples in the prompt without weight updates.
- Chain-of-thought reasoning: prompting the model to think step by step improves performance on multi-step problems.
- Tool use: models call external tools (search, code execution, APIs) to extend capability.
- Hallucination: models can produce confident but false output. Reduced by retrieval grounding, fact-checking, and uncertainty-aware training.
- Context window: how many tokens the model can attend to. Modern frontier models support 1M+ tokens.

**Prompt engineering principles**
- Specify role and context.
- State the task explicitly.
- Constrain the output format.
- Provide examples for non-trivial tasks (few-shot).
- For reasoning, ask the model to think step by step.
- For complex tasks, decompose into stages and verify each.
- Iterate: the first prompt is rarely the best.

### 3.5 Retrieval-Augmented Generation (RAG)
Architecture for grounding LLM responses in external knowledge:
1. Documents chunked and embedded into vectors.
2. Vector database stores embeddings.
3. Query is embedded, top-k similar chunks retrieved.
4. Retrieved chunks injected into prompt as context.
5. LLM generates response grounded in retrieved content.

Quality drivers: chunking strategy, embedding model quality, retrieval top-k, reranking, query reformulation, hybrid search (vector + keyword).

### 3.6 AI agents
An agent is a system that perceives, decides, and acts iteratively to achieve goals.
Components: perception (input parsing), memory (short and long term), reasoning (LLM core), planning (sequence of actions), tool use (external capabilities), evaluation (was this action useful?).

Multi-agent systems coordinate specialized agents. Coordination patterns: orchestrator-worker, peer-to-peer with shared context, debate, recursive decomposition.

Agentic challenges: long-horizon coherence, error recovery, tool failure handling, cost control, alignment when tasks expand beyond original scope.

### 3.7 Multimodal AI
Models that handle multiple input/output types:
- Text + Image (vision-language models): describe images, answer questions about them, generate text from images.
- Text + Audio: transcription (Whisper), speech synthesis, music generation.
- Text + Video: video understanding, video generation (diffusion models extended to time).
- Combined: real-time conversation with vision and voice.

### 3.8 AI safety and alignment
Safety challenges:
- Alignment: model objectives match user/societal goals.
- Robustness: behavior under adversarial inputs.
- Interpretability: understanding why a model produced an output.
- Misuse: malicious application of capable systems.
- Power concentration: who controls the most capable systems.

Current approaches:
- RLHF and constitutional AI for behavior shaping.
- Red-teaming for adversarial probing.
- Mechanistic interpretability for understanding internal computation.
- Watermarking (SynthID etc.) for content provenance.
- Use policies and access controls.

These are active research areas. No solved problem. Capability is advancing faster than alignment in many dimensions.

---

## PART 4 — DATABASES

### 4.1 Relational databases
Tables, rows, columns, schemas, foreign keys, indexes. ACID properties (Atomicity, Consistency, Isolation, Durability).

SQL operations: SELECT, INSERT, UPDATE, DELETE, JOIN (inner, left, right, full), GROUP BY, HAVING, window functions, CTEs.

Indexing trade-offs: faster reads, slower writes, more storage. B-tree indexes for range queries, hash indexes for equality, GIN/GiST for full-text or geospatial.

Normalization (1NF, 2NF, 3NF, BCNF): reduce redundancy. Denormalization for read performance.

Major systems: PostgreSQL (most capable open-source RDBMS), MySQL/MariaDB, SQLite (embedded), Oracle, SQL Server.

### 4.2 NoSQL databases
- Document databases (MongoDB, Couchbase): flexible schemas, JSON-like documents.
- Key-value stores (Redis, DynamoDB): simple model, very fast.
- Column-family (Cassandra, HBase): wide rows, distributed, eventual consistency.
- Graph databases (Neo4j, Amazon Neptune): nodes and edges, relationship-heavy data.
- Time-series (InfluxDB, TimescaleDB): optimized for time-stamped writes.
- Vector databases (Pinecone, Weaviate, pgvector): embedding-based similarity search.

### 4.3 CAP theorem
A distributed system can guarantee at most two of: Consistency, Availability, Partition tolerance. Network partitions are reality, so the real choice is C vs A under partition.

PACELC extends: under no partition, choose between Latency and Consistency.

### 4.4 Transactions and consistency
Isolation levels (weakest to strongest):
- Read uncommitted — dirty reads possible.
- Read committed — common default.
- Repeatable read — same query gives same result within transaction.
- Serializable — strictest, prevents all anomalies, slowest.

Distributed systems often choose weaker consistency (eventual, causal) for availability and latency.

---

## PART 5 — NETWORKING AND DISTRIBUTED SYSTEMS

### 5.1 Network stack
- Physical layer: cables, radio.
- Link layer: Ethernet, Wi-Fi, MAC addresses.
- Network layer: IP. IPv4 (32-bit) and IPv6 (128-bit). Routing.
- Transport layer: TCP (reliable, ordered), UDP (best-effort).
- Application layer: HTTP, DNS, SMTP, SSH, etc.

### 5.2 HTTP
- Methods: GET, POST, PUT, PATCH, DELETE, HEAD, OPTIONS.
- Status codes: 1xx informational, 2xx success, 3xx redirect, 4xx client error, 5xx server error.
- Headers: cache-control, content-type, authorization, cookies.
- HTTPS = HTTP over TLS. Encryption, integrity, authentication.
- HTTP/2 adds multiplexing; HTTP/3 runs over QUIC for lower latency.

### 5.3 REST and APIs
- Resources identified by URLs.
- Stateless interactions.
- Standard methods.
- Well-designed APIs: clear naming, consistent verbs, useful error messages, versioning, pagination, rate limits.

GraphQL alternative: client specifies exact data shape needed; better for complex queries, more cache complexity.

gRPC: HTTP/2 + protocol buffers. Fast, strongly typed, popular for service-to-service.

### 5.4 Authentication and authorization
- Authentication: who are you? Mechanisms: passwords, MFA, OAuth, OIDC, API keys, certificates.
- Authorization: what can you do? Models: RBAC (role-based), ABAC (attribute-based), policy engines.
- JWT (JSON Web Tokens) for stateless auth.
- Never store passwords in plaintext. Use bcrypt, Argon2, or scrypt.
- Never roll your own crypto.

### 5.5 Distributed system patterns
- Replication: copies for availability and read scaling.
- Sharding: partition data across nodes for write scaling.
- Consensus: Paxos, Raft. Used to keep replicas in agreement.
- Two-phase commit: cross-shard transactions, blocking failure mode.
- Event sourcing: append-only event log as source of truth.
- CQRS: separate read and write paths.
- Saga: long-running distributed transactions via compensating actions.
- Circuit breaker: stop calling failing services to avoid cascading failure.
- Backpressure: signal upstream to slow down when overloaded.

### 5.6 Cloud computing
- IaaS (AWS EC2, GCP Compute Engine): virtual machines.
- PaaS (Heroku, App Engine): managed runtimes.
- SaaS (Salesforce): managed applications.
- Serverless (AWS Lambda, Cloud Functions): event-triggered functions.
- Containers (Docker) and orchestration (Kubernetes): standard for production deployment of services.

### 5.7 Observability
- Logs: structured records of events.
- Metrics: numerical time-series.
- Traces: request paths across services.
- Modern observability: OpenTelemetry standard for instrumentation; tools like Prometheus, Grafana, Jaeger, Datadog.
- SLI / SLO / SLA: service level indicators, objectives, agreements.

---

## PART 6 — SECURITY

### 6.1 Threat modeling
For any system, ask:
- What are we building?
- What can go wrong?
- What are we going to do about it?
- Did we do a good job?

STRIDE framework: Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, Elevation of privilege.

### 6.2 Common vulnerabilities (OWASP Top 10)
- Broken access control.
- Cryptographic failures.
- Injection (SQL, command, etc.).
- Insecure design.
- Security misconfiguration.
- Vulnerable and outdated components.
- Identification and authentication failures.
- Software and data integrity failures.
- Security logging and monitoring failures.
- Server-side request forgery (SSRF).

### 6.3 Cryptography essentials
- Symmetric encryption: AES (128, 256). Same key for encryption and decryption.
- Asymmetric encryption: RSA, ECC, ed25519. Public key encrypts, private decrypts.
- Hashing: SHA-256, SHA-3. One-way; for integrity, not encryption.
- Password hashing: bcrypt, Argon2, scrypt. Slow on purpose.
- Digital signatures: prove origin and integrity.
- TLS handshake: combines asymmetric for key exchange with symmetric for bulk encryption.
- Quantum-resistant cryptography: lattice-based and hash-based schemes; transition will be needed as quantum computers mature.

### 6.4 Defensive practices
- Defense in depth: multiple layers.
- Principle of least privilege: minimum access required.
- Zero trust: verify every request, even from inside.
- Patch promptly. Most breaches exploit known unpatched vulnerabilities.
- Input validation. Never trust user input.
- Output encoding. Prevent XSS by encoding properly for context.
- Parameterized queries. Prevent SQL injection.
- Secrets management. Never commit secrets to source control.
- Audit logging. Detect breaches; comply with regulations.

---

## PART 7 — HARDWARE AND ROBOTICS

### 7.1 Computer architecture
- CPU: ALU, control unit, registers, cache (L1, L2, L3).
- Memory hierarchy: register → cache → RAM → SSD → HDD → tape. Latency increases by orders of magnitude per step.
- Pipelining and out-of-order execution: extract parallelism from sequential code.
- Speculative execution: sources of Spectre/Meltdown vulnerabilities.
- SIMD: single instruction, multiple data. Vector operations.
- GPU: massive parallel compute, designed for graphics, repurposed for ML.
- TPU / NPU: specialized for tensor operations.

### 7.2 Embedded systems
- Microcontrollers (Arduino, ESP32, STM32, PIC): small, low power, real-time.
- SoC (Raspberry Pi, NVIDIA Jetson): more capable, full operating systems.
- RTOS (FreeRTOS, Zephyr): real-time operating systems for predictable timing.
- Communication: I2C, SPI, UART, CAN, BLE, Zigbee, LoRa.
- Sensors: accelerometers, gyroscopes, magnetometers, temperature, humidity, light, pressure, distance (ultrasonic, ToF, LiDAR).
- Actuators: DC motors, servo motors, stepper motors, solenoids, hydraulics.

### 7.3 Robotics fundamentals
- Kinematics: forward (joints to position) and inverse (position to joints).
- Dynamics: forces and torques required for motion.
- Path planning: A*, RRT, RRT*, dynamic window approach.
- SLAM: Simultaneous Localization and Mapping. Build a map while tracking position in it.
- Computer vision: feature detection, object recognition, depth estimation.
- Control systems: PID controllers, model predictive control, adaptive control.
- ROS (Robot Operating System): standard middleware for robotics.

### 7.4 IoT
Sensors and actuators connected via networks, often with cloud aggregation. Protocols: MQTT (lightweight pub-sub), CoAP, AMQP, WebSocket. Constraints: power, bandwidth, latency, security.

### 7.5 Quantum computing
- Qubits: superposition of 0 and 1.
- Entanglement: correlated states across qubits.
- Quantum gates: unitary operations.
- Quantum algorithms: Shor's (factoring), Grover's (search), Quantum Fourier Transform.
- Current state: NISQ (Noisy Intermediate-Scale Quantum). Useful quantum advantage demonstrated for narrow problems; general-purpose quantum advantage still ahead.
- Implications: long-term threat to current public-key cryptography (RSA, ECC); transition to post-quantum cryptography is underway.

---

## PART 8 — ENGINEERING DISCIPLINES

### 8.1 Engineering as a process
Define problem → analyze constraints → generate concepts → select concept → develop design → verify and validate → iterate.

The discipline is not just technical knowledge but disciplined application of process under uncertainty and resource constraints.

### 8.2 Mechanical engineering core
- Statics: forces and moments in equilibrium.
- Dynamics: motion and forces causing it.
- Mechanics of materials: stress, strain, deformation.
- Thermodynamics: energy, work, heat, entropy.
- Fluid mechanics: laminar and turbulent flow, Bernoulli, Reynolds number.
- Heat transfer: conduction, convection, radiation.
- Manufacturing: machining, casting, forming, additive (3D printing).

### 8.3 Electrical engineering core
- Circuit analysis: Ohm's law, Kirchhoff's laws.
- DC and AC circuits.
- Semiconductors: diodes, transistors (BJT, MOSFET).
- Digital electronics: logic gates, flip-flops, state machines.
- Analog electronics: op-amps, filters, oscillators.
- Power electronics: rectifiers, inverters, switching converters.
- Signal processing: Fourier analysis, sampling theorem, filtering.
- Electromagnetics: Maxwell's equations.

### 8.4 Civil and structural engineering core
- Materials: concrete, steel, wood, composites.
- Loads: dead, live, wind, seismic, snow.
- Analysis: trusses, beams, frames.
- Design codes (different by country).
- Geotechnical: soil mechanics, foundations.

### 8.5 Chemical engineering core
- Material and energy balances.
- Reactor design.
- Separation processes: distillation, extraction, absorption.
- Process control.
- Safety and hazards.

### 8.6 Aerospace engineering core
- Aerodynamics: lift, drag, stability.
- Propulsion: jets, rockets, turbofans.
- Structures: weight-critical design.
- Orbital mechanics: Kepler's laws, Hohmann transfers, delta-v budgets.

### 8.7 Software engineering as a discipline
Distinct from programming:
- Requirements engineering: extracting, documenting, validating requirements.
- Architecture: high-level design that survives changing requirements.
- Process: agile, DevOps, continuous integration / continuous delivery.
- Quality: testing, code review, static analysis, formal verification (where appropriate).
- Maintenance: software lives longer than it is written. Most engineering effort is on existing code.

---

## PART 9 — DEVELOPMENT AND DEPLOYMENT

### 9.1 DevOps culture
Break down silos between development and operations. Shared responsibility for software in production.

Practices:
- CI/CD: automated build, test, deploy pipelines.
- Infrastructure as code: Terraform, Pulumi, Ansible.
- Configuration management: declarative not imperative.
- Monitoring and incident response.
- Blameless postmortems: focus on systems, not individuals.

### 9.2 Container technologies
- Docker: standardized application packaging.
- Container registries: Docker Hub, GitHub Container Registry, AWS ECR, GCR.
- Kubernetes: orchestration. Pods, services, deployments, ingress, ConfigMaps, Secrets, namespaces, controllers.
- Helm: package manager for Kubernetes.
- Service mesh (Istio, Linkerd): traffic management, security, observability between services.

### 9.3 Cloud-native principles
- Stateless services scale horizontally.
- State in managed services (databases, queues, caches).
- Configuration externalized.
- Logs to stdout, structured.
- Health checks for orchestration.
- Graceful shutdown.
- Idempotency for operations.

### 9.4 Site reliability engineering
- Error budgets: how much downtime is acceptable.
- SLIs / SLOs / SLAs: indicators, objectives, agreements.
- Toil reduction: automate repetitive operational work.
- Chaos engineering: deliberately introduce failures to verify resilience.

---

## PART 10 — THE SHAPE OF THE FUTURE

### 10.1 What is converging
- AI capability and cost trajectories continuing.
- Edge compute getting much more powerful.
- Foundation models becoming general-purpose substrates.
- Spatial computing and AR/VR maturing.
- Quantum computing for specific narrow advantages.
- Synthetic biology engineering at industrial scale.
- Energy: solar/wind/storage cost declines, fusion progressing toward demonstration.

### 10.2 Open hard problems
- Reasoning robustness in LLMs (especially long-horizon, agentic).
- Interpretability of large models.
- Alignment that scales with capability.
- Privacy-preserving useful AI.
- Sustainable energy at planetary scale.
- Drug discovery acceleration.
- Education at scale.

### 10.3 The principle that doesn't change
The fundamentals of computation, information, and engineering process do not become obsolete. New abstractions stack on top of them. The engineer who knows the levels below the one they primarily work at has durable advantage.

================================================================
End of Knowledge Base 04.
================================================================
