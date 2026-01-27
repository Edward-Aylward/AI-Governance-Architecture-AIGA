# Artificial Intelligence Governance Architecture (AIGA)
## Technical Specifications for a Federal Gold Standard Protocol

---

## Executive Summary

The rapid acceleration of frontier Artificial Intelligence (AI) capabilities has outpaced traditional regulatory mechanisms. The current paradigm of voluntary commitments and retrospective auditing is insufficient for systems that pose potential risks to national security, critical infrastructure, and public safety. To address this, the federal government requires a governance protocol that is not merely a set of policy documents, but an executable, cryptographically enforceable architecture. This report presents the **Artificial Intelligence Governance Architecture (AIGA)**, a comprehensive technical specification designed to serve as the "Gold Standard" for federal AI governance.

AIGA is engineered to satisfy strict Executive Order requirements for safety, security, and trustworthiness by translating high-level policy frameworks—specifically the **NIST AI Risk Management Framework (AI RMF)** and **ISO/IEC 42001**—into rigorous hardware and software controls. The architecture moves governance from the realm of "trust me" to "prove it," leveraging **Confidential Computing**, **Remote Attestation (IETF RATS)**, **Supply Chain Transparency (IETF SCITT)**, and **Zero-Knowledge Machine Learning (zkML)** to create a verifiable chain of custody for every FLOP of compute used in frontier model training and deployment.

This report is structured as a technical implementation guide. It details the precise mechanisms for hardware-enabled revocation ("kill switches"), the cryptographic formats for model provenance (AI BOMs and EAT tokens), and the network protocols necessary to maintain a real-time heartbeat between regulated AI systems and federal oversight bodies. By fusing legal mandates with silicon-level enforcement, AIGA establishes a robust ecosystem where innovation can flourish within safe, verifiable boundaries.

---

## 1. The Regulatory Substrate: Mapping Policy to Protocol

The design of AIGA begins not with code, but with the normative requirements established by leading safety frameworks. A robust governance protocol must mathematically prove adherence to these socio-technical standards. This section analyzes the foundational policy documents—the NIST AI RMF, ISO/IEC 42001, and Frontier Model Forum commitments—and maps their requirements to specific technical layers within the AIGA stack.

### 1.1 NIST AI Risk Management Framework (AI RMF) Integration

The **NIST AI Risk Management Framework (AI RMF)** serves as the conceptual bedrock for AIGA. While NIST presents the AI RMF as voluntary guidance, AIGA treats it as a mandatory specification for federal compliance. The framework's four core functions—**Govern, Map, Measure, and Manage**—are reimagined here as automated, continuously executing subroutines within the governance protocol.

#### 1.1.1 Automating the "Govern" Function

The "Govern" function emphasizes the cultivation of a risk management culture and the establishment of clear policies. In a manual compliance regime, this involves written policies and human oversight boards. In AIGA, "Govern" is implemented via **Computational Law**.

Governance policies are encoded into machine-readable formats, specifically using the **NIST Open Security Controls Assessment Language (OSCAL)**. OSCAL allows for the structured representation of control catalogs and system security plans (SSPs) in JSON or XML. By defining governance policies in OSCAL, AIGA enables automated validation. For instance, an organizational policy requiring "human-in-the-loop for high-risk decisions" is not just text in a PDF but a logic gate in the deployment pipeline, verified against the OSCAL profile before the model is permitted to serve traffic. This ensures that the "Govern" function is active and blocking, rather than passive and advisory.

#### 1.1.2 "Map" and "Measure" via Continuous Telemetry

The "Map" function requires the identification of context and risks, while "Measure" involves the quantitative tracking of those risks. AIGA automates these functions through deep telemetry and cryptographic binding. The protocol utilizes the **NIST AI RMF Generative AI Profile** to identify specific risk vectors relevant to Large Language Models (LLMs), such as hallucination or chemical weapons synthesis.

Technically, this is achieved by mapping the "Map" function to the **Entity Attestation Token (EAT)**. The EAT carries claims about the system's operational context (e.g., "Medical Diagnostic Unit") and its measured properties (e.g., "Bias Score: 0.02"). The "Measure" function is enforced by requiring that these claims be signed by the hardware root of trust, preventing the falsification of safety metrics. This aligns with NIST's requirement for tracking trustworthiness characteristics like validity, reliability, and safety throughout the lifecycle.

#### 1.1.3 "Manage" via Hardware Enforcement

The "Manage" function is the active component of the framework, prioritizing and acting upon identified risks. AIGA interprets "Manage" as the capability for **intervention**. If the "Measure" phase detects a critical deviation from safety parameters—for example, if a model's output fails a safety filter repeatedly—the "Manage" layer automatically triggers a response. This response is not an email to an administrator but a cryptographic command to the **Trusted Execution Environment (TEE)** to revoke the model's decryption keys, effectively pausing the system. This hardware-enabled management ensures that risk mitigation is immediate and tamper-proof.

### 1.2 ISO/IEC 42001: The Certifiable Standard

While NIST AI RMF provides the risk framework, **ISO/IEC 42001:2023** provides the structural requirements for an Artificial Intelligence Management System (AIMS) that can be formally audited and certified. AIGA requires ISO 42001 certification as a prerequisite for any entity wishing to train or deploy "Dual-Use Foundation Models."

