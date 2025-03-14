# EuroVoyage

EuroVoyage is a specialized directory platform for European restaurants, attractions, and destinations. Our mission is to provide travelers with authentic, detailed, and personalized information about European travel experiences.

## Project Overview

This repository contains the codebase for the EuroVoyage platform, which is currently in Phase 1 of development. The primary focus of this phase is to implement a fully functional testing pipeline that processes data from Airtable through Apify's Google Maps Business Scraper, stores it in Supabase, applies templates, and publishes the content to the website.

## Key Documentation

- [ROADMAP.md](./ROADMAP.md) - Detailed development roadmap with phases and tasks
- [PIPELINE_DOCUMENTATION.md](./PIPELINE_DOCUMENTATION.md) - Comprehensive documentation of the testing pipeline

## Pipeline Workflow

The EuroVoyage testing pipeline follows this workflow:

```
Airtable → Apify → Supabase → Template Application → Publication
```

### Pipeline Components

1. **Airtable Integration**
   - Source of initial place data
   - Contains basic information about places to be processed

2. **Apify Integration**
   - Uses Google Maps Business Scraper actor
   - Retrieves detailed information about places
   - Accesses data via API compass/google-places-api

3. **Supabase Storage**
   - Stores all processed data
   - Maintains pipeline state and logs
   - Provides data for template application

4. **Template Application**
   - Applies formatting templates to the data
   - Prepares content for publication
   - Generates preview for admin approval

5. **Publication**
   - Publishes formatted content to the website
   - Makes content available to users
   - Updates content status in the database

## Current Status

The project is currently in Phase 1, focusing on implementing the testing pipeline. The goal is to successfully process a single place ID through the entire pipeline workflow.

## Getting Started

### Prerequisites

- Node.js (v14 or higher)
- Airtable account and API key
- Apify account and API key
- Supabase account and project

### Installation

1. Clone the repository:
   ```
   git clone https://github.com/aemd2/wesbite.git
   cd wesbite
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Set up environment variables:
   ```
   cp .env.example .env
   ```
   Then edit the `.env` file with your API keys and configuration.

4. Start the development server:
   ```
   npm run dev
   ```

## Contributing

We welcome contributions to the EuroVoyage project. Please refer to the [ROADMAP.md](./ROADMAP.md) file for current development priorities.

## License

This project is proprietary and confidential. All rights reserved.

## Contact

For questions or inquiries about the EuroVoyage project, please contact the project maintainers.