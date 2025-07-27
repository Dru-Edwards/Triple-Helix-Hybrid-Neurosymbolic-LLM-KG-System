# Triple-Helix Hybrid Neurosymbolic LLM-KG System

**A Professional, Scalable AI System with Pluggable Domain Specialization**

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://python.org)
[![Docker](https://img.shields.io/badge/Docker-Ready-blue.svg)](https://docker.com)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Tests](https://img.shields.io/badge/Coverage-90%25-brightgreen.svg)](tests/)

A complete neurosymbolic AI system that integrates multiple quantized LLMs with knowledge graphs, virtue-based orchestration, and comprehensive safety mechanisms. Features a **pluggable specialty template system** for domain-specific deployments and professional-grade deployment infrastructure.

---

## 🚀 **Quick Start (Choose Your Path)**

### **Option 1: One-Click Installation (Recommended)**

```bash
# Clone and install
git clone https://github.com/your-org/triple-helix.git
cd triple-helix
python install.py --type=development

# Start the system
./start_triplehelix.sh  # Linux/Mac
# or
start_triplehelix.bat   # Windows
```

### **Option 2: Docker Deployment (Production)**

```bash
# Full production stack with monitoring
docker compose -f docker/docker-compose.yml up -d

# Access services:
# - Triple-Helix API: http://localhost:8080
# - Neo4j Browser: http://localhost:7474
# - Grafana Dashboard: http://localhost:3000
```

### **Option 3: Manual Setup**

```bash
# Install dependencies
pip install -r requirements.txt

# Initialize system
python scripts/seed_kg.py

# Start application
python src/app.py --config=development
```

---

## 🎯 **Core Architecture**

### **Neurosymbolic Foundation**
- **Knowledge Graph Spine**: Neo4j + FAISS vector indexing for semantic reasoning
- **Graph Neural Network**: PyTorch Geometric virtue-weighted GNN for dynamic knowledge weighting
- **Multi-LLM Orchestration**: Support for 3-8 quantized INT4 models (Gemma-2-2b, Phi-3-mini)
- **Virtue Pillars**: Logic, Empathy, and Authenticity meta-agents with entropy-guarded softmax

### **AI Safety & Quality Assurance**
- **Watchdog Systems**: Real-time hallucination and bias detection with configurable thresholds
- **Debate Engine**: Multi-agent deliberation with Habermasian discourse ethics
- **Virtue Alignment**: Dynamic balancing prevents overconfident assertions
- **Entropy Guards**: Maintains virtue balance with H(w) ≥ 0.8 threshold

### **Professional Features**
- **Pluggable Templates**: Domain-specific specialization without code changes
- **Comprehensive Monitoring**: Prometheus metrics + Grafana dashboards
- **Scalable Deployment**: Docker-based horizontal scaling
- **Enterprise Security**: Audit logging, compliance features, role-based access

---

## 🎨 **Template System (Domain Specialization)**

The system features a **pluggable specialty template system** that allows easy domain adaptation:

### **Available Templates**

```bash
# List available domain templates
python src/cli/template_manager.py templates list

# Example output:
# ├── default        - General-purpose template
# ├── healthcare     - Medical and clinical applications
# ├── legal_research - Legal analysis and compliance
# ├── education      - Educational content and tutoring
# └── financial      - Financial analysis and reporting
```

### **Quick Template Usage**

```bash
# Apply a domain template
python src/cli/template_manager.py templates apply healthcare

# Restart system with new specialization
python src/app.py --config=active

# Query with domain expertise
# > "What are the contraindications for this medication?"
# System now responds with medical virtue weighting and safety protocols
```

### **Create Custom Templates**

```bash
# Create new domain template
python src/cli/template_manager.py templates create legal_research \
  --author="Legal Team" \
  --description="Legal research and compliance" \
  --logic-weight=0.5 \
  --empathy-weight=0.2 \
  --authenticity-weight=0.3

# Customize knowledge graph, prompts, and safety rules
# Templates located in: templates/legal_research/
```

---

## 🖥️ **Usage Examples**

### **Interactive Query Session**

```bash
# Start interactive mode
python src/app.py --interactive

# Example conversation:
> "Analyze the ethical implications of AI in healthcare"

🤖 [Logic Pillar]: Examining regulatory frameworks and technical capabilities...
💝 [Empathy Pillar]: Considering patient privacy and healthcare accessibility...
🎯 [Authenticity Pillar]: Reviewing current research and real-world implementations...

⚖️ [Debate Engine]: Synthesizing perspectives through discourse ethics...
📊 [Virtue Alignment]: Logic: 0.4, Empathy: 0.4, Authenticity: 0.2

[Comprehensive analysis follows...]
```

### **API Usage**

```python
from src.app import TripleHelixSystem
from config import CONFIG

# Initialize system
system = TripleHelixSystem(CONFIG)

# Submit query
response = system.query(
    "What are the latest developments in quantum computing?",
    context_images=["quantum_circuit.png"],
    specialty="technology"
)

# Access detailed metrics
print(f"Virtue Alignment: {response.virtue_scores}")
print(f"Safety Flags: {response.safety_flags}")
print(f"Debate Rounds: {response.debate_rounds}")
```

### **Batch Processing**

```bash
# Process multiple queries from file
python src/cli/batch_processor.py \
  --input queries.json \
  --output results.json \
  --template healthcare \
  --format detailed
```

---

## 📊 **Performance Metrics**

### **System Benchmarks**

```bash
# Run comprehensive benchmarks
python scripts/benchmark.py

# Performance targets:
# ✅ Accuracy: ≥90% on multi-hop KGQA
# ✅ Virtue Alignment: ≥80% coherence
# ✅ Latency: <10s per query
# ✅ VRAM: <12GB peak usage
# ✅ Entropy Guard: H(w) ≥ 0.8
```

### **Real-time Monitoring**

```bash
# Access monitoring dashboard
open http://localhost:3000  # Grafana
open http://localhost:9090  # Prometheus

# CLI monitoring
python src/cli/monitor.py --live
```

---

## 🏗️ **Repository Structure**

```
triple_helix/
├── src/                    # Core system implementation
│   ├── kg/                 # Knowledge Graph + GNN
│   ├── llm/                # LLM nodes and pillars
│   ├── debate/             # Watchdogs and debate engine
│   ├── metrics/            # Logging and evaluation
│   ├── cli/                # Command-line interface
│   └── app.py              # Main application entry
├── templates/              # Domain specialty templates
│   ├── default/            # General-purpose template
│   ├── healthcare/         # Medical domain template
│   └── legal_research/     # Legal domain template
├── docker/                 # Docker deployment files
│   ├── Dockerfile          # Multi-stage container build
│   ├── docker-compose.yml  # Full stack deployment
│   └── config/             # Environment configurations
├── scripts/                # Installation and utilities
│   ├── install.sh          # System installation
│   ├── seed_kg.py          # Knowledge graph seeding
│   └── benchmark.py        # Performance benchmarking
├── tests/                  # Comprehensive test suite
│   ├── unit/               # Unit tests (≥90% coverage)
│   ├── integration/        # Integration tests
│   └── templates/          # Template-specific tests
├── config/                 # Configuration files
├── install.py              # One-click installer
├── DEPLOYMENT_GUIDE.md     # Comprehensive deployment guide
├── SYSTEM_ANALYSIS.md      # System capabilities analysis
└── README.md               # This file
```

---

## 🔧 **Configuration**

### **Environment Variables**

```bash
# Core Configuration
export TRIPLE_HELIX_ENV=production
export TRIPLE_HELIX_LOG_LEVEL=info

# Database Configuration
export NEO4J_URI=bolt://localhost:7687
export NEO4J_USER=neo4j
export NEO4J_PASSWORD=your_password

# Performance Tuning
export VRAM_LIMIT_GB=16
export MAX_DEBATE_ROUNDS=10
export ENABLE_GPU=true
```

### **Configuration Files**

```json
{
  "environment": "production",
  "max_debate_rounds": 10,
  "vram_limit_gb": 16,
  "virtue_weights": {
    "Logic": 0.33,
    "Empathy": 0.33,
    "Authenticity": 0.34
  },
  "safety_thresholds": {
    "hallucination_threshold": 0.1,
    "bias_detection_sensitivity": 0.8
  }
}
```

---

## 🚀 **Deployment Options**

### **Development Environment**

```bash
# Quick development setup
python install.py --type=development
python src/app.py --config=development --debug
```

### **Production Deployment**

```bash
# Full production stack
docker compose -f docker/docker-compose.yml up -d

# Scale horizontally
docker compose -f docker/docker-compose.yml up -d --scale triple-helix=3
```

### **Cloud Deployment**

```bash
# AWS/GCP/Azure deployment
# See DEPLOYMENT_GUIDE.md for detailed instructions
```

---

## 📚 **Documentation**

| Document | Description |
|----------|-------------|
| [DEPLOYMENT_GUIDE.md](DEPLOYMENT_GUIDE.md) | Comprehensive deployment and template guide |
| [SYSTEM_ANALYSIS.md](SYSTEM_ANALYSIS.md) | System capabilities and limitations |
| [API_REFERENCE.md](docs/API_REFERENCE.md) | Complete API documentation |
| [TEMPLATE_GUIDE.md](docs/TEMPLATE_GUIDE.md) | Template development guide |

---

## 🧪 **Testing**

```bash
# Run all tests
python -m pytest tests/ -v

# Run with coverage
python -m pytest tests/ --cov=src --cov-report=html

# Test specific template
python -m pytest tests/templates/test_healthcare.py

# Integration tests
python -m pytest tests/integration/ -v
```

---

## 🛡️ **Security & Compliance**

- **Audit Logging**: Comprehensive audit trails for all system interactions
- **Access Control**: Role-based permissions and authentication
- **Data Privacy**: GDPR/HIPAA compliance features available
- **Secrets Management**: Environment-based credential handling
- **Vulnerability Scanning**: Automated security scanning in CI/CD

---

## 🤝 **Contributing**

1. **Fork the repository**
2. **Create feature branch**: `git checkout -b feature/new-template`
3. **Add tests**: Ensure ≥90% coverage
4. **Format code**: `black src/ && ruff check src/`
5. **Submit PR**: Include template documentation

### **Template Contributions**

```bash
# Create new template
python src/cli/template_manager.py templates create my_domain

# Test template
python -m pytest tests/templates/test_my_domain.py

# Submit for review
git add templates/my_domain/
git commit -m "Add my_domain specialty template"
```

---

## 📞 **Support**

- **Documentation**: Comprehensive guides in `/docs`
- **Issues**: GitHub issue tracker
- **Discussions**: Community discussions and Q&A
- **Enterprise**: Professional support available

---

## 🎯 **Roadmap**

- [ ] **Multi-language Support**: Expand beyond English
- [ ] **Cloud Templates**: AWS/GCP/Azure deployment templates
- [ ] **GUI Interface**: Web-based template management
- [ ] **Federated Learning**: Distributed model training
- [ ] **Advanced Metrics**: Custom domain-specific metrics

---

## 📄 **License**

see the [LICENSE](LICENSE) file for details.

---

## 🏆 **Acknowledgments**

- Built with virtue-based AI principles
- Implements neurosymbolic architecture
- Follows enterprise-grade security practices
- Designed for professional deployment

---

**Ready to transform your AI deployment? Get started with the one-click installer!**

```bash
python install.py --type=production
```
