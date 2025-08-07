📌 **GeoZK: Milestones and Step-by-Step Development Plan**

---

## ✅ Phase 0: Environment & GitHub Setup (✅ Done)

* [x] Install Ubuntu OS and configure development environment
* [x] Set up Python, Rust, Circom, SnarkJS, Solana, Node.js, Docker, Git
* [x] Create project folder structure with `.gitkeep`
* [x] Initialize Git & GitHub repo with SSH

---

## 🚀 Phase 1: Build ZK Circuit & Generate Proofs (Week 1)

### 🧩 1. Design Minimal Circom Circuit

* [ ] Create circuit to check if a user location (lat, long) lies **within a polygon** (region boundary)
* [ ] Encode region polygon as public input
* [ ] Encode user's lat/long and timestamp as private input

### 🔧 2. Compile & Test Circuit

* [ ] Use `circom` to compile `.circom` file → get `.r1cs`, `.wasm`, `.sym`
* [ ] Create `input.json` and use SnarkJS to generate witness `.wtns`
* [ ] Run `groth16` setup: generate `.ptau`, `.zkey`, and verification key

### ✅ 3. Generate and Verify ZK Proofs

* [ ] Run `snarkjs groth16 prove` and `verify`
* [ ] Save `proof.json` and `public.json`
* [ ] Document results in `zk_proofs/outputs`

---

## 🧠 Phase 2: Build Rust Verifier & Solana Integration (Week 2)

### 🔒 4. Rust-based Verifier

* [ ] Create a verifier contract using `snarkjs zkey export solidityverifier` as base
* [ ] Convert it to Rust compatible logic
* [ ] Scaffold a Solana program (using Anchor or native Rust)

### 🪙 5. Deploy on Solana Devnet

* [ ] Deploy smart contract to Devnet
* [ ] Use CLI to test proof verification on-chain
* [ ] Log transaction and success

---

## ⚙️ Phase 3: Data Engineering + Proof Linking (Week 3–4)

### 📥 6. Collect Geolocation Data

* [ ] Simulate or ingest `device_id`, `lat`, `long`, `timestamp` using Spark/Sedona
* [ ] Create Airflow DAG to orchestrate periodic ETL jobs

### 🔗 7. Integrate Proof Generation in ETL

* [ ] Use Python subprocess to trigger Circom proof creation inside DAG
* [ ] Store `proof.json` and `public.json` alongside raw data

### 🧾 8. Link Proofs to Devices

* [ ] Join device data with zk proofs using device ID and timestamp
* [ ] Store in output table (Parquet or JSONL)

---

## 📊 Phase 4: Analytics Dashboard (Week 5)

### 📈 9. Build Frontend UI

* [ ] React/JS frontend to display verified presence analytics
* [ ] Map view with heat zones of verified presence

### 🔍 10. Admin Panel for Manual Verifier

* [ ] Upload proof.json, see decoded output
* [ ] View logs from smart contract or verifier node

---

## 🧪 Phase 5: Tests + Docs + Deployment (Week 6)

### ✅ 11. Testing

* [ ] Unit tests for ZK proof generation
* [ ] Integration test for pipeline + verifier + dashboard

### 📄 12. Documentation

* [ ] Fill `/docs/specs` and `/docs/pitch_deck`
* [ ] Add architecture diagrams

### 🚢 13. Deployment

* [ ] Dockerize each module
* [ ] Optional: GitHub Actions for CI/CD
* [ ] Host dashboard and expose API

---

## 💡 Final Goal:

"Prove a user was inside a location using ZK, log it in a verifiable system, analyze it via dashboards."

---
