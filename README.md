# 🔬 Scientific Consensus Engine

**NextGen BioAgents — Nucleate NYC BioHack 2026**
[![Nebius](https://img.shields.io/badge/Powered%20by-Nebius%20Token%20Factory-6B46C1)](https://tokenfactory.nebius.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> A multi-agent system that continuously ingests scientific literature, debates hypotheses through adversarial consensus, and surfaces novel drug targets — powered by Nebius Token Factory + Consensus Hardening Protocol.

---

## 🏆 Challenge Track: Research Agent

> *"Agents that continuously ingest scientific papers, patents, and preprints; identify gaps in existing knowledge; generate novel hypotheses; and update their conclusions as new data emerges."*

## 🚀 Built With

| Component | Technology |
|-----------|-----------|
| **LLM Inference** | [Nebius Token Factory](https://tokenfactory.nebius.com/) — DeepSeek V3.2 / Llama 3.3-70B |
| **Consensus Framework** | [Consensus Hardening Protocol](https://codeberg.org/cubiczan/consensus-hardening-protocol) |
| **Multi-Agent Swarm** | Cubiczan Swarm Pack — stigmergy + PARL + adversarial debate |
| **RAG Pipeline** | Nebius Qwen3-Embedding-8B + PGVector |
| **Tools** | Nebius function calling for PubMed, arxiv, Uniprot APIs |

## ✨ Key Features

| Capability | Details |
|---|---|
| **Literature Ingestion** | Auto-fetches papers from PubMed, arXiv, bioRxiv via function calling |
| **Adversarial Hypothesis Debate** | 3 agent personas debate a scientific claim — Optimist, Skeptic, Validator |
| **Consensus Locks** | CHP EXPLORING → PROVISIONAL_LOCK → LOCKED progression with auditable trails |
| **Gap Analysis** | Surfaces underexplored research directions with confidence scores |
| **Live Updating** | Re-checks conclusions as new papers are published |

## 🏗 Architecture

```
                     ┌──────────────────────────────────────┐
  Papers ───────────>│       Context Engine (PGVector)       │
  PubMed, arXiv      │  Paper embeddings + structured claims │
                     └──────────────────┬───────────────────┘
                                        │
                                        ▼
                     ┌──────────────────────────────────────┐
                     │       Multi-Agent Debate Arena        │
                     │                                        │
              ┌──────┴──────┐  ┌──────┴──────┐  ┌──────┴──────┐
              │  Optimist   │  │  Skeptic    │  │  Validator  │
              │  Agent      │  │  Agent      │  │  Agent      │
              │ (supports)  │  │ (challenges)│  │ (evidence)  │
              └──────┬──────┘  └──────┬──────┘  └──────┬──────┘
                     │                │                │
                     └────────────────┼────────────────┘
                                      ▼
                     ┌──────────────────────────────────────┐
                     │  Consensus Hardening Protocol (CHP)   │
                     │  R0 Gate → EXPLORING → PROVISIONAL   │
                     │  → LOCKED (auditable, hash-stamped)  │
                     └──────────────────────────────────────┘
                                      │
                                      ▼
                     ┌──────────────────────────────────────┐
                     │   Research Brief: Hypothesis,        │
                     │   Evidence, Confidence, Novelty      │
                     └──────────────────────────────────────┘
```

## 🔧 How It Uses Nebius Token Factory

1. **DeepSeek V3.2** — Heavy reasoning for adversarial debate rounds (each agent uses its own chain-of-thought)
2. **Llama 3.3-70B** — Orchestrator + synthesis agent for final research brief
3. **Function Calling** — PubMed search, arXiv fetch, Uniprot protein lookup via Nebius tools
4. **Qwen3-Embedding-8B** — Paper embeddings for RAG on 10,000+ documents
5. **Structured JSON** — All debate rounds, evidence citations, and consensus locks output as machine-verifiable JSON

## 🎥 Demo Video (3 min)

### Script Outline:
1. **0:00-0:30** — Problem: Scientific literature doubles every 12 years. No one can keep up.
2. **0:30-1:00** — Input a hypothesis: "TRAF2 mediates resistance to CAR-T therapy via NF-κB signaling"
3. **1:00-1:45** — 3 agents debate, each citing papers — watch them discover a novel connection to IL-6
4. **1:45-2:30** — CHP hardens the consensus: EXPLORING → PROVISIONAL_LOCKED → human review
5. **2:30-3:00** — Output: research brief with gap analysis for novel drug targets

## 🚀 Quick Start

```bash
# Clone
git clone https://github.com/cubiczan/scientific-consensus-engine
cd scientific-consensus-engine

export NEBIUS_API_KEY="your-key-here"

# Ingest papers on a topic
python pipeline.py --topic "CAR-T therapy resistance mechanisms"

# Run debate
python debate.py --hypothesis "TRAF2 mediates CAR-T resistance via NF-κB"

# View consensus report
python synthesize.py --session latest
```

---

*Built at Nucleate NYC BioHack: NextGen BioAgents — June 6, 2026*
