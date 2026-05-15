# fastapi-hr-analytics-service

Production-grade Python microservice for AI-powered HR analytics.

## Architecture
- FastAPI REST endpoints for candidate scoring and resume parsing
- Async task queues via Celery + RabbitMQ for batch ML inference
- spaCy NLP model for resume parsing (28% accuracy improvement over rule-based)
- Redis caching layer for sub-6s report generation (down from 45s)

## Running locally
```bash
docker-compose up --build
# API available at http://localhost:8000
# Docs at http://localhost:8000/docs
```

## Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /parse-resume | Extract structured data from resume PDF |
| POST | /match-candidates | Score candidates against job description |
| GET | /analytics/attrition | Predict employee attrition risk |

## Tech stack
FastAPI · PostgreSQL · Redis · Celery · RabbitMQ · Docker · AWS ECS · spaCy · scikit-learn
