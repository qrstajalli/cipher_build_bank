# CIPHER

### Connected Intelligence for Pattern & Hidden Entity Recognition

> **Detect patterns. Trace networks. Predict financial crime.**

[![Vite](https://img.shields.io/badge/Vite-5.4-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![React](https://img.shields.io/badge/React-18.3-61DAFB?logo=react&logoColor=black)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.5-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-38B2AC?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

CIPHER is an AI-powered financial crime intelligence platform designed to identify suspicious activity that remains invisible when transactions are analyzed in isolation.

Instead of treating every transaction as a disconnected event, CIPHER models financial activity as a **dynamic graph network**, fusing graph topology, temporal dynamics, anomaly detection, predictive flow modeling, and explainable investigation tools.

---

## 🚨 The Problem

Financial crime often hides in the **complex connections between transactions and accounts**.

Traditional rule-based monitoring systems struggle with:

- **Transaction Fragmentation & Smurfing** — structuring small transfers below reporting thresholds.
- **Network Obscurity & Layering** — routing money through multiple intermediary accounts, shells, and mules.
- **Temporal Evasion** — spreading suspicious behavior across weeks or months to evade short-term windows.
- **Alert Fatigue** — overwhelming compliance teams with thousands of isolated false positives.
- **Manual Reconstruction** — tracing multi-hop fund flows across fragmented spreadsheets and logs.

> **What if investigators could see the suspicious network before it finishes forming?**

---

## 💡 The Solution

CIPHER constructs a **Financial Digital Twin** of transaction activity, enabling investigators to explore, analyze, and simulate complex financial topologies.

```text
                     Financial Transactions (CSV / Stream)
                                     │
                                     ▼
                          ┌─────────────────────┐
                          │     CIPHER Engine   │
                          │ Transaction-to-Graph│
                          └──────────┬──────────┘
                                     │
                 ┌───────────────────┼───────────────────┐
                 ▼                   ▼                   ▼
       Topology & Clusters   Temporal Sequences   Account Flow Metrics
        (Connected Comp.)     (Time Windows)      (In / Out / Degrees)
                 │                   │                   │
                 └───────────────────┼───────────────────┘
                                     │
                                     ▼
                          ┌─────────────────────┐
                          │ Interactive Graph & │
                          │  Digital Twin Canvas │
                          └──────────┬──────────┘
                                     │
                    ┌────────────────┴────────────────┐
                    ▼                                 ▼
         Crime Pattern Detection           Entity & Flow Inspection
          (Cycles, Mules, Hubs)             (Accounts, Edges, Volume)
                    │                                 │
                    └────────────────┬────────────────┘
                                     │
                                     ▼
                         Investigation Center Leads
```

---

## ✨ Key Features

### 1. 🔗 Dynamic Graph Digital Twin
- Converts raw tabular transaction data into interactive nodes (accounts) and directed edges (transfers).
- Real-time physics simulation (force-directed canvas layout with repulsion, link spring tension, and centering forces).
- Smooth pan, zoom, drag-and-drop node manipulation, and high-DPI rendering.

### 2. 📊 Graph Analytics & Metrics
- **Cluster & Component Detection**: Discovers disconnected communities and isolated money flow rings using Union-Find algorithms.
- **Account-Level Profiles**: Dynamic calculation of total incoming volume, outgoing volume, transaction counts, and counterparty listings.
- **Global Network Stats**: Live tracking of total accounts, edge counts, gross transaction volume, and temporal coverage.

### 3. 🧪 Synthetic Investigation Scenarios & Custom Data Import
- Built-in multi-account laundering pattern demo (mule networks, layering rings, and aggregator hubs).
- **Custom CSV Ingestion**: Drag-and-drop or upload custom financial transaction CSV files with instant client-side validation and schema checks.

### 4. 🛡️ Investigation Center (Roadmap)
- Structural and behavioral risk scoring per network subgraph.
- Anomaly flagging and explainability traces (*"Why was this subgraph flagged?"*).
- Prioritized queue of investigation leads and automated AML reporting workflows.

---

## 📁 Repository Structure

```text
cipher_build_bank/
├── index.html              # HTML entry point with custom typography
├── package.json            # Project scripts and dependencies
├── tailwind.config.js      # Custom theme styling & dark mode tokens
├── tsconfig.json           # TypeScript configuration
├── vite.config.ts          # Vite build setup & path aliases (@/ -> src/)
└── src/
    ├── App.tsx             # Root component with routing and global layout
    ├── main.tsx            # Application bootstrapping
    ├── index.css           # Design tokens, fonts, and dark aesthetic styles
    ├── components/
    │   ├── GraphView.tsx   # Canvas-based interactive force-directed graph
    │   ├── Navbar.tsx      # Navigation bar and global footer
    │   ├── StatsBar.tsx    # Live network statistical summary banner
    │   └── UploadModal.tsx # CSV file upload modal with validation feedback
    ├── pages/
    │   ├── OverviewPage.tsx      # Platform overview & conceptual demo
    │   ├── NetworkPage.tsx       # Primary interactive network explorer
    │   ├── InvestigationPage.tsx # Pipeline preview & investigation center
    │   └── AboutPage.tsx         # Vision, core thesis, and architecture
    ├── graph/
    │   ├── buildGraph.ts         # Graph parsing, CSV ingestion & Union-Find
    │   └── forceSimulation.ts    # Custom multi-body physics simulation engine
    ├── data/
    │   └── demoData.ts           # Preloaded synthetic money flow scenario
    ├── types/
    │   └── index.ts              # Core TypeScript interfaces & schemas
    └── utils/
        └── format.ts             # Currency (INR/Standard) & date formatters
```

---

## 🚀 Getting Started

### Prerequisites
- **Node.js**: v18.0.0 or higher
- **npm** (or `pnpm` / `yarn`)

### Installation

1. **Clone the repository**:
   ```bash
   git clone <repo-url>
   cd cipher_build_bank
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Start the development server**:
   ```bash
   npm run dev
   ```
   Open your browser at `http://localhost:5173`.

### Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Starts the Vite local development server with HMR |
| `npm run build` | Compiles TypeScript and creates an optimized production build |
| `npm run preview` | Locally previews the production build output |
| `npm run typecheck` | Validates TypeScript types across the codebase |
| `npm run lint` | Runs ESLint to check for code style and syntax issues |

---

## 📥 CSV Data Ingestion Format

To upload your own transaction dataset in the **Network Explorer**, provide a CSV file with the following headers:

```csv
transaction_id,sender,receiver,amount,timestamp
TX_001,ACC_1001,ACC_2004,450000,2026-03-01T10:30:00Z
TX_002,ACC_2004,ACC_3009,220000,2026-03-01T11:15:00Z
TX_003,ACC_2004,ACC_4012,225000,2026-03-01T11:45:00Z
TX_004,ACC_3009,ACC_9999,215000,2026-03-02T09:00:00Z
TX_005,ACC_4012,ACC_9999,220000,2026-03-02T09:20:00Z
```

### Schema Specification
- `transaction_id` *(string)*: Unique identifier for each transaction record.
- `sender` *(string)*: Originating account ID / entity identifier.
- `receiver` *(string)*: Destination account ID / entity identifier.
- `amount` *(number)*: Numerical value of the transaction.
- `timestamp` *(ISO 8601 string / datetime)*: Date and time of transfer.

---

## 🛠️ Technology Stack

- **Framework & Runtime**: [React 18](https://react.dev/), [TypeScript](https://www.typescriptlang.org/), [Vite](https://vitejs.dev/)
- **Styling & Design System**: [Tailwind CSS](https://tailwindcss.com/) with high-contrast, dark glassmorphism palette and bespoke typography
- **Visualization**: HTML5 Canvas with custom force-directed graph algorithms (velocity Verlet integration, Coulomb repulsion, Hooke spring forces)
- **Icons**: [Lucide React](https://lucide.dev/)
- **Routing**: [React Router DOM v7](https://reactrouter.com/)

---

## 🗺️ Roadmap

- [x] High-performance canvas graph rendering and force-directed simulation
- [x] CSV transaction ingestion and schema validator
- [x] Interactive entity inspection (node profiles, edge details, connected subnets)
- [x] Connected components and graph topology analytics
- [ ] Automated cycle detection (circular routing & layering loops)
- [ ] Smurfing and fan-in/fan-out anomaly detectors
- [ ] Risk scoring engine with explainability traces
- [ ] Exportable investigative case reports (PDF / JSON)
- [ ] Time-lapse replay slider for dynamic temporal evolution

---

## 📄 License

This project is licensed under the MIT License.
