# EuroVoyage Testing Pipeline Documentation

## Overview

The EuroVoyage Testing Pipeline is a core component of our platform that automates the process of retrieving, enriching, storing, formatting, and publishing content. This document provides detailed information about the pipeline architecture, components, and implementation.

## Pipeline Architecture

The Testing Pipeline consists of five main stages:

1. **Data Source (Airtable)**
   - Source of initial place data
   - Contains basic information about places to be processed

2. **Data Enrichment (Apify)**
   - Uses Google Maps Business Scraper actor
   - Retrieves detailed information about places
   - Accesses data via API compass/google-places-api

3. **Data Storage (Supabase)**
   - Stores all processed data
   - Maintains pipeline state and logs
   - Provides data for template application

4. **Template Application (Website)**
   - Applies formatting templates to the data
   - Prepares content for publication
   - Generates preview for admin approval

5. **Publication (Website)**
   - Publishes formatted content to the website
   - Makes content available to users
   - Updates content status in the database

## Implementation Details

### Airtable Integration

The Airtable integration retrieves data from a specified Airtable base using the Airtable API:

- **Base Configuration**: The pipeline connects to a specific Airtable base using API keys stored in environment variables
- **Data Retrieval**: The pipeline retrieves records for a specific place ID
- **Data Transformation**: The retrieved data is transformed into a format suitable for the next pipeline stage

### Apify Integration

The Apify integration uses the Google Maps Business Scraper actor to enrich the data:

- **Actor Configuration**: The pipeline configures the Google Maps Business Scraper actor with appropriate parameters
- **API Access**: The pipeline uses API compass/google-places-api to access Google Maps data
- **Data Processing**: The actor processes the place ID and returns detailed information
- **Error Handling**: The pipeline handles potential errors in the Apify processing stage

### Supabase Storage

The Supabase storage component manages all data throughout the pipeline:

- **Schema Design**: The database schema is designed to store all necessary place information
- **Pipeline State**: The database tracks the state of each place ID in the pipeline
- **Logging**: All pipeline actions are logged for debugging and monitoring
- **Error Tracking**: Errors are recorded with detailed information for troubleshooting

### Template Application

The template application component formats the data for display:

- **Template Selection**: The appropriate template is selected based on the place type
- **Data Formatting**: The data is formatted according to the template
- **Preview Generation**: A preview is generated for admin approval
- **Validation**: The formatted content is validated for completeness and accuracy

### Publication

The publication component makes the content available on the website:

- **Content Storage**: The formatted content is stored in the appropriate database tables
- **URL Generation**: A URL is generated for the published content
- **Status Update**: The status of the place ID is updated in the pipeline tracking system
- **Notification**: The admin is notified of the successful publication

## Admin Dashboard

The Admin Dashboard provides a user interface for controlling and monitoring the pipeline:

- **Pipeline Trigger**: Admins can trigger the pipeline for a specific place ID
- **Status Monitoring**: The dashboard displays the current status of the pipeline
- **Log Viewer**: Admins can view detailed logs of pipeline operations
- **Error Handling**: The dashboard displays any errors that occur during processing
- **Content Preview**: Admins can preview the formatted content before publication
- **Publication Control**: Admins can approve or reject content for publication

## Testing and Verification

The pipeline includes comprehensive testing and verification:

- **Unit Tests**: Each component of the pipeline is tested individually
- **Integration Tests**: The interactions between components are tested
- **End-to-End Tests**: The entire pipeline is tested with a test place ID
- **Error Handling Tests**: Various error scenarios are tested to ensure proper handling
- **Performance Tests**: The pipeline is tested for performance under various conditions

## Success Criteria

The Testing Pipeline is considered successful when:

1. A single place ID can be processed from Airtable through to publication
2. Each stage of the pipeline provides appropriate logging and status updates
3. Errors are properly handled and reported
4. The Admin Dashboard provides clear visibility into the pipeline operation
5. The published content accurately reflects the source data

## Future Enhancements

After the successful implementation of the Testing Pipeline, future enhancements will include:

- **Batch Processing**: Processing multiple place IDs simultaneously
- **Scheduling**: Automated pipeline runs on a schedule
- **Advanced Error Recovery**: Automatic retry and recovery mechanisms
- **Performance Optimization**: Improved processing speed and efficiency
- **Extended Data Sources**: Integration with additional data sources
- **Enhanced Templates**: More sophisticated content formatting options
- **Analytics**: Detailed analytics on pipeline performance and content quality