# Ecological Resource Competition Mapper

A biological intelligence tool that automatically discovers and maps how plants and animals compete for essential resources like food, water, and territory.

## Overview

This system takes any plant or animal species as input and uses text analysis to discover their resource competition relationships from ecological descriptions. It returns structured graph data through REST API endpoints.

## Features

- **Smart Species Discovery**: Enter any species name and find all competing species from the dataset
- **Competition Detection**: Automatic text analysis to identify resource competition mentions
- **Intelligent Classification**: Categorizes competition types (food, water, territory, breeding resources)
- **Graph Data API**: Returns structured graph data for external visualization tools
- **API-Only Architecture**: No frontend included - pure backend service
- **LLM Enhancement**: Mocked LLM integration for enriched ecological insights

## Technical Stack

- **Backend**: Node.js + TypeScript
- **Database**: Neo4j for graph storage  
- **Architecture**: API-only service (no frontend)
- **AI Integration**: Mocked LLM calls for relationship analysis
- **Local Development**: No deployment required

## Dataset

The system works with `ecosystem_dataset.json` containing 50+ species with rich ecological descriptions that mention resource competition relationships.

**Sample data structure:**
```json
{
  "id": "1",
  "name": "Gray Wolf",
  "scientific_name": "Canis lupus",
  "description": "Apex predator competing with Brown Bears for elk carcasses during winter months. Territory overlaps with Coyotes in Yellowstone, leading to direct competition for deer and small mammals. Competes with Mountain Lions for ungulate prey...",
  "type": "mammal",
  "habitat": "Forests, tundra, grasslands",
  "diet": "Carnivore",
  "region": "North America, Europe, Asia",
  "conservation_status": "Least Concern"
}
```

## Key Challenges Addressed

### Natural Language Processing
- Parsing unstructured ecological text to identify species mentions
- Extracting competition types from context ("competes for", "territory overlap")
- Handling seasonal variations and resource scarcity contexts
- Managing scientific vs. common name variations

### Ecological Complexity
- **Seasonal Variations**: Competition patterns that change with seasons
- **Resource Hierarchies**: Multiple species competing for the same resources
- **Temporal Dynamics**: Migration patterns, breeding seasons, climate dependencies
- **Multi-level Competition**: Food, water, territory, and breeding resource conflicts

### Technical Solutions
- **Mock LLM Integration**: Simulated AI-powered relationship extraction
- **Confidence Scoring**: Reliability ratings for extracted relationships  
- **Graph Data Structure**: Structured nodes/edges format for visualization
- **API Design**: RESTful endpoints for all system functionality

## Resource Competition Types

The system identifies and classifies several types of ecological competition:

- **Food Competition**: Prey animals, plant matter, seasonal resources
- **Water Sources**: Rivers, lakes, seasonal water holes, territorial springs  
- **Territory/Shelter**: Denning sites, nesting areas, territorial boundaries
- **Breeding Resources**: Mating territories, nesting materials, spawning grounds

## API Examples

### Get Species Competition
```bash
GET /api/species/gray-wolf/competitions
```

**Response:**
```json
{
  "species": "Gray Wolf",
  "scientific_name": "Canis lupus",
  "resource_competitions": [
    {
      "competing_species": "Brown Bear",
      "resource_type": "prey",
      "specific_resource": "elk carcasses",
      "competition_intensity": 0.8,
      "seasonal_factor": "winter_months",
      "confidence": 0.9,
      "description": "Direct competition for elk carcasses during winter when food is scarce"
    }
  ]
}
```

### Search Species
```bash
GET /api/search?q=wolf
```

### Get Graph Data
```bash
GET /api/graph/species/gray-wolf
```

**Response:**
```json
{
  "nodes": [
    {
      "id": "gray-wolf",
      "name": "Gray Wolf",
      "type": "mammal",
      "scientific_name": "Canis lupus"
    },
    {
      "id": "brown-bear", 
      "name": "Brown Bear",
      "type": "mammal",
      "scientific_name": "Ursus arctos"
    }
  ],
  "edges": [
    {
      "source": "gray-wolf",
      "target": "brown-bear",
      "relationship": "competes_for",
      "resource": "elk_carcasses",
      "intensity": 0.8,
      "seasonal": "winter",
      "confidence": 0.9
    }
  ]
}
```

## Installation & Setup

```bash
# Clone repository
git clone [your-repo-url]
cd ecological-competition-mapper

# Install dependencies
npm install

# Setup Neo4j database
# [Add your Neo4j setup instructions]

# Load sample data
npm run load-data

# Start development server
npm run dev
```

## Project Structure

```
├── src/
│   ├── api/           # REST API endpoints
│   ├── services/      # Business logic and text processing
│   ├── models/        # Neo4j database models
│   ├── utils/         # Helper functions and NLP utilities
│   └── mock/          # LLM integration mocks
├── data/
│   └── ecosystem_dataset.json
├── tests/            # API tests
└── docs/             # API documentation
```

## Development Approach

### Text Processing Strategy
The system uses rule-based text analysis combined with mocked LLM enhancement to extract ecological relationships. Key processing steps:

1. **Species Name Recognition**: Identify mentioned species in descriptions
2. **Context Analysis**: Extract competition-related phrases and context
3. **Relationship Classification**: Categorize competition types and resources
4. **Confidence Scoring**: Assign reliability scores to extracted relationships
5. **Seasonal Detection**: Identify temporal patterns in competition

### Limitations & Future Improvements

**Current Limitations:**
- Rule-based text processing has accuracy constraints
- Seasonal pattern detection is simplified
- Competition intensity scoring is heuristic-based
- Limited to provided dataset species

**Future Enhancements:**
- Real LLM integration for improved accuracy
- Dynamic dataset expansion
- Climate change impact modeling
- Population dynamics integration

## Time Investment

**Actual development time:** [Report your honest time spent]

**Time breakdown:**
- Text processing and NLP: [X hours]
- Neo4j integration: [X hours]  
- API development: [X hours]
- Graph data structure design: [X hours]
- Testing and debugging: [X hours]

## Demo

[Link to your demo video - 3-5 minutes showing the system in action]

## Technical Decisions & Trade-offs

[Document your key architectural decisions, what you prioritized given time constraints, and what you would improve with more time]

## License

[Your license choice]
