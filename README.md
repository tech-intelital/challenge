# Ecological Resource Competition Mapper

API service that discovers ecological competition relationships from species descriptions using text analysis and graph data structures.

## Setup & Configuration

**Important:** You are free to modify, add, or restructure any files in this starter template. The provided structure is just a starting point, adapt it to your preferred architecture and approach.

## Quick Start

```bash
npm install
npm run setup-db
npm run load-data
npm start
```

## API Endpoints

### Species Competition

```bash
GET /api/species/{species-name}/competitions
```

### Graph Data

```bash
GET /api/graph/species/{species-name}
```

Returns nodes/edges structure for visualization tools.

### Search

```bash
GET /api/search?q={query}
```

## Data Structure

**Input:** `data/ecosystem_dataset.json` - 50+ species with ecological descriptions

**Output:** Structured competition relationships with confidence scores

```json
{
  "competing_species": "Brown Bear",
  "resource_type": "prey",
  "specific_resource": "elk carcasses",
  "competition_intensity": 0.8,
  "seasonal_factor": "winter_months",
  "confidence": 0.9
}
```

## Suggested Architecture

_Note: This is a suggested structure - feel free to organize your code however you prefer._

```
src/
├── api/          # REST endpoints
├── services/     # Text processing & relationship extraction
├── models/       # Neo4j database models
├── utils/        # NLP utilities
└── mock/         # LLM integration mocks
```

## Technical Approach

1. **Text Processing**: Extract species mentions from descriptions
2. **Relationship Classification**: Categorize competition types (food, water, territory)
3. **Confidence Scoring**: Rate extraction reliability
4. **Graph Structure**: Output nodes/edges for visualization
5. **Mock Enhancement**: Simulate LLM-powered analysis

## Development Notes

**Time Spent:** [Track your actual hours]

**Key Decisions:**

- [Document your architectural choices]
- [Trade-offs made given time constraints]
- [What you'd improve with more time]

**Challenges Encountered:**

- [Parsing challenges and solutions]
- [Edge cases handled]
- [Limitations acknowledged]

## Testing

```bash
npm test
npm run test:api
```

## Demo

[Link to demo video showing API functionality]
