# Changelog

All notable changes to AutomotiveGPT will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-02-02

### Added
- Initial release of AutomotiveGPT
- Hybrid retrieval system (dense + sparse + reranking)
- 5 vehicle manuals indexed (1,708 pages total):
  - Honda Civic 2022 Owner's Manual
  - Toyota Camry 2023 Owner's Manual
  - Ford F-150 2021 Owner's Manual
  - Tesla Model 3 2023 Owner's Manual
  - Honda Civic 2022-2025 Safety Recall Report
- FastAPI REST API with /chat endpoint
- Streamlit web interface
- Multi-turn conversation support
- Citation tracking with source document + page number
- Docker deployment configuration
- Comprehensive test suite (20 test queries)

### Performance
- 90% success rate (18/20 test queries)
- 85% document retrieval accuracy
- 95% citation rate
- 8.84s average latency
- 21.29s P95 latency
- $0.045 average cost per query

### Known Issues
- Occasional timeouts (~10% of queries) on OpenAI free tier
- Will be addressed in v1.1 with retry logic

---

## [Unreleased]

### In Progress (v1.1)
- Retry logic for API timeouts
- Parallel retrieval for faster responses
- Persistent BM25 cache

[1.0.0]: https://github.com/YOUR_USERNAME/automotive-gpt/releases/tag/v1.0.0
