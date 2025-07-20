# Technical Assessment: Ecological Resource Competition Mapper

Welcome to our technical assessment! This is a fascinating challenge to build a biological intelligence tool that maps how plants and animals compete for essential resources.

**Time Expectation:** This should take approximately 4 hours of focused work. You have one week to complete and submit your solution.

**Important:** Please track and honestly report your actual time spent. We value integrity and are more interested in your approach and problem-solving process than a perfect solution.

## The Challenge: Build an Ecosystem Resource Competition Finder

### The Task
Build a tool that takes any plant or animal species as input and automatically discovers and maps their resource competition relationships using ecological data.

### Requirements:
- **Smart Discovery:** When a user enters "Gray Wolf", your system should find and display competing species from the dataset (prey competition, territory overlap, resource conflicts, etc.)
- **Competition Detection:** Use text analysis to identify resource competition mentioned in species habitat descriptions
- **Intelligent Classification:** Automatically categorize competition types (food competition, water sources, nesting sites, territory, seasonal migration routes, etc.)
- **Graph Data Output:** API endpoints that return graph data structures for visualization
- **API-Only:** No frontend required - all functionality through REST endpoints
- **Real-time Enhancement:** Use LLM integration (mocked) to enrich basic relationships with ecological insights

### Technical Stack Requirements
- Node.js + TypeScript backend
- Neo4j for ecosystem graph storage
- **No frontend required** - API endpoints return graph data
- LLM integration for ecological analysis (mock the expensive calls)
- Can run locally (no deployment required)

## What You'll Work With

**Dataset**: `ecosystem_dataset.json` with 50+ species containing ecological descriptions that mention competition relationships.

**Sample species description:**
> "Gray Wolf: Apex predator competing with Brown Bears for elk carcasses during winter months. Territory overlaps with Coyotes leading to direct competition for deer and small mammals..."

Your job: Extract these relationships automatically using text analysis.

**The "impossible" part:** The ecological relationships are embedded in natural language descriptions, and you need to extract them accurately, classify resource competition types correctly, and handle complex cases where multiple species compete for the same resources in different seasons or conditions.

## Technical Hints (Read Carefully!)

### The Ecological Data Challenge
The provided dataset contains complex ecological relationships hidden in natural language descriptions. You'll need to:
- Parse unstructured text to identify species mentions and resource conflicts
- Determine competition types from context ("competes for", "territory overlap", "resource conflict")
- Handle seasonal variations ("during spawning season", "winter competition")
- Deal with variations in species names (common vs. scientific names)
- Understand resource hierarchies (primary prey vs. opportunistic feeding)

### The LLM Challenge  
Since LLM APIs cost money, you must:
- Create intelligent mocks that simulate ecological relationship extraction from text
- Show how you WOULD integrate real LLMs with proper ecological prompt engineering
- Demonstrate understanding of how LLMs could enhance basic ecological text parsing
- Mock seasonal pattern recognition and resource scarcity analysis

### The "Impossible" Parts
You'll quickly realize some ecological challenges:
- Perfect natural language understanding of complex ecological relationships without expensive LLMs
- Handling seasonal competition variations (summer vs. winter resource availability)
- Resolving conflicts when Species A competes with Species B for Resource X, but they also sometimes share Resource Y
- Determining competition intensity and ecological impact levels
- Understanding cascading effects in food webs

**This is intentional!** We want to see:
- How you prioritize when ecological perfection isn't achievable
- Your creative biological text processing solutions  
- How you handle seasonal variations and resource scarcity edge cases
- Your ability to build something ecologically useful despite limitations

## Sample Expected Output

When someone searches for "Gray Wolf":
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
      "competition_type": "direct_scavenging",
      "confidence": 0.9,
      "source": "habitat_analysis",
      "description": "Direct competition for elk carcasses during winter when food is scarce"
    },
    {
      "competing_species": "Mountain Lion",
      "resource_type": "prey",
      "specific_resource": "ungulates",
      "competition_intensity": 0.7,
      "seasonal_factor": "year_round",
      "competition_type": "hunting_territory_overlap", 
      "confidence": 0.85,
      "source": "territory_analysis",
      "description": "Overlapping hunting territories for deer and elk populations"
    },
    {
      "competing_species": "Coyote",
      "resource_type": "territory",
      "specific_resource": "small_mammal_hunting_grounds",
      "competition_intensity": 0.6,
      "seasonal_factor": "year_round", 
      "competition_type": "territorial_displacement",
      "confidence": 0.75,
      "source": "behavioral_analysis",
      "description": "Territory overlap leading to coyote displacement in core wolf areas"
    }
  ],
  "resource_dependencies": [
    {
      "resource": "water_sources",
      "importance": 0.9,
      "competing_species_count": 12,
      "seasonal_variation": "high_summer_competition"
    }
  ]
}
```

## Unique Ecological Challenges to Consider

### Resource Type Classifications:
- **Food Competition:** Prey animals, plant matter, seasonal fruits/nuts
- **Water Sources:** Rivers, lakes, seasonal water holes, territorial springs  
- **Shelter/Territory:** Denning sites, nesting areas, territorial boundaries
- **Breeding Resources:** Mating territories, nesting materials, spawning grounds

### Temporal Complexity:
- **Seasonal Variations:** Migration patterns, breeding seasons, food availability cycles
- **Climate Dependencies:** Drought impacts, seasonal temperature effects
- **Population Dynamics:** Resource pressure changes based on population sizes

### Ecosystem Interactions:
- **Trophic Levels:** Primary producers, herbivores, carnivores, apex predators
- **Symbiotic Relationships:** Mutualism vs. competition (sometimes the same species!)
- **Cascading Effects:** How competition between two species affects the entire ecosystem

## Deliverables

### Code Submission (choose one):
- GitHub repository link, OR  
- ZIP file with complete code and README

### Demo Video (3-5 minutes)
- Show the system working with the provided dataset
- Explain your approach to ecological relationship extraction
- Mention your actual time spent

That's it! Keep it simple.

## Evaluation Criteria

We're evaluating:
- **Creativity:** How do you solve the ecological complexity?
- **Technical Architecture:** Clean, scalable code structure
- **Problem-Solving:** How do you handle biological constraints and seasonal variations?
- **Communication:** How clearly do you explain your ecological approach?
- **Honesty:** Realistic time reporting and acknowledgment of limitations

## Getting Started
1. Clone the starter repository: `git clone [repo-url]`
2. Read the technical hints above
3. Start building and document your ecological discovery journey!

## Submission
Send your code (GitHub link or ZIP file) and demo video (unlisted YouTube link is fine) to [email].

## Questions?
If you have clarification questions about ecological concepts or technical requirements, feel free to reach out. We're happy to help with genuine questions, but part of the assessment is seeing how you handle the inherent complexity of ecosystem analysis.

**Good luck!** Remember: we're not expecting perfect ecological modeling. We want to see how you think about biological systems, build technical solutions, and solve complex natural science problems creatively.

This assessment is designed to be challenging and somewhat impossible—just like real ecosystem analysis! Show us your creativity, technical skills, and scientific problem-solving approach.
