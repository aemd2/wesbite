# EuroVoyage Development Roadmap

<!-- AI-METADATA
{
  "version": "2.0.0",
  "project_name": "EuroVoyage",
  "current_phase": "Phase 1",
  "target_completion_date": "Month 2",
  "documentation_type": "roadmap"
}
-->

## Project Overview
EuroVoyage is a specialized directory platform for European restaurants, attractions, and destinations. Our mission is to provide travelers with authentic, detailed, and personalized information about European travel experiences.

## Development Phases

### Phase 1: Testing Pipeline Implementation (Current Phase)
**Timeline:** Month 1  
**Focus:** Implementing a fully functional testing pipeline  
**Status:** IN_PROGRESS

#### Core Objective
Successfully implement a complete testing pipeline that processes a single place ID through the entire workflow:
1. Retrieve data from Airtable
2. Process data through Apify's Google Maps Business Scraper (using API compass/google-places-api)
3. Store processed data in Supabase
4. Apply template in the website
5. Publish the content

#### Key Tasks

##### Pipeline Infrastructure
- [ ] **P1.1** [P0] Set up Airtable integration for data source
- [ ] **P1.2** [P0] Configure Apify actor (Google Maps Business Scraper) connection
- [ ] **P1.3** [P0] Establish Supabase database schema for pipeline data
- [ ] **P1.4** [P0] Create pipeline logging and tracking system
- [ ] **P1.5** [P0] Implement error handling and reporting

##### Backend Implementation
- [ ] **P1.6** [P0] Develop API endpoint for triggering pipeline process
- [ ] **P1.7** [P0] Create data transformation service between pipeline stages
- [ ] **P1.8** [P0] Implement authentication for pipeline access
- [ ] **P1.9** [P0] Build content processing service for template application
- [ ] **P1.10** [P0] Develop publication mechanism for processed content

##### Frontend Implementation
- [ ] **P1.11** [P0] Create Admin Dashboard with pipeline interface
- [ ] **P1.12** [P0] Build pipeline status visualization
- [ ] **P1.13** [P0] Implement pipeline trigger controls
- [ ] **P1.14** [P0] Develop pipeline logs viewer
- [ ] **P1.15** [P0] Create content preview interface

##### Testing and Verification
- [ ] **P1.16** [P0] Test Airtable data retrieval
- [ ] **P1.17** [P0] Verify Apify processing with test place ID
- [ ] **P1.18** [P0] Validate Supabase data storage
- [ ] **P1.19** [P0] Test template application
- [ ] **P1.20** [P0] Verify end-to-end pipeline with a single place ID

## Pipeline Workflow
The testing pipeline follows this specific workflow:

```
Airtable → Apify → Supabase → Template Application → Publication
```

### Step-by-Step Process

1. **Initiation**: Admin triggers the pipeline with a pre-filled place ID
2. **Data Retrieval**: System connects to Airtable and retrieves data for the specified place ID
3. **Data Enrichment**: The place ID is sent to Apify's Google Maps Business Scraper for additional data
4. **Data Storage**: All processed data is stored in Supabase tables with appropriate schema
5. **Template Application**: The system applies a predefined template to format the data for display
6. **Publication**: The formatted content is published to the website
7. **Verification**: Admin can review logs and verify the published content

## Success Criteria for Phase 1

Phase 1 will be considered complete when:

1. A single place ID can be successfully processed through the entire pipeline
2. Each step of the pipeline provides appropriate logging and status updates
3. The final published content accurately reflects the data from Airtable and Apify
4. The Admin Dashboard provides a clear interface for monitoring and controlling the pipeline
5. Error handling is robust and provides clear feedback on any issues

## Next Phases (High-Level Overview)

### Phase 2: Enhanced Pipeline and Core Features
- Implement batch processing for multiple place IDs
- Develop scheduling capabilities for automated pipeline runs
- Build basic user-facing features for viewing published content
- Implement search functionality for published content

### Phase 3: User Experience and Content Expansion
- Develop user authentication and profiles
- Implement review and rating system
- Expand content types and templates
- Enhance search with filters and recommendations

### Phase 4: Business Features and Monetization
- Implement business owner accounts and dashboards
- Develop premium listing features
- Build booking and reservation capabilities
- Create analytics for business performance

## Current Status
**Current Phase:** Testing Pipeline Implementation (Phase 1)  
**In Progress:** Setting up Airtable integration and Apify connection  
**Current Focus:** Establishing the core pipeline infrastructure  
**Up Next:** Developing the Admin Dashboard interface for pipeline control

## Revision History
- **v2.0.0** - Refocused roadmap on testing pipeline implementation as the primary Phase 1 objective
- **v1.0.0** - Initial roadmap creation