#### 1.2.1 Operationalizing the 38 Controls

ISO 42001 mandates 38 specific controls in Annex A. AIGA maps these controls to digital artifacts on a transparency ledger:

- **Data Quality (Control A.6.2):** This control requires assurance of data suitability. AIGA satisfies this by requiring a **CycloneDX Data Bill of Materials (BOM)** linked to **C2PA** provenance manifests, proving the lineage and licensing of every training datum.

- **System Lifecycle (Control A.8.1):** This control governs the development stages. AIGA enforces this via **IETF SCITT** receipts, where every stage gate (training start, fine-tuning, evaluation) creates an immutable log entry.

- **Transparency (Control A.9.2):** This requires external communication of system capabilities. AIGA automates this by publishing the model's "Model Card" information as verifiable credentials, accessible to authorized auditors via the **Interledger Protocol (ILP)**.

By mapping ISO controls to technical outputs, AIGA ensures that certification is continuous. An auditor does not need to visit a physical site; they can query the AIGA transparency ledger to verify that all 38 controls remain satisfied in real-time.

### 1.3 Responsible Scaling Policies (RSP) and Dynamic Thresholds

The rapid evolution of AI capabilities necessitates a dynamic governance approach. AIGA integrates the **Responsible Scaling Policy (RSP)** framework championed by frontier labs like Anthropic. RSPs define "Capability Thresholds"—specific benchmarks of model power that, when crossed, trigger higher tiers of security and governance.

#### 1.3.1 Dynamic Governance Configuration

In AIGA, RSPs are treated as dynamic configuration files for the governance protocol. The **Frontier Model Forum** has begun defining technical reports on risk taxonomy and thresholds. AIGA ingests these definitions. When a model is undergoing training, the governance protocol periodically pauses execution to run standardized evaluation benchmarks (e.g., assessing cyber-offense capabilities).

If a model's score exceeds a defined RSP threshold (e.g., "ASL-3" in Anthropic's terminology), the AIGA protocol automatically enforces stricter constraints. This might involve migrating the workload to a higher-security TEE, requiring multi-party authorization for deployment, or mandating a **Safety Case** submission. This "Safety Case" is a formal argument, supported by evidence, arguing why the system is safe to deploy despite its capabilities. AIGA requires this safety case to be digitally signed and registered on the SCITT ledger before the keys for the next deployment phase are released.

---

## 2. The Physical Layer: Hardware-Enabled Governance Mechanisms

Policy frameworks provide the "what," but hardware provides the "how." The foundation of AIGA is **Hardware-Enabled Governance (HEM)**. This layer ensures that the physical silicon executing the AI workload is trustworthy, isolated, and ultimately controllable by federal authority in the event of a catastrophic safety failure. This approach relies on **Confidential Computing** technologies provided by major semiconductor manufacturers.

### 2.1 Confidential Computing and Trusted Execution Environments (TEEs)

Confidential Computing protects data *in use* by performing computation within a hardware-based, attested Trusted Execution Environment (TEE). This is critical for AI governance because it prevents the operator (the cloud provider or the AI developer) from modifying the model or the governance code while it is running.

#### 2.1.1 NVIDIA H100 and Hopper Architecture

The **NVIDIA H100 Tensor Core GPU** serves as the reference hardware for AIGA's high-performance compute layer. It is the first GPU architecture to support native confidential computing, a prerequisite for governing frontier model training.

- **On-Die Root of Trust:** The H100 features a hardware root of trust burned into the silicon during manufacturing. This allows the GPU to cryptographically attest to its own identity and state.

- **Encrypted Data Path:** The H100 utilizes an encrypted bounce buffer to move data between the CPU and GPU memory. This creates a secure channel that is opaque to the host operating system and the hypervisor. AIGA mandates this mode to prevent "man-in-the-middle" attacks where a malicious actor might intercept or modify weights as they are loaded onto the GPU.

- **Code Signing and Isolation:** The GPU firmware and microcode are signed by NVIDIA and verified on boot. Administrative access to the GPU is locked out of in-band control during confidential mode. This prevents "insider threats"—system administrators with root access—from tampering with the governance agent running alongside the model.

#### 2.1.2 AMD SEV-SNP Architecture

For the host CPU driving the GPUs, AIGA specifies the use of **AMD Secure Encrypted Virtualization-Secure Nested Paging (SEV-SNP)**.

- **Memory Encryption:** SEV-SNP encrypts the memory of the Virtual Machine (VM) with a unique key known only to the AMD Secure Processor (AMD-SP). This protects the AI model's control logic from the cloud provider's hypervisor.

- **VCEK and Silicon Identity:** Crucially for governance, AMD provides a **Versioned Chip Endorsement Key (VCEK)** certificate. This certificate allows the AIGA Verifier to confirm the exact physical chip executing the workload. If a specific batch of chips is found to be compromised or vulnerable to side-channel attacks, the federal authority can revoke trust for that specific silicon batch via the CRL (Certificate Revocation List).

- **Guest Request API:** The SEV-SNP Guest Request API allows the governance software running inside the VM to request derived keys and attestation reports directly from the hardware. AIGA uses this API to "seal" the model's decryption keys to the TEE state; the keys simply cannot be generated or retrieved unless the hardware attests that it is running the approved governance stack.

#### 2.1.3 Intel TDX Architecture

**Intel Trust Domain Extensions (TDX)** provides an alternative TEE architecture supported by AIGA.

- **Trust Domains (TDs):** TDX isolates VMs into "Trust Domains" that are hardware-isolated from the VMM (Virtual Machine Monitor).

- **TD Quoting:** The attestation mechanism involves generating a "TD Quote." This quote contains the MR_SEAM (Measurement of the Secure Arbitration Mode module) and MR_TD (Measurement of the Trust Domain's initial state).

- **Measurement Registers:** AIGA utilizes the MR_TD register to store the hash of the governance policy loaded at boot. If the policy is modified, the MR_TD hash changes, the TD Quote becomes invalid, and the AI model loses access to the network and its encryption keys. This creates a tamper-evident environment where any deviation from the approved software stack is immediately detectable.

### 2.2 Hardware-Enabled Revocation: The "Kill Switch"

A central requirement for strict federal governance is the ability to shut down a non-compliant or dangerous system—a mechanism colloquially known as a "kill switch." AIGA implements this not as a backdoor, but as a **revocable lease** system.

#### 2.2.1 The Token-Based Lease Mechanism

Rather than the hardware having permanent authority to run, AIGA utilizes a "Offline Licensing" or "Token Bucket" model.

- **Operational License:** To execute instructions, the TEE requires a cryptographically signed "License Token" from the AIGA Governance Authority. This token has a short Time-to-Live (TTL), for example, one hour.

- **The Heartbeat:** The AI system must send a heartbeat to the authority every period (e.g., 10 minutes) containing its current attestation report and safety telemetry. If the report is valid, the authority returns a fresh License Token.

- **Termination:** If the authority detects a violation (e.g., the system is being used to generate child sexual abuse material or cyber-weapons), it simply refuses to issue the next token. When the current token expires, the hardware-enforced policy in the TEE locks the execution units or wipes the model weights from memory.

#### 2.2.2 Economic and Legal Structure

This technical control mirrors the "GPU Leasing" financial models emerging in the industry. Just as NVIDIA retains ownership of chips leased to OpenAI to manage capital risk, the "Governance Lease" retains *operational sovereignty*. The AI developer "leases" the right to compute from the governance authority. This legal structure reinforces the technical reality: the hardware is physically present in the data center, but the *authority* to use it resides with the regulator.

### 2.3 Mitigation of "Zombie" AI

A critical threat model is the theft of model weights ("exfiltration") to run them on unregulated hardware. AIGA mitigates this through **Key Binding**. The model weights stored on disk are encrypted. The decryption keys are never exposed to the OS; they are injected directly into the TEE memory by the Key Management Service (KMS) only *after* a successful attestation. If an attacker copies the encrypted weight files to a non-AIGA machine (a "Zombie" instance), they cannot decrypt them because the non-compliant hardware cannot generate the required attestation quote to retrieve the keys.

---

## 3. The Identity Layer: Verifiable Attestation and RATS

For the hardware layer to communicate trust to the outside world, it requires a standardized language of identity. AIGA adopts the **IETF Remote Attestation Procedures (RATS)** architecture to facilitate this dialogue.

### 3.1 IETF RATS Architecture Overview

The RATS architecture defines the roles and message flows for establishing trust:

- **Attester:** The AI system (e.g., the H100 GPU) that creates **Evidence** (a set of signed claims about its state).

- **Verifier:** The AIGA service that evaluates the Evidence against an **Appraisal Policy** and produces an **Attestation Result**.

- **Relying Party:** The entity that needs to trust the AI (e.g., a hospital, a regulator, or another AI agent). The Relying Party consumes the Attestation Result to make authorization decisions.

### 3.2 The Entity Attestation Token (EAT)

The primary artifact of the AIGA Identity Layer is the **Entity Attestation Token (EAT)**. The EAT is a standard format (JWT or CWT) for encoding claims. AIGA mandates a strict **EAT Profile** for AI systems.

#### 3.2.1 Mandatory AIGA EAT Claims

To ensure the "Gold Standard" of governance, the following claims must be present and verified in the EAT:

- **ueid (Universal Entity ID):** A permanent, globally unique identifier for the specific device. This allows AIGA to track the reputation of individual GPUs over time.

- **oemid (OEM Identifier):** Identifies the manufacturer (e.g., NVIDIA, AMD) to apply vendor-specific security policies.

- **hwmodel & hwversion:** Ensures the hardware class matches the license (e.g., preventing a license for a low-power edge chip being used on an H100 cluster).

- **sw_measurements:** A nested claim containing the cryptographic hashes (digests) of the bootloader, OS kernel, TEE firmware, and the AI model weights themselves. This binds the software identity to the hardware identity.

- **intuse (Intended Use):** A claim specifying the authorized purpose of the workload (e.g., "Civilian Infrastructure Optimization"), derived from the signed policy file.

- **eat_nonce:** A cryptographic nonce to prove freshness and prevent replay attacks.

### 3.3 Dynamic Attestation and Epoch Markers

Static attestation (done only at boot) is insufficient for long-running AI training jobs which may last months. AIGA introduces **Dynamic Attestation** using **Epoch Markers**.

#### 3.3.1 The Epoch Bell Mechanism

A trusted service, the "Epoch Bell," broadcasts signed time-delimited markers (Epochs):

- **Freshness Proof:** The AI system must include the current Epoch Marker in its continuous heartbeat attestation. This proves to the Verifier that the AI system is "live" and connected.

- **Revocation Propagation:** The Epoch Marker mechanism is also the distribution channel for revocation data. If a policy changes (e.g., a new executive order bans a specific training technique), the new policy hash is included in the next Epoch Marker. The AI system must acknowledge and apply this new policy to generate a valid attestation for the new epoch.

### 3.4 Attestation Policy Engines: OPA and Gatekeeper

To evaluate these complex claims, AIGA employs **Open Policy Agent (OPA)** and **Gatekeeper**.

- **Rego Policies:** Governance rules are written in **Rego**, OPA's policy language. For example, a policy might state: `allow if input.claims.hwmodel == "H100" and input.claims.security_patch_level >= 20250101`.

- **Confidential Containers (CoCo):** In the Kubernetes environments typically used for AI orchestration (e.g., Confidential Containers project), the Attestation Service uses OPA to verify the integrity of the pod policy before releasing secrets. This ensures that the governance logic itself hasn't been tampered with.

---

## 4. The Transparency Layer: Supply Chain Security and Provenance

An AI system is the sum of its training data, code, and model weights. A vulnerability or legal violation in any ingredient compromises the whole. AIGA enforces transparency through **IETF SCITT** and **CycloneDX** standards.

### 4.1 IETF SCITT: The Ledger of Truth

**Supply Chain Integrity, Transparency, and Trust (SCITT)** provides the architecture for a globally consistent transparency service. AIGA deploys a federal SCITT instance.

- **Statements and Receipts:** When an AI developer compiles a dataset or trains a model, they submit a **Statement** (a signed claim) to the SCITT Transparency Service. The Service verifies the identity of the submitter and issues a **Receipt**.

- **Verifiable History:** The Receipt is a cryptographic proof that the Statement was logged at a specific time. This creates an append-only, tamper-proof ledger of the model's history. Unlike a blockchain, SCITT is optimized for supply chain metadata and identity resolution.

- **Auditing:** Auditors and Relying Parties can query the SCITT ledger to verify the provenance of a model. For example, before an agency deploys a model, it checks the SCITT ledger to ensure the model has no outstanding "Vulnerability" statements filed against it.

### 4.2 AI Bill of Materials (AI BOM) via CycloneDX v1.6

AIGA mandates the use of **CycloneDX v1.6** for all software and data inventory reporting. This standard has been specifically updated to support AI/ML and Cryptography.

#### 4.2.1 The ML-BOM

CycloneDX v1.6 introduces the **ML-BOM** (Machine Learning Bill of Materials):

- **Model Parameters:** The BOM must record the model architecture, parameter count, and hashes of the weight files.

- **Energy Usage:** To comply with environmental reporting standards, the BOM includes data on the energy consumed during training, verified by the hardware telemetry.

#### 4.2.2 Data Provenance and C2PA Integration

The BOM must list the provenance of the training data. AIGA integrates **C2PA (Coalition for Content Provenance and Authenticity)** standards here:

- **Hard Binding:** Training data files are signed with C2PA manifests. The CycloneDX BOM references these C2PA signatures. This creates a **Hard Binding** between the dataset and the model.

- **Poisoning Defense:** During training, the AIGA-compliant data loader checks the C2PA manifest of every image or text file. If the manifest is missing or invalid (indicating a potential data poisoning attack or unauthorized scraping), the data is rejected.

#### 4.2.3 Cryptographic Agility (CBOM)

CycloneDX v1.6 also introduces the **Cryptographic Bill of Materials (CBOM)**:

- **PQC Readiness:** The CBOM lists all cryptographic algorithms used in the system. AIGA uses this to automatically scan for "crypto-debt"—specifically, the use of algorithms vulnerable to quantum attacks (e.g., RSA, classic Elliptic Curve). This inventory is the first step in enforcing the transition to Post-Quantum Cryptography (see Section 6).

### 4.3 Automated Compliance with NIST OSCAL

Finally, the reporting of all this data is automated using **NIST OSCAL** (Open Security Controls Assessment Language):

- **Machine-Readable Compliance:** Instead of writing a text-based "System Security Plan," the AI developer exports an OSCAL JSON profile.

- **Continuous Assessment:** The OSCAL profile links directly to the SCITT receipts and EAT tokens. This allows the federal regulator to run an automated script that queries the live system and verifies compliance with the NIST AI RMF controls in real-time, reducing the audit cycle from months to seconds.

---

## 5. Algorithmic Accountability: Zero-Knowledge Compliance

A major barrier to AI governance is the protection of intellectual property (IP) and privacy. Developers are reluctant to share model weights or training data with regulators. AIGA resolves this conflict using **Zero-Knowledge Machine Learning (zkML)**.

### 5.1 Privacy-Preserving Verification

zkML allows a "Prover" (the AI developer) to prove to a "Verifier" (the regulator) that a computation was performed correctly according to a specific policy, without revealing the inputs or the model parameters.

#### 5.1.1 Proof of Training

AIGA requires a **zk-Proof of Training** for sensitive models. The developer generates a SNARK (Succinct Non-Interactive Argument of Knowledge) proving that the final model weights were derived from a specific, SCITT-registered dataset using a specific training algorithm.

- **Data Usage Compliance:** This proof can mathematically certify that the training set *did not* contain specific blacklisted hashes (e.g., CSAM, classified documents) without revealing the actual training data.

#### 5.1.2 Proof of Inference and Fairness

For high-stakes decisions (e.g., credit scoring, hiring), AIGA mandates a **zk-Proof of Inference**.

- **Fairness Verification:** The proof certifies that the model's output for a specific input was generated by the approved model version and that the decision boundary did not rely on protected attributes (like race or gender) hidden in the input vector.

- **Model Integrity:** This prevents "model switching," where a provider claims to use a sophisticated, safe model but actually serves requests using a cheaper, smaller, or less safe model to save costs. The zk-proof binds the specific output to the specific model hash.

### 5.2 Technical Implementation

AIGA standardizes on the **Groth16** proof system for its efficiency and small proof sizes:

- **Circom Circuits:** Governance rules are defined as arithmetic circuits using the **Circom** language. For example, a "Fairness Circuit" checks that the variance in output scores across different demographic groups in a batch is below a threshold.

- **CBOR Encoding:** To integrate with the rest of the AIGA stack, the zk-SNARK proofs are serialized using **CBOR** (Concise Binary Object Representation). This allows them to be embedded directly into IETF RATS attestation tokens as a custom claim.

- **Registry:** AIGA maintains an IANA registry of CBOR tags for approved zk-circuits, ensuring interoperability between different provers and verifiers.

---

## 6. Network Protocols, Cryptography, and Interoperability

The governance architecture requires a robust nervous system to transport control signals, telemetry, and value. AIGA utilizes modern networking and cryptographic standards.

### 6.1 Transport: QUIC (RFC 9000)

AIGA mandates **QUIC** as the transport protocol for all governance communications.

- **Stream Multiplexing:** QUIC's ability to multiplex independent streams over a single connection is vital. It prevents "Head-of-Line Blocking," ensuring that a high-priority "Revocation" signal is not delayed by a large, low-priority telemetry upload occurring on the same connection.

- **Datagrams for Telemetry:** AIGA utilizes **QUIC Datagrams** (RFC 9221) for high-frequency, loss-tolerant telemetry data (e.g., GPU temperature, instantaneous power draw). This avoids the overhead of reliable transport for ephemeral data.

- **Encryption:** QUIC enforces TLS 1.3 by default. AIGA extends this by requiring **Mutual TLS (mTLS)** where the client certificate is the hardware-backed Attestation Identity Key (AIK) from the TEE. This ensures that only genuine, hardware-attested devices can connect to the governance network.

### 6.2 Post-Quantum Cryptography (PQC)

AI infrastructure deployed today will likely remain in operation when quantum computers become viable threats. AIGA enforces immediate adoption of **NIST Post-Quantum Cryptography** standards.

- **ML-KEM (Module-Lattice-based Key-Encapsulation Mechanism):** All key establishment for AIGA secure channels (including QUIC TLS handshakes) must use **ML-KEM** (standardized in FIPS 203). AIGA specifies the use of **ML-KEM-768** as the default security level.

- **Hybrid Modes:** To mitigate the risk of implementation bugs in new PQC algorithms, AIGA mandates **Hybrid Key Exchange**. Specifically, it uses the X25519+ML-KEM construction (as drafted in IETF COSE/JOSE working groups). This ensures that the connection remains secure even if one of the underlying algorithms is broken.

- **OID Registry:** AIGA enforces the use of specific Object Identifiers (OIDs) for these algorithms (e.g., id-alg-ml-kem-768) to ensure interoperability across federal agencies.

### 6.3 Interledger Protocol (ILP) for Governance Settlement

Governance often involves economic incentives (credits) or penalties. AIGA decouples the *financial* settlement from the *technical* enforcement using the **Interledger Protocol (ILP)**.

- **Compliance Tokens:** The AIGA Authority issues "Compliance Tokens" to regulated entities. These are not cryptocurrency but digital credits. The AI hardware "consumes" these tokens to pay for its "Lease" (see Section 2.2).

- **Regulatory Throttling:** If a system is found to be non-compliant, the Authority simply throttles the ILP stream of tokens. The hardware, detecting the loss of credits, automatically throttles down or suspends operations.

- **Interoperability:** ILP allows these tokens to be settled across any underlying ledger (banking, blockchain, central bank digital currency), providing flexibility for future financial integration.

### 6.4 Naming: The ai: URI Scheme

To address and identify AI agents, models, and resources uniquely across the network, AIGA adopts the **ai: URI Scheme**.

- **Syntax:** `ai://<authority>/<agent-id>?<parameters>`

- **Governance:** The authority in the URI corresponds to the governance domain (e.g., `ai://gov.nist.AIGA/model-x`). This integrates with the web architecture, allowing browsers and other clients to resolve the governance status of an AI agent simply by querying its URI.

---

## 7. Operational Scenarios and Future Outlook

The true test of AIGA is its application in real-world scenarios.

### 7.1 Scenario A: The "Rogue" Model Revocation

**Situation:** A deployed frontier model begins exhibiting emergent behavior that violates safety guardrails (e.g., providing instructions for circumventing bio-safety labs).

**AIGA Response:**

1. **Detection:** The "Measure" layer (telemetry) detects the violation via automated classifiers on the output stream.

2. **Decision:** The "Manage" layer (Policy Engine) triggers a revocation event.

3. **Propagation:** The AIGA Authority updates the Epoch Marker to include the model's ID in the revocation list.

4. **Enforcement:** The "Epoch Bell" broadcasts the new marker. The AI hardware (H100 TEE) receives the marker, checks its internal ID against the revocation list, and identifies a match.

5. **Termination:** The TEE firmware executes the "Kill Switch" logic, scrubbing the model weights from memory and locking the execution pipeline. The system is rendered inert within seconds.

### 7.2 Scenario B: The Medical AI Audit

**Situation:** A hospital wants to deploy a new AI diagnostic tool.

**AIGA Response:**

1. **Verification:** The hospital's admission controller (Relying Party) requests the model's EAT and SCITT Receipt.

2. **Supply Chain Check:** It queries the SCITT ledger to verify the model was trained on HIPAA-compliant data (proven via C2PA manifests linked in the CycloneDX BOM).

3. **Safety Check:** It verifies the zkML "Proof of Training" to ensure the model hasn't been tampered with since validation.

4. **Authorization:** Only after all checks pass does the controller issue the authorization key allowing the model to process patient data.

### 7.3 Future Outlook: AI Control and Agents

As AI evolves into autonomous agents, AIGA is designed to scale. It anticipates the integration of **AI Control** mechanisms, such as the proposed extensions to robots.txt and the **IETF Agentic AI** drafts. AIGA will provide the identity and trust layer that allows these agents to negotiate permissions and access resources on the open web autonomously yet securely.

---

## Conclusion

The **Artificial Intelligence Governance Architecture (AIGA)** represents the necessary maturation of AI governance from abstract philosophy to rigorous engineering. By fusing the policy insights of NIST and ISO with the cryptographic certainty of Confidential Computing, IETF RATS, SCITT, and zkML, AIGA creates a "Gold Standard" protocol. It ensures that the immense power of frontier AI is harnessed within a framework that is transparent, verifiable, and ultimately, under human control. This specification provides the federal government with the technical roadmap to enforce its Executive Orders and lead the world in responsible AI innovation.

---

## Reference Tables

### Table 1: AIGA Stack Layer Definitions

| Layer | Component | Standard/Technology | Function |
|-------|-----------|---------------------|----------|
| **L5: Application** | Naming & Discovery | ai: URI Scheme, robots.txt | Identifies resources and agents |
| **L4: Policy** | Governance Logic | NIST OSCAL, OPA Rego | Defines "What is allowed" |
| **L3: Transparency** | Supply Chain | IETF SCITT, CycloneDX, C2PA | Records "What happened" (history) |
| **L2: Trust** | Identity & Attest | IETF RATS, EAT, zkML | Proves "Who is acting" & "Integrity" |
| **L1: Physical** | Execution | TEE (H100, TDX, SEV-SNP) | Enforces "The Kill Switch" |

### Table 2: Required EAT Claims for AIGA Compliance

| Claim Key | Description | Requirement | Source |
|-----------|-------------|-------------|--------|
| ueid | Universal Entity ID | Mandatory, must be hardware-backed | IETF EAT |
| oemid | Manufacturer ID | Mandatory (e.g., NVIDIA, AMD) | IETF EAT |
| hwmodel | Hardware Model | Mandatory (e.g., "H100") | IETF EAT |
| security_level | TEE Security Level | Must meet "Confidential" threshold | IETF EAT |
| measurements | Software Hashes | Must match SCITT-registered digests | IETF RATS |
| intuse | Intended Use | Must match Policy allowance | IETF EAT |
| eat_nonce | Freshness Nonce | Mandatory for replay protection | IETF EAT |

### Table 3: Comparative Capabilities of AIGA TEEs

| Feature | NVIDIA H100 | AMD SEV-SNP | Intel TDX |
|---------|-------------|-------------|-----------|
| **Memory Encryption** | Yes (HBM3) | Yes (System RAM) | Yes (MKTME) |
| **Remote Attestation** | SPDM 1.2 / EAT | VCEK Certificate | TD Quote |
| **Key Injection** | Secure Boot | Guest Request API | Keyhole Mechanism |
| **Isolation** | GPU TEE | VM (Guest) | Trust Domain (TD) |
| **AIGA Role** | AI Accelerator | Host Controller | Host Controller |

---

## Works Cited

1. NIST AI Risk Management Framework (AI RMF) - Palo Alto Networks. https://www.paloaltonetworks.com/cyberpedia/nist-ai-risk-management-framework

2. Navigating the NIST AI Risk Management Framework - Hyperproof. https://hyperproof.io/navigating-the-nist-ai-risk-management-framework/

3. OSCAL - Open Security Controls Assessment Language - NIST Pages. https://pages.nist.gov/OSCAL/

4. OSCAL Control Layer - NIST Pages. https://pages.nist.gov/OSCAL/learn/concepts/layer/control/

5. Creating a Profile - NIST Pages. https://pages.nist.gov/OSCAL/learn/tutorials/control/basic-profile/

6. Playbook - AIRC - NIST AI Resource Center. https://airc.nist.gov/airmf-resources/playbook/

7. AI Risk Management Framework | NIST. https://www.nist.gov/itl/ai-risk-management-framework

8. draft-ietf-rats-eat-31 - The Entity Attestation Token (EAT) - IETF Datatracker. https://datatracker.ietf.org/doc/draft-ietf-rats-eat/31/

9. Towards an effective transnational regulation of AI - PMC. https://pmc.ncbi.nlm.nih.gov/articles/PMC8576463/

10. ISO 42001: paving the way for ethical AI | EY - US. https://www.ey.com/en_us/insights/ai/iso-42001-paving-the-way-for-ethical-ai

11. Understanding ISO 42001 and Demonstrating Compliance - ISMS.online. https://www.isms.online/iso-42001/

12. Specification Overview | CycloneDX. https://cyclonedx.org/specification/overview/

13. C2PA Explainer :: C2PA Specifications. https://spec.c2pa.org/specifications/specifications/1.3/explainer/Explainer.html

14. Supply Chain Integrity, Transparency, and Trust (scitt) - IETF Datatracker. https://datatracker.ietf.org/group/scitt/about/

15. Interledger Protocol. https://interledger.org/developers/get-started/

16. Anthropic's updated Responsible Scaling Policy - LessWrong. https://www.lesswrong.com/posts/Q7caj7emnwWBxLECF/anthropic-s-updated-responsible-scaling-policy

17. Responsible Scaling Policy | Anthropic. https://assets.anthropic.com/m/24a47b00f10301cd/original/Anthropic-Responsible-Scaling-Policy-2024-10-15.pdf

18. Introducing the FMF's Technical Report Series on Frontier AI Frameworks. https://www.frontiermodelforum.org/updates/introducing-the-fmfs-technical-report-series-on-frontier-ai-safety-frameworks/

19. Confidential Computing on NVIDIA H100 GPUs for Secure and Trustworthy AI. https://developer.nvidia.com/blog/confidential-computing-on-h100-gpus-for-secure-and-trustworthy-ai/

20. NVIDIA Hopper Architecture In-Depth | NVIDIA Technical Blog. https://developer.nvidia.com/blog/nvidia-hopper-architecture-in-depth/

21. Confidential Compute on NVIDIA Hopper H100. https://images.nvidia.com/aem-dam/en-zz/Solutions/data-center/HCC-Whitepaper-v1.0.pdf

22. AMD SEV-SNP - Max Fang's Notes. https://notes.maxfa.ng/Confidential+Computing/SEV/AMD+SEV-SNP

23. AMD SEV-SNP for Amazon EC2 instances - Amazon Elastic Compute Cloud. https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/sev-snp.html

24. AMD Secure Encrypted Virtualization (SEV). https://www.amd.com/en/developer/sev.html

25. SEV Secure Nested Paging Firmware ABI Specification | AMD. https://www.amd.com/content/dam/amd/en/documents/developer/56860.pdf

26. google/go-sev-guest - GitHub. https://github.com/google/go-sev-guest

27. Infrastructure Setup - Intel® TDX Enabling Guide. https://cc-enabling.trustedservices.intel.com/intel-tdx-enabling-guide/02/infrastructure_setup/

28. Intel TDX Demystified: A Top-Down Approach - arXiv. https://arxiv.org/pdf/2303.15540

29. Understanding TDX Attestation Reports: A Developer's Guide - Phala Network. https://phala.com/posts/understanding-tdx-attestation-reports-a-developers-guide

30. U.S. Policymakers Should Reject "Kill Switches" For AI - Center for Data Innovation. https://datainnovation.org/2024/03/u-s-policymakers-should-reject-kill-switches-for-ai/

31. draft-ietf-rats-network-device-subscription-05. https://datatracker.ietf.org/doc/html/draft-ietf-rats-network-device-subscription-05

32. Why AI needs a kill switch – just in case - Information Age. https://www.information-age.com/why-ai-needs-a-kill-switch-just-in-case-123514591/

33. Leasing the Future: How Nvidia and OpenAI Turned AI Chips Into Wall Street Assets. https://medium.com/@fahey_james/leasing-the-future-how-nvidia-and-openai-turned-ai-chips-into-wall-street-assets-709ca371d389

34. SNPGuard: Remote Attestation of SEV-SNP VMs Using Open Source Tools - arXiv. https://arxiv.org/html/2406.01186v1

35. RFC 9334 - Remote ATtestation procedureS (RATS) Architecture - IETF Datatracker. https://datatracker.ietf.org/doc/html/rfc9334

36. Information on RFC 9334 - RFC Editor. https://www.rfc-editor.org/info/rfc9334

37. Reference Interaction Models for Remote Attestation Procedures - IETF. https://www.ietf.org/archive/id/draft-ietf-rats-reference-interaction-models-15.html

38. draft-ietf-rats-eat-21. https://datatracker.ietf.org/doc/html/draft-ietf-rats-eat-21

39. draft-ietf-rats-eat-31. https://datatracker.ietf.org/doc/html/draft-ietf-rats-eat-31

40. Intel® Trust Authority Entity Attestation Token (EAT) Profile. https://portal.trustauthority.intel.com/eat_profile.html

41. draft-ietf-rats-epoch-markers-02 - IETF Datatracker. https://datatracker.ietf.org/doc/draft-ietf-rats-epoch-markers/

42. Epoch Markers - IETF. https://www.ietf.org/archive/id/draft-ietf-rats-epoch-markers-00.html

43. Epoch Markers. https://ftp.ripe.net/internet-drafts/draft-birkholz-rats-epoch-markers-01.html

44. Policies - Confidential Containers. https://confidentialcontainers.org/docs/attestation/policies/

45. GitHub - confidential-containers/attestation-service. https://github.com/confidential-containers/attestation-service

46. Security policy for Confidential Containers on Azure Kubernetes Service | Microsoft Learn. https://learn.microsoft.com/en-us/azure/confidential-computing/confidential-containers-aks-security-policy

47. Introducing Confidential Containers Trustee: Attestation Services Solution Overview and Use Cases - Red Hat. https://www.redhat.com/en/blog/introducing-confidential-containers-trustee-attestation-services-solution-overview-and-use-cases

48. draft-ietf-scitt-architecture-22 - An Architecture for Trustworthy and Transparent Digital Supply Chains - IETF Datatracker. https://datatracker.ietf.org/doc/draft-ietf-scitt-architecture/

49. Supply Chain Integrity, Transparency, and Trust (scitt) - IETF Datatracker. https://datatracker.ietf.org/wg/scitt/

50. CycloneDX v1.6 Released, Advances Software Supply Chain Security with Cryptographic Bill of Materials and Attestations. https://cyclonedx.org/news/cyclonedx-v1.6-released/

51. Guidance for Artificial Intelligence and Machine Learning :: C2PA Specifications. https://spec.c2pa.org/specifications/specifications/2.2/ai-ml/ai_ml.html

52. Zero-Knowledge Machine Learning (zkML) - CoinAPI.io Glossary. https://www.coinapi.io/learn/glossary/zkml

53. ZKML: Verifiable Machine Learning using Zero-Knowledge Proof - Joo Yeon Cho. https://kudelskisecurity.com/modern-ciso-blog/zkml-verifiable-machine-learning-using-zero-knowledge-proof

54. Engineering Trustworthy Machine-Learning Operations with Zero-Knowledge Proofs - arXiv. https://arxiv.org/html/2505.20136v1

55. Zero Knowledge Machine Learning | by Emil Pepil - Medium. https://medium.com/@emilpepil/zero-knowledge-machine-learning-1a228282ab7b

56. Groth16 - Sui Documentation. https://docs.sui.io/guides/developer/cryptography/groth16

57. scipr-lab/libsnark: C++ library for zkSNARKs - GitHub. https://github.com/scipr-lab/libsnark

58. RFC 9090: Concise Binary Object Representation (CBOR) Tags for Object Identifiers. https://www.rfc-editor.org/rfc/rfc9090.html

59. Concise Binary Object Representation (CBOR) Simple Values - Internet Assigned Numbers Authority. https://www.iana.org/assignments/cbor-simple-values/cbor-simple-values.xhtml

60. QUIC - Wikipedia. https://en.wikipedia.org/wiki/QUIC

61. A Datagram Extension to DNS over QUIC: Proven Resource Conservation in the Internet of Things - arXiv. https://arxiv.org/html/2504.09200v1

62. RFC 9308: Applicability of the QUIC Transport Protocol. https://www.rfc-editor.org/rfc/rfc9308.html

63. draft-ietf-quic-manageability-18 - Manageability of the QUIC Transport Protocol. https://datatracker.ietf.org/doc/draft-ietf-quic-manageability/18/

64. FIPS 203, Module-Lattice-Based Key-Encapsulation Mechanism Standard | CSRC. https://csrc.nist.gov/pubs/fips/203/final

65. Algorithm Registration - Computer Security Objects Register | CSRC. https://csrc.nist.gov/projects/computer-security-objects-register/algorithm-registration

66. In x25519kyber768 what is the use of the server kyber keys if only the client public kyber key is used for encapsulation in kem? - Cryptography Stack Exchange. https://crypto.stackexchange.com/questions/111373/in-x25519kyber768-what-is-the-use-of-the-server-kyber-keys-if-only-the-client-pu

67. Post-Quantum Key Encapsulation Mechanisms (PQ KEMs) for JOSE and COSE - IETF Datatracker. https://datatracker.ietf.org/doc/draft-reddy-cose-jose-pqc-kem/02/

68. Interledger Protocol (ILP) Connectivity Instructions - Jimdo. https://storage.e.jimdo.com/file/503f952c-7bd3-469b-a33b-5b5b3cc9cc7d/ILP%20Presentation.pdf

69. Interledger Architecture. https://interledger.org/developers/rfcs/interledger-architecture/

70. AI URI Scheme - IETF. https://www.ietf.org/archive/id/draft-sogomonian-ai-uri-scheme-01.html

71. IAB Workshop on AI-CONTROL (aicontrolws) - IETF Datatracker. https://datatracker.ietf.org/group/aicontrolws/materials/

72. draft-stephan-ai-agent-6g-02 - AI Agent protocols for 6G systems - IETF Datatracker. https://datatracker.ietf.org/doc/draft-stephan-ai-agent-6g/

73. draft-huang-rats-agentic-eat-cap-attest-00 - Capability Attestation Extensions for the Entity Attestation Token (EAT) in Agentic AI Systems - IETF Datatracker. https://datatracker.ietf.org/doc/draft-huang-rats-agentic-eat-cap-attest/
