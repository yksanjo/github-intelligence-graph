# GitHub Intelligence Graph 🕸️

A high-compute scraping project that builds a developer influence graph from GitHub data. Extract relationships between repositories, developers, organizations, and trace influence propagation through the open-source ecosystem.

## 🎯 Project Overview

**Goal**: Build a comprehensive knowledge graph of the GitHub ecosystem to analyze:
- Developer influence and expertise propagation
- Technology trend heatmaps
- Early signal detection for breakout repositories
- Technical due diligence for projects

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    GitHub Intelligence Graph                │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────┐   │
│  │   Scraper   │  │   Graph     │  │   Analytics     │   │
│  │   Engine    │──▶│   Store     │──▶│   Engine        │   │
│  └─────────────┘  │  (Neo4j)    │  └─────────────────┘   │
│                   └─────────────┘                          │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────┐   │
│  │  GitHub API │  │  Vector DB  │  │   Visualizer    │   │
│  │  + Raw HTML │  │ (Pinecone)  │  │   (D3.js)       │   │
│  └─────────────┘  └─────────────┘  └─────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

## 📊 Data Sources

- **Public Repositories**: Stars, forks, issues, PRs, releases
- **Developer Profiles**: Contributions, followers, organizations
- **Commit History**: Author patterns, contribution graphs
- **Issues & PRs**: Activity timelines, sentiment
- **Release Notes**: Changelog extraction

## 🔧 Tech Stack

- **Language**: Python + TypeScript
- **Graph Database**: Neo4j
- **Vector Store**: Pinecone / Qdrant
- **API**: FastAPI (Python) + Express (TypeScript)
- **Queue**: Redis + BullMQ
- **Embeddings**: CodeBERT, GraphCodeBERT

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/yksanjo/github-intelligence-graph.git
cd github-intelligence-graph

# Install dependencies
pip install -r requirements.txt

# Set up environment
cp .env.example .env
# Edit .env with your GitHub token

# Run the scraper
python src/scraper/github_scraper.py

# Start the API
uvicorn src.api.main:app --reload
```

## 📈 Features

- [ ] GitHub API integration with rate limiting
- [ ] Neo4j graph storage
- [ ] Code embeddings generation
- [ ] Developer influence scoring
- [ ] Technology trend analysis
- [ ] Interactive D3.js visualization
- [ ] Real-time webhook updates

## 📊 Project Phases

### Phase 1: Data Collection
- GitHub API scraper for top 10K repos
- Metadata extraction (stars, forks, contributors)
- Commit history analysis

### Phase 2: Graph Building
- Neo4j schema design
- Entity resolution
- Relationship mapping

### Phase 3: Intelligence
- Code embeddings
- Influence algorithms
- Trend detection

### Phase 4: Visualization
- D3.js interactive graphs
- Dashboard analytics

## 📝 License

MIT License - See [LICENSE](LICENSE) for details.

## 👤 Author

Yoshi Kondo - [@yksanjo](https://github.com/yksanjo)

---

🌟 Star us on GitHub if you find this interesting!
