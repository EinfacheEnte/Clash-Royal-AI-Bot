# Clash Royal AI 🏰⚔️

A sophisticated AI-powered bot for Clash Royale that uses machine learning to defeat human opponents. Built to run on ARM-based macOS systems and interact with the game via Bluestacks Air Android emulator.

---

## 🎯 Project Goal

To develop a self-learning AI agent capable of playing Clash Royale autonomously, making strategic decisions in real-time battles, and defeating human opponents through advanced machine learning techniques.

---

## 🚀 Current Progress

| Component | Status | Description |
|-----------|--------|-------------|
| Project Setup | ✅ Complete | Initial repo created with README |
| Architecture Design | 📋 In Planning | Detailed roadmap defined |
| Bluestacks Integration | ⏳ Pending | A11y/ADB hook implementation |
| Game State Parser | ⏳ Pending | Extracting game state data |
| Card Database | ⏳ Pending | Comprehensive card library |
| ML Model | ⏳ Pending | Reinforcement learning agent |
| Decision Engine | ⏳ Pending | Strategic decision making |

---

## 🗺️ Implementation Roadmap

### Phase 1: Foundation (Week 1-2)

#### 1.1 Project Setup
- [x] Initialize Git repository
- [ ] Create project directory structure
- [ ] Set up virtual environment
- [ ] Create requirements.txt
- [ ] Add pre-commit hooks

#### 1.2 Bluestacks Integration
- [ ] Install Bluestacks Air
- [ ] Configure ADB connection
- [ ] Install Clash Royale on emulator
- [ ] Implement screen capture via A11y
- [ ] Create A11y binding scripts
- [ ] Implement mouse/keyboard control

#### 1.3 Game State Parser
- [ ] Screen capture pipeline
- [ ] Base detection (king tower, princess towers)
- [ ] Card position detection (enemy/ally units)
- [ ] Elixir bar reading
- [ ] Log cabin detection
- [ ] Bridge spell detection
- [ ] Arena map boundaries

### Phase 2: Card Database (Week 2-3)

#### 2.1 Card Information
- [ ] Scrape/compile all 100+ cards
- [ ] Card rarities (Common, Rare, Epic, Legendary)
- [ ] Elixir costs (1-10)
- [ ] Attack types (Basic, Splash, Area)
- [ ] Speed & DPS stats
- [ ] Health & duration
- [ ] Spell ranges
- [ ] Special abilities

#### 2.2 Deck Management
- [ ] Legal deck validator (8 cards max)
- [ ] Deck rarity balance checker
- [ ] Synergy analysis
- [ ] Common counter-picks

### Phase 3: Decision Engine (Week 3-5)

#### 3.1 Rules-Based Engine
- [ ] Threat assessment (elixir advantage)
- [ ] Position analysis (side/center)
- [ ] Priority targeting (priority targets)
- [ ] Card timing (elixir efficiency)
- [ ] Bridge logistics detection
- [ ] Push recognition

#### 3.2 ML Model Architecture
- [ ] State representation design
- [ ] Neural network architecture
- [ ] Action space definition
- [ ] Loss function design
- [ ] Reward function design

#### 3.3 Training Infrastructure
- [ ] Replay system setup
- [ ] Data augmentation
- [ ] Training loop implementation
- [ ] Model checkpointing
- [ ] Validation pipeline

### Phase 4: Game Controller (Week 4-6)

#### 4.1 Action Execution
- [ ] Troop deployment via A11y
- [ ] Spell casting
- [ ] Building construction
- [ ] Log cabin placement
- [ ] Action queue management

#### 4.2 Error Handling
- [ ] Anti-cheat detection
- [ ] Game pause/resume handling
- [ ] Disconnection recovery
- [ ] Invalid action recovery

### Phase 5: ML Training Loop (Week 5-8)

#### 5.1 Data Collection
- [ ] Self-play training
- [ ] Human opponent data
- [ ] Win/loss logging
- [ ] Replay recording

#### 5.2 Training Pipeline
- [ ] PPO implementation (preferred)
- [ ] OR DQN implementation
- [ ] Model fine-tuning
- [ ] Transfer learning
- [ ] Knowledge distillation

#### 5.3 Model Evaluation
- [ ] Metrics: Win rate, avg games, elo
- [ ] Elo rating system
- [ ] Performance benchmarks
- [ ] Human vs bot comparison

### Phase 6: Advanced Features (Week 8+)

#### 6.1 Strategy Recognition
- [ ] Opponent pattern detection
- [ ] Meta analysis
- [ ] Counter-strategy adaptation
- [ ] Rock-paper-scissors dynamics

