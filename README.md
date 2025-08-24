# 🌍 GeoZK: Zero-Knowledge Proofs for Geolocation Verification

GeoZK is a research & development project that combines **Zero-Knowledge Proofs (ZKPs)**, **Rust-based Solana smart contracts**, and **data engineering pipelines** to **prove user presence in a geographic location without revealing raw coordinates**.  

📌 **Core Idea:**  
> *"Prove a user was inside a region at a certain time, without leaking the exact location."*  

This project blends **cryptography, blockchain, and geospatial analytics** to create privacy-preserving proofs of location.

---

## 🛠 Tech Stack

- **ZK Circuits**: [Circom](https://docs.circom.io/), SnarkJS  
- **Blockchain**: Solana (Rust / Anchor)  
- **Backend / Data Engineering**: Python, Apache Spark + Sedona, Airflow  
- **Frontend**: React + Map Visualization (Heatmaps & Analytics)  
- **Infra**: Docker, GitHub Actions (CI/CD)

---

## 🚧 Development Roadmap

### ✅ Phase 0: Environment & GitHub Setup (Done)
- Ubuntu setup with Python, Rust, Circom, SnarkJS, Solana, Node.js, Docker
- Repo initialized: [GeoZK GitHub](https://github.com/rounsunn-dev/GeoZK)
- Folder structure scaffolded with `.gitkeep`

---

### 🚀 Phase 1: ZK Circuit & Proof Generation (Week 1)
- [ ] Circom circuit: verify `(lat, long)` is inside a polygon (region boundary)  
- [ ] Compile circuit → `.r1cs`, `.wasm`, `.sym`  
- [ ] Use SnarkJS to generate witness, `.zkey`, and verification key  
- [ ] Generate `proof.json` + `public.json` and store in `/zk_proofs/outputs`

---

### 🧠 Phase 2: Rust Verifier & Solana Integration (Week 2)
- [ ] Build verifier in Rust (convert from SnarkJS output)  
- [ ] Deploy Solana program on Devnet  
- [ ] Verify zkProofs on-chain & log transactions  

---

### ⚙️ Phase 3: Data Engineering + Proof Linking (Week 3–4)
- [ ] Collect simulated geolocation data (`device_id`, `lat`, `long`, `timestamp`)  
- [ ] Build Airflow DAGs for ETL  
- [ ] Integrate Circom proof generation into DAGs  
- [ ] Link proofs with device data for verifiable geospatial records  

---

### 📊 Phase 4: Analytics Dashboard (Week 5)
- [ ] React-based UI with geospatial heatmaps of **verified presence**  
- [ ] Admin panel for manual proof verification (`proof.json` upload, decode output)  

---

### 🧪 Phase 5: Tests + Docs + Deployment (Week 6)
- [ ] Unit & integration tests  
- [ ] `/docs` with specs + architecture diagrams + pitch deck  
- [ ] Dockerize all modules & set up CI/CD (GitHub Actions)  
- [ ] Deploy frontend dashboard + APIs  

---

## 🎯 Final Goal
A **privacy-preserving geolocation verification system** where:  
1. Users generate ZK proofs of being inside a region.  
2. Proofs are verified on Solana.  
3. Data engineers can run analytics & visualize presence via dashboards.  

---


## 📁 Project Structure
- `zk_proofs/`: Circuits, inputs, proofs
- `contracts/`: Rust smart contracts, verifiers
- `data_pipeline/`: PySpark jobs, Airflow DAGs
- `dashboard/`: Frontend + analytics
- `infrastructure/`: Dockerfiles, CI/CD
- `tests/`: Unit and integration tests
- `docs/`: Pitch deck, architecture, notes

## 🛠️ Setup
See `docs/specs/setup.md` for environment setup.

---

