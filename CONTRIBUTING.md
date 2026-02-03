# Contributing to AutomotiveGPT

Thank you for considering contributing to AutomotiveGPT! 🎉

This project aims to build the open-source standard for automotive technical documentation retrieval, and we need your help to make it better.

## 🚀 Quick Links

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)

---

## How Can I Contribute?

### 🐛 Report Bugs

Found a bug? [Open a bug report](https://github.com/sreekarvamsi/automotive-gpt/issues/new?template=bug_report.md)

**Before submitting:**
- Check if the issue already exists
- Include steps to reproduce
- Share error messages and logs
- Specify your environment (OS, Python version, etc.)

### 💡 Suggest Features

Have an idea? [Request a feature](https://github.com/sreekarvamsi/automotive-gpt/issues/new?template=feature_request.md)

**Good feature requests include:**
- Clear use case description
- Expected behavior
- Why this would be valuable

### 📖 Add Vehicle Manuals

Have automotive PDFs to contribute?

1. Ensure they're **legally shareable** (public domain, your own, or with permission)
2. Add them to the `data/` folder
3. Run ingestion: `python scripts/ingest.py --source data/your-manual.pdf`
4. Submit a PR with the ingestion results

### 💻 Submit Code

1. **Fork** the repository
2. **Create a branch:** `git checkout -b feature/YourFeature`
3. **Make changes** and commit: `git commit -m 'Add YourFeature'`
4. **Push:** `git push origin feature/YourFeature`
5. **Open a Pull Request**

---

## Development Setup

### Prerequisites

- Python 3.10+
- Docker (optional, for full stack)
- API keys: OpenAI, Pinecone, Cohere

### Installation
```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/automotive-gpt.git
cd automotive-gpt

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Copy environment template
cp .env.example .env
# Edit .env and add your API keys

# Start infrastructure
docker-compose up -d postgres redis

# Run tests
pytest tests/ -v
```

### Running Locally
```bash
# Start API server
uvicorn src.api.main:app --reload

# In another terminal, start Streamlit UI
streamlit run src/ui/app.py
```

---

## Pull Request Process

### Before Submitting

- [ ] Code follows [PEP 8](https://pep8.org/) style guidelines
- [ ] Added tests for new features
- [ ] All tests pass: `pytest tests/ -v`
- [ ] Updated documentation if needed
- [ ] Added your changes to `CHANGELOG.md`

### PR Checklist

1. **Title:** Clear, descriptive (e.g., "Fix: timeout handling in generation")
2. **Description:** Explain what and why
3. **Link issues:** Use "Fixes #123" or "Closes #456"
4. **Screenshots:** If UI changes, include before/after

### Review Process

- PRs are typically reviewed within 48 hours
- Maintainers may request changes
- Once approved, your PR will be merged!

---

## Style Guidelines

### Python Code

- **PEP 8 compliance:** Use `black` for formatting
- **Type hints:** Add type hints to all functions
- **Docstrings:** Use Google-style docstrings
```python
def retrieve_documents(query: str, top_k: int = 10) -> list[Document]:
    """Retrieve relevant documents for a query.
    
    Args:
        query: The search query string
        top_k: Number of documents to return
        
    Returns:
        List of retrieved documents sorted by relevance
    """
    pass
```

### Commit Messages

Format: `<type>: <description>`

Types:
- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation changes
- `test:` Test additions/changes
- `refactor:` Code refactoring
- `chore:` Maintenance tasks

Examples:
- `feat: add retry logic for API timeouts`
- `fix: comparison queries not retrieving multiple documents`
- `docs: update installation instructions`

### Testing

- Write tests for new features
- Maintain >80% code coverage
- Run the test suite before submitting: `pytest tests/ -v --cov=src`

---

## Code of Conduct

### Our Standards

- Be respectful and inclusive
- Welcome newcomers
- Focus on constructive feedback
- Assume good intentions

### Unacceptable Behavior

- Harassment or discrimination
- Trolling or insulting comments
- Publishing others' private information
- Other unprofessional conduct

### Enforcement

Violations can be reported to [srikarkrishnag@gmail.com]. All complaints will be reviewed and investigated.

---

## Questions?

- **General questions:** [Open a Discussion](https://github.com/sreekarvamsi/automotive-gpt/discussions)
- **Bug reports:** [Open an Issue](https://github.com/sreekarvamsi/automotive-gpt/issues)
- **Twitter:** [@srikarkrishnag](https://twitter.com/@srikarkrishnag)

---

Thank you for contributing! 🚗💨