#### 6.2 Self-Improvement
- [ ] Online learning
- [ ] Continuous training
- [ ] Knowledge sharing
- [ ] Multi-agent training

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                    Clash Royale AI Bot                       │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  ┌─────────────────┐    ┌──────────────────┐    ┌─────────┐│
│  │   A11y Hook     │    │   Game           │    │   Deck   ││
│  │   Layer         │───▶│   State          │───▶│   Manager││
│  │  (Bluestacks)   │    │   Parser         │    │          ││
│  └─────────────────┘    └──────────────────┘    └─────────┘│
│         │                    │                       │      │
│         ▼                    ▼                       ▼      │
│  ┌─────────────────────────────────────────────────────┐   │
│  │               ML Decision Engine                     │   │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐ │   │
│  │  │  State      │  │  Action     │  │  Elixir      │ │   │
│  │  │  Embedding  │  │  Selector   │  │  Management  │ │   │
│  │  └─────────────┘  └─────────────┘  └─────────────┘ │   │
│  └─────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌─────────────────┐    ┌──────────────────┐    ┌─────────┐│
│  │   Card          │    │   Opponent       │    │   Log    ││
│  │   Database      │◀───│   Analysis        │◀───│   Buffer ││
│  │   (100+ cards)  │    │   (Strategy       │    │          ││
│  │                  │    │    Recognition)   │    │          ││
│  └─────────────────┘    └──────────────────┘    └─────────┘│
│                                                               │
└─────────────────────────────────────────────────────────────┘
```

---

## 📋 Technical Stack

| Layer | Technology | Purpose |
|-------|-------|--------|
| **Language** | Python 3.10+ | Primary programming language |
| **ML Framework** | PyTorch | Deep learning model |
| **A11y Access** | Selenium/Playwright | Game screen capture & control |
| **ADB** | Android Debug Bridge | Emulator communication |
| **Image Processing** | OpenCV | Visual state analysis |
| **Data Storage** | SQLite/PostgreSQL | Game logs & training data |
| **Model Serving** | TorchServe | Deployment & inference |

---

## 🧠 Machine Learning Approach

### Model Architecture

```
Input: Game State (Visual + Structured)
│
├─ Visual Stream (CNN)
│  └─ Screen capture → Feature extraction
│
└─ Structured Stream (MLP)
   ├─ Card positions
   ├─ Elixir count
   ├─ Active units
   ├─ Arena position
   │
   └─ Fusion Layer
      └─ Decision head → Action selection
```

### Reward Function

```
R = w1 * win_loss + w2 * push_prevented + w3 * base_hit
   - w4 * cards_left - w5 * towers_destroyed
```

### Training Strategy

1. **Pre-training**: Play against random bot (100k games)
2. **Fine-tuning**: Self-play improvement (1M+ games)
3. **Human-adaptation**: Learn from human playstyles
4. **Continuous learning**: Online updates after sessions

---

## 📊 Metrics & KPIs

| Metric | Target | Current |
|--------|--------|---------|
| Win Rate vs Humans | >55% | - |
| Win Rate vs Self | >60% | - |
| Avg Games Per Session | 5-10 | - |
| Decision Latency | <100ms | - |
| Model Accuracy | >85% | - |

---

## 📁 Project Structure

```
Clash-Royal-AI-Bot/
├── README.md
├── requirements.txt
├── config.yaml
├── src/
│   ├── __init__.py
│   ├── hooks/
│   │   ├── __init__.py
│   │   ├── base.py
│   │   ├── bluestacks_a11y.py
│   │   └── adb.py
│   ├── parser/
│   │   ├── __init__.py
│   │   ├── state.py
│   │   ├── cards.py
│   │   ├── elixir.py
│   │   └── position.py
│   ├── model/
│   │   ├── __init__.py
│   │   ├── architecture.py
│   │   ├── trainer.py
│   │   └── predictor.py
│   ├── decision/
│   │   ├── __init__.py
│   │   ├── engine.py
│   │   ├── heuristics.py
│   │   └── strategies.py
│   ├── deck/
│   │   ├── __init__.py
│   │   ├── manager.py
│   │   └── database.py
│   └── utils/
│       ├── __init__.py
│       ├── logging.py
│       └── helpers.py
├── data/
│   ├── cards.json
│   ├── replays/
│   └── logs/
├── models/
│   └── checkpoints/
└── tests/
    └── unit/
```

---

## 🔧 Setup Instructions

### Prerequisites

- macOS with ARM architecture (M1/M2/M3)
- Python 3.10+
- 16GB+ RAM
- Clash Royale installed on Bluestacks Air

### Installation

```bash
# Clone repository
git clone https://github.com/EinfacheEnte/Clash-Royal-AI-Bot.git
cd "Clash Royal AI"

# Create virtual environment
python -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Configure Bluestacks
# 1. Enable A11y bindings
# 2. Install Clash Royale
# 3. Run setup script
python setup.py --init
```

---

## 👥 Contributing

Contributions welcome! See contributing guidelines for details.

---

## 📄 License

MIT License

---

## 🏷️ Tags

`#clash-royale` `#ai` `#machine-learning` `#automation` `#python` `#bluestacks`

---

*Built with ❤️ by EinfacheEnte*
