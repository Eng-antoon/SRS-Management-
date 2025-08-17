# SONNY Delivery Agent App - Software Requirements Specification (SRS)

**Version:** 1.0  
**Date:** January 2025  
**Epic:** COR-377 - Delivery Agent App  
**Product:** SONNY (Android Delivery Agent Application)

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Business Context and Problem Statement](#2-business-context-and-problem-statement)
3. [Solution Overview](#3-solution-overview)
4. [User Personas and Stakeholder Analysis](#4-user-personas-and-stakeholder-analysis)
5. [Current State Analysis](#5-current-state-analysis)
6. [Functional Requirements](#6-functional-requirements)
7. [Technical Architecture](#7-technical-architecture)
8. [System Integration Requirements](#8-system-integration-requirements)
9. [First Iteration Scope](#9-first-iteration-scope)
10. [Success Metrics and Acceptance Criteria](#10-success-metrics-and-acceptance-criteria)
11. [Risk Assessment](#11-risk-assessment)
12. [Glossary](#12-glossary)

---

## 1. Executive Summary

### 1.1 Project Vision
SONNY is a custom-built Android application designed to replace the Locus Delivery Agent app for our logistics company's FMCG transportation operations. The application aims to provide a user-centric delivery management solution that aligns with our Delivery Agents' (DAs) actual workflows while maintaining seamless integration with existing Locus administrative systems.

### 1.2 Strategic Objectives
- **Immediate Goal:** Replace Locus DA mobile app with SONNY while maintaining full operational continuity
- **Long-term Vision:** Develop a complete in-house fulfillment engine to replace all Locus dependencies
- **Business Impact:** Improve DA productivity, increase data visibility, and reduce operational costs

### 1.3 Key Success Factors
- Zero disruption to current operations during transition
- 100% data synchronization with Locus administrative dashboard
- Improved DA user experience and workflow efficiency
- Enhanced data collection capabilities for business intelligence

---

## 2. Business Context and Problem Statement

### 2.1 Company Profile
We are a logistics company specializing in FMCG (Fast-Moving Consumer Goods) transportation using trucks. Our operations involve tracking vehicles through driver mobile applications and managing delivery agents who handle last-mile delivery to retail locations.

### 2.2 Current Technology Stack
- **Driver Tracking:** Custom in-house mobile application
  - Route logging and live location tracking
  - Permission monitoring (GPS, Internet, Power saving)
  - Debug file generation for trip analysis
- **DA Management:** Locus third-party application
- **Administrative Backend:** Ruby-based admin panel

### 2.3 Core Business Problems

#### 2.3.1 Locus Application Limitations
1. **User Experience Misalignment**
   - App workflow doesn't match DA persona and actual work patterns
   - No ability to customize UI/UX to fit our operational needs
   - Complex navigation that causes confusion among DAs

2. **Data Collection Constraints**
   - Limited access to granular operational data
   - Cannot track DA behavioral patterns and route deviations
   - Insufficient visibility into SLA breaches and performance metrics

3. **Operational Inefficiencies**
   - DAs consistently override app-suggested routes based on real-world constraints
   - Batch processing of deliveries at end-of-day rather than real-time updates
   - Manual workarounds via WhatsApp and phone calls for issue resolution

4. **Cost Factors**
   - High licensing costs for Locus platform
   - Dependency on external vendor for critical business operations
   - Limited scalability and customization options

#### 2.3.2 Workflow Misalignment Issues
Based on field research and DA interviews, current system failures include:
- Route optimization ignores practical constraints (store closing times, traffic patterns)
- Mandatory workflows don't account for real-world delivery scenarios
- Proof of delivery processes are cumbersome and often bypassed
- Issue escalation requires manual intervention and causes delays

---

## 3. Solution Overview

### 3.1 SONNY Application Vision
SONNY is designed as a pragmatic, DA-centric delivery management application that bridges the gap between operational reality and system requirements. The application will respect actual DA workflows while ensuring complete data capture and system integration.

### 3.2 Core Design Principles
1. **Workflow Alignment:** Match real DA operational patterns rather than forcing artificial processes
2. **Data Transparency:** Capture comprehensive operational metrics for business intelligence
3. **Seamless Integration:** Maintain 100% compatibility with existing Locus administrative systems through comprehensive API integration
4. **Incremental Replacement:** Phased approach to minimize operational disruption
5. **Business Value Focus:** Prioritize features that deliver immediate operational improvements and cost savings

### 3.3 Locus Integration Business Value
**Immediate Business Benefits:**
- **Operational Continuity:** Zero disruption to existing dispatch and monitoring workflows
- **Cost Optimization:** Reduced per-agent licensing costs while maintaining full administrative capabilities
- **Enhanced Data Collection:** Real-time location tracking and performance analytics beyond current capabilities
- **Improved User Experience:** Customized DA interface while preserving supervisor visibility

**Strategic Advantages:**
- **Vendor Independence:** Reduced dependency on Locus for mobile application functionality
- **Innovation Capability:** Ability to rapidly implement business-specific features and improvements
- **Data Ownership:** Enhanced control over operational data and analytics
- **Scalability:** Foundation for future expansion and custom dashboard development

### 3.4 Strategic Implementation Approach

#### Phase 1: Mobile App Replacement (Current Scope)
- Develop SONNY Android application with Locus-compatible data exchange
- Implement middleware layer for seamless Locus dashboard integration
- Maintain all existing operational processes while improving user experience

#### Phase 2: Administrative Dashboard Development (Future)
- Build custom administrative dashboard starting with DA management and dispatching
- Gradually replace Locus administrative functions
- Develop advanced analytics and reporting capabilities

#### Phase 3: Complete Platform Independence (Future)
- Implement full route optimization and tour planning capabilities
- Achieve complete independence from Locus platform
- Deploy advanced AI/ML capabilities for operational optimization

---

## 4. User Personas and Stakeholder Analysis

### 4.1 Primary User Personas

#### 4.1.1 Mahmoud - The Experienced & Pragmatic DA
**Profile:**
- Highly experienced delivery agent with 3+ years in the field
- Relies on personal knowledge and judgment over system suggestions
- Physically demanding workload (50-250 cartons per stop)

**Key Behaviors:**
- Ignores app-suggested route sequences in favor of optimized personal routes
- Prioritizes deliveries based on store closing times and known delay patterns
- Uses WhatsApp groups for issue escalation and communication
- Batches administrative tasks at end of day

**Pain Points:**
- Route inefficiency from system-generated plans
- Extreme waiting times at customer locations (several hours)
- Inaccurate delivery location data requiring manual correction
- Truck loading order mismatches with optimal delivery sequence

**System Requirements:**
- Flexible route modification capabilities
- Real-time location accuracy
- Streamlined proof of delivery process
- Efficient issue reporting mechanism

#### 4.1.2 Mohamed - The Process-Oriented DA
**Profile:**
- Newer DA focused on understanding official processes
- Interested in tools that provide structure and efficiency
- Proactive in building informal networks for faster problem resolution

**Key Behaviors:**
- Re-prioritizes deliveries based on customer closing times
- Documents all necessary paperwork before departing warehouse
- Builds contact lists for direct communication with sales team
- Shows high interest in technological improvements

**Pain Points:**
- Slow problem resolution through official channels (30+ minute waits)
- Complex and non-standardized receiving procedures at customer locations
- Dependency on driver/helper relationships for successful operations
- Customers refusing partial orders requiring immediate approval

**System Requirements:**
- In-app issue reporting with formal record creation
- Direct communication channels with relevant stakeholders
- Standardized customer interaction protocols
- Real-time approval mechanisms for delivery modifications

#### 4.1.3 Ziad - The Supervisor/Operations Manager
**Profile:**
- Bridge between field operations and central planning
- Manages daily dispatch and DA oversight
- Central point for all escalations and exception handling

**Key Behaviors:**
- Manual trip assignment based on DA skills and customer requirements
- Uses Locus primarily for location tracking
- Manages through constant phone communication with DAs
- Makes critical decisions on delivery modifications and rescheduling

**Pain Points:**
- Communication overload requiring constant reactive management
- Acts as information bottleneck between DAs and company systems
- Inconsistent app usage from DAs impacting real-time visibility
- Limited proactive management capabilities due to manual processes

**System Requirements:**
- Comprehensive real-time visibility into DA operations
- Automated escalation and approval workflows
- Centralized communication and issue management
- Proactive alerts and exception handling

### 4.2 Secondary Stakeholders

#### 4.2.1 Operations Management Team
- Requires comprehensive operational visibility and reporting
- Depends on accurate SLA tracking and performance metrics
- Needs integration with existing business intelligence systems

#### 4.2.2 IT/Technical Team
- Responsible for system maintenance and integration
- Requires robust monitoring and debugging capabilities
- Manages data security and compliance requirements

#### 4.2.3 Finance/Cost Management
- Tracks operational costs and efficiency metrics
- Requires accurate delivery confirmation and invoice management
- Monitors resource utilization and optimization opportunities

---

## 5. Current State Analysis

### 5.1 Existing Locus Workflow Analysis

#### 5.1.1 Current DA Daily Workflow
**Phase 1: Authentication**
1. Open Locus application
2. Login with Rider ID and password
3. Handle forgot password scenarios through Rider ID validation

**Phase 2: Task Assignment & Tour Initiation**
1. View assigned tour card on home screen
2. Access tour detailed screen with task sequencing capabilities
3. Start tour with confirmation prompts

**Phase 3: Pick-up Task Execution**
1. Navigate to active task screen
2. Swipe confirmations for task initiation and work beginning
3. Photo capture for pickup confirmation
4. Upload visual proof of pickup completion

**Phase 4: Drop-off Task Execution**
1. Navigate to drop-off location using integrated mapping
2. Confirm arrival and initiate drop-off process
3. Product scanning for inventory verification
4. Signature capture and photo upload for proof of delivery

**Phase 5: Tour Completion**
1. Process additional tasks if remaining
2. Complete tour ending procedures

#### 5.1.2 Actual DA Operational Reality
**Morning Warehouse Phase:**
1. Receive Locus-assigned orders from supervisor
2. **Immediate Route Re-optimization:** DAs disregard system sequence
3. **Personal Prioritization Logic:**
   - Customer closing times (highest priority)
   - Known problematic customers and queue patterns
   - Geographic proximity and traffic considerations
   - Delivery quantity optimization (larger quantities = higher priority)
4. Paperwork preparation and vehicle loading assessment

**On-Road Delivery Phase:**
1. **Self-Directed Navigation:** Follow personal route, not Locus suggestions
2. **Customer Interaction Scenarios:**
   - Standard delivery with invoice stamping
   - Extended waiting in delivery queues (up to several hours)
   - Customer rejection scenarios requiring supervisor escalation
   - Payment processing delays for cash deliveries
3. **Problem Resolution:** WhatsApp communication with supervisor and sales teams
4. **Proof Collection:** Photo capture without immediate app updating

**End-of-Day Administrative Phase:**
1. **Batch Processing:** Complete all Locus order closures simultaneously
2. Upload all collected invoice photos
3. Return refused goods and settle cash collections
4. Formal trip closure in Locus system

### 5.2 System Integration Points

#### 5.2.1 Current Locus Data Exchange
- **Inbound:** Tour assignments, customer data, product information
- **Outbound:** Delivery confirmations, proof of delivery photos, completion status
- **Real-time:** Location tracking, status updates, exception alerts

#### 5.2.2 Administrative Dependencies
- **Dispatch Management:** Manual assignment through Locus interface
- **Real-time Monitoring:** Location tracking and status visibility
- **Issue Resolution:** Exception handling and approval workflows
- **Reporting:** Performance metrics and operational analytics

---

## 6. Functional Requirements

### 6.1 Authentication and User Management (Epic COR-378)

#### 6.1.1 User Authentication
**Requirement ID:** FR-001  
**Priority:** High  
**Description:** Secure login system integrated with Fulfillment Engine

**Functional Specifications:**
- Support for Rider ID and password authentication
- Integration with automated DA profile synchronization from Locus
- Forgot password functionality with SMS-based reset
- Session management and automatic logout for security

**Acceptance Criteria:**
- DA can successfully login using existing Locus credentials
- Failed login attempts trigger appropriate error messaging
- Password reset functionality sends new password to registered phone number
- Inactive DAs are prevented from accessing the application

#### 6.1.2 Profile Synchronization
**Requirement ID:** FR-002  
**Priority:** High  
**Description:** Automated synchronization of DA profiles from Locus system

**Functional Specifications:**
- Real-time synchronization of new DA profiles from Locus
- Automatic profile updates for modified DA information
- Status management for inactive or deleted DAs
- Data validation and error handling for synchronization failures

### 6.2 Tour Management and Assignment (Epic COR-379)

#### 6.2.1 Tour Ingestion via Locus API
**Requirement ID:** FR-003  
**Priority:** High  
**Description:** Automated import of tour plans from Locus system via GET tour API

**Functional Specifications:**
- **Tour Data Retrieval:** Integration with `/v1/client/{clientId}/tour/{tourId}` endpoint
- **Complete Tour Structure Extraction:**
  - Tour ID, name, and assigned rider information
  - Visit sequences with location and timing data
  - Task details including pickup and delivery requirements
  - Fleet information (rider, vehicle model, transporter)
  - Summary data (task counts, volume, resource utilization)
- **Real-time Tour Updates:** Monitoring for tour status changes and modifications
- **Tour Include Parameters:** SEQUENCE, TOUR_VISITS, VISITS_INFO, EXECUTION_TRAIL, FLEET, TASKS

**Locus Tour Data Structure Integration:**
- **Tour Metadata:** id, name, status, date, plannedSequence, fleetInfo
- **Visit Information:** visitId, location, timeWindow, status, checklists
- **Task Graph:** visits with volumes, resources, orderDetail, payments
- **Fleet Details:** rider profile, vehicle model, transporter information
- **Performance Metrics:** planned vs. actual travel distance/duration

**Data Requirements:**
- **Tour Management:** Complete tour lifecycle from assignment to completion
- **Location Data:** GPS coordinates, addresses, geocoding metadata
- **Resource Tracking:** Volume utilization, weight limits, skill requirements
- **Timeline Management:** Planned vs. actual timing with ETA calculations

#### 6.2.2 Tour Display and Management
**Requirement ID:** FR-004  
**Priority:** High  
**Description:** User-friendly tour visualization and management interface

**Functional Specifications:**
- Clear tour overview with stop sequencing
- Individual stop detail access with mapping integration
- Tour start/stop functionality with confirmation
- Real-time tour status tracking and updates

### 6.3 Delivery Execution Workflow

#### 6.3.1 Pickup Task Management
**Requirement ID:** FR-005  
**Priority:** High  
**Description:** Comprehensive pickup task execution and confirmation

**Functional Specifications:**
- Swipe-to-start pickup task functionality
- Work initiation confirmation with time tracking
- Photo capture for pickup verification
- Multiple image upload capability
- Quantity confirmation and discrepancy reporting

#### 6.3.2 Drop-off Task Management
**Requirement ID:** FR-006  
**Priority:** High  
**Description:** Complete drop-off process with proof of delivery

**Functional Specifications:**
- Navigation integration for drop-off locations
- Arrival confirmation with GPS verification
- Product scanning functionality (barcode/QR code)
- Digital signature capture
- Photo upload for delivery proof
- Quantity verification and exception handling

#### 6.3.3 Flexible Route Management
**Requirement ID:** FR-007  
**Priority:** Medium  
**Description:** Support for DA route optimization preferences

**Functional Specifications:**
- Stop sequence modification capabilities
- Priority-based reordering (closing times, customer preferences)
- Route deviation tracking and analytics
- Integration with mapping services for navigation

### 6.4 Real-time Data Synchronization (Epic COR-380)

#### 6.4.1 Locus Integration Bridge
**Requirement ID:** FR-008  
**Priority:** Critical  
**Description:** 100% data synchronization with Locus administrative dashboard using Locus API

**Functional Specifications:**
- **Location Updates:** Bulk rider location updates via `/v1/client/{clientId}/rider-locations` endpoint
  - Real-time GPS tracking with battery status monitoring
  - Bulk update capability for performance optimization (multiple locations per request)
  - GPS accuracy validation and provider information
- **Task Status Synchronization:** Real-time task updates via `/v1/client/{clientId}/task/{taskId}/status`
  - Status transitions: RECEIVED → WAITING → ACCEPTED → STARTED → ARRIVED → TRANSACTING → COMPLETED
  - Visit-level status updates via `/v1/client/{clientId}/task/{taskId}/visit/{visitId}/status`
  - Timestamp synchronization with ISO-8601 format
- **Proof of Delivery:** POD upload via `/v1/client/{clientId}/task/{taskId}/custom-fields`
  - Photo attachment with metadata
  - Digital signature storage
  - Custom field data for additional delivery information
- **Tour Management:** Tour data retrieval via `/v1/client/{clientId}/tour/{tourId}`
  - Complete tour structure including visit sequences
  - Fleet and rider information synchronization
  - Performance analytics and summary data

**API Integration Requirements:**
- **Authentication:** Basic Authentication with secure credential management
- **Error Handling:** Comprehensive HTTP status code handling (2xx, 4xx, 5xx)
- **Retry Logic:** Exponential backoff for failed requests
- **Rate Limiting:** Compliance with Locus API rate limits
- **Data Validation:** Schema validation for all API payloads

**Critical Data Synchronization Points:**
- **Mandatory Location Fields:** lat, lng, provider, timestamp, riderId
- **Battery Monitoring:** charge, chargingStatus, timestamp
- **Task Status Updates:** status, triggerTime, location coordinates
- **Visit Completions:** visit-specific status with proof of delivery
- **Custom Fields:** POD photos, signatures, and delivery notes

#### 6.4.2 Local Data Management
**Requirement ID:** FR-009  
**Priority:** High  
**Description:** Comprehensive local data storage and offline capability

**Functional Specifications:**
- Local SQLite database for offline operation
- Data synchronization queue management
- Conflict resolution for concurrent updates
- Data backup and recovery mechanisms

### 6.5 Issue Management and Communication

#### 6.5.1 In-App Issue Reporting
**Requirement ID:** FR-010  
**Priority:** Medium  
**Description:** Streamlined issue reporting with formal record creation

**Functional Specifications:**
- Categorized issue reporting (customer rejection, incorrect address, payment issues)
- Photo and note attachment capabilities
- Automatic escalation to supervisor dashboard
- Issue status tracking and resolution notifications
- Integration with existing communication channels

#### 6.5.2 Communication Integration
**Requirement ID:** FR-011  
**Priority:** Low  
**Description:** Enhanced communication capabilities with supervisors and support teams

**Functional Specifications:**
- Direct messaging with supervisor
- Emergency contact integration
- Status update broadcasting
- Notification management and preferences

---

## 7. Technical Architecture

### 7.1 Application Architecture

#### 7.1.1 Platform Specifications
- **Target Platform:** Android Only
- **Minimum Android Version:** Android 8.0 (API level 26)
- **Architecture Pattern:** MVVM (Model-View-ViewModel)
- **Development Framework:** Native Android (Kotlin)

#### 7.1.2 Core Components
1. **Authentication Module**
   - Secure credential management
   - Biometric authentication support
   - Session management
   
2. **Tour Management Module**
   - Tour data synchronization
   - Local tour storage and caching
   - Route optimization interface
   
3. **Task Execution Module**
   - Pickup/Drop-off workflow management
   - Photo capture and management
   - Digital signature collection
   
4. **Synchronization Engine**
   - Real-time data exchange with Locus
   - Offline capability with queue management
   - Conflict resolution algorithms
   
5. **Location Services**
   - GPS tracking and monitoring
   - Geofencing capabilities
   - Navigation integration

### 7.2 Data Architecture

#### 7.2.1 Local Database Schema
**Core Entities:**
- **DA_Profile:** Agent identification and authentication data
- **Tour:** Tour assignments and metadata
- **Order:** Individual delivery orders within tours
- **Task:** Pickup and drop-off task details
- **SKU:** Product information and quantities
- **Photo:** Delivery proof and documentation
- **Location:** GPS tracking and route data
- **Sync_Queue:** Pending synchronization operations

#### 7.2.2 Locus Data Model Integration
**Core Entity Mappings:**

**Rider Profile Mapping:**
```sql
-- SONNY Local Schema
CREATE TABLE rider_profiles (
    rider_id VARCHAR(50) PRIMARY KEY,
    name VARCHAR(100),
    phone_number VARCHAR(20),
    status ENUM('ACTIVE', 'INACTIVE'),
    team_ids JSON,
    skills JSON,
    competency_rating DECIMAL(3,2),
    last_sync_timestamp BIGINT,
    locus_rider_data JSON -- Complete Locus rider object
);
```

**Tour and Task Mapping:**
```sql
-- Tour Management Schema
CREATE TABLE tours (
    tour_id VARCHAR(100) PRIMARY KEY,
    tour_name VARCHAR(200),
    rider_id VARCHAR(50),
    status ENUM('UNASSIGNED', 'QUEUED', 'STARTED', 'COMPLETED'),
    planned_start_time DATETIME,
    actual_start_time DATETIME,
    planned_end_time DATETIME,
    actual_end_time DATETIME,
    locus_tour_data JSON, -- Complete Locus tour object
    last_sync_timestamp BIGINT
);

CREATE TABLE tasks (
    task_id VARCHAR(100) PRIMARY KEY,
    tour_id VARCHAR(100),
    sequence_number INT,
    task_type ENUM('PICKUP', 'DELIVERY'),
    status ENUM('RECEIVED', 'WAITING', 'ACCEPTED', 'STARTED', 'ARRIVED', 'TRANSACTING', 'COMPLETED', 'CANCELLED'),
    customer_name VARCHAR(200),
    customer_address TEXT,
    latitude DECIMAL(10, 8),
    longitude DECIMAL(11, 8),
    planned_arrival_time DATETIME,
    actual_arrival_time DATETIME,
    completion_time DATETIME,
    locus_task_data JSON,
    FOREIGN KEY (tour_id) REFERENCES tours(tour_id)
);
```

**Visit and Order Detail Mapping:**
```sql
CREATE TABLE visits (
    visit_id VARCHAR(100) PRIMARY KEY,
    task_id VARCHAR(100),
    visit_type ENUM('HOMEBASE', 'CUSTOMER'),
    status ENUM('RECEIVED', 'WAITING', 'ACCEPTED', 'STARTED', 'ARRIVED', 'TRANSACTING', 'COMPLETED', 'CANCELLED'),
    location_data JSON,
    checklist_values JSON,
    proof_of_delivery JSON,
    FOREIGN KEY (task_id) REFERENCES tasks(task_id)
);

CREATE TABLE order_line_items (
    item_id VARCHAR(100) PRIMARY KEY,
    task_id VARCHAR(100),
    sku_name VARCHAR(200),
    planned_quantity INT,
    delivered_quantity INT,
    price DECIMAL(10, 2),
    currency VARCHAR(10),
    status ENUM('PENDING', 'DELIVERED', 'PARTIAL', 'REFUSED'),
    FOREIGN KEY (task_id) REFERENCES tasks(task_id)
);
```

#### 7.2.3 Data Synchronization Strategy
**Real-time Synchronization Events:**
- Task status changes (STARTED, COMPLETED, CANCELLED)
- Tour start and completion events
- Critical location updates during active delivery
- Emergency situations and escalations
- POD photo uploads and confirmations

**Batch Synchronization (5-minute intervals):**
- Historical location tracking data
- Performance metrics and analytics
- Non-critical metadata updates
- System health monitoring data

**Conflict Resolution Strategy:**
- **Tour Assignments:** Locus as authoritative source
- **Field Execution Data:** SONNY as authoritative source
- **Timestamp-based Resolution:** Latest update wins for concurrent changes
- **Manual Override:** Critical discrepancies require supervisor intervention

**Offline Support:**
- Complete operational capability for 4+ hours without connectivity
- Local data persistence with automatic sync upon reconnection
- Conflict detection and resolution for offline-generated data

### 7.3 Integration Architecture

#### 7.3.1 Locus API Integration Layer
**Architecture Pattern:** Adapter Pattern with Circuit Breaker
**Components:**
- **API Client Manager:** Handles HTTP requests and authentication
- **Data Mapper:** Transforms between SONNY and Locus data formats
- **Retry Manager:** Implements exponential backoff and failure handling
- **Cache Layer:** Local caching for frequently accessed tour and rider data

**Integration Flow:**
1. **Inbound Data Flow (Locus → SONNY):**
   - Tour assignments retrieved via GET tour APIs
   - Rider profile synchronization
   - Vehicle and fleet information updates
   - Administrative changes and updates

2. **Outbound Data Flow (SONNY → Locus):**
   - Real-time location updates via bulk rider-locations API
   - Task status updates and completion events
   - POD photos and documents via custom-fields API
   - Visit-level status changes and confirmations

#### 7.3.2 Data Synchronization Engine
**Real-time Processing:**
- **Event Queue:** Priority-based message queuing for critical events
- **Sync Orchestrator:** Manages data consistency across systems
- **Conflict Resolver:** Handles concurrent updates and data conflicts
- **Health Monitor:** Tracks sync status and alerts on failures

**Batch Processing:**
- **Location Aggregator:** Batches location updates for performance
- **Analytics Processor:** Processes performance metrics and reporting data
- **Cleanup Manager:** Handles data retention and cleanup policies

#### 7.3.3 Middleware Services
**API Gateway Features:**
- Request routing and load balancing
- Authentication and authorization validation
- Rate limiting and throttling
- Request/response transformation
- Logging and monitoring integration

**Message Queue System:**
- **High Priority Queue:** Critical events (task completion, emergencies)
- **Standard Queue:** Regular updates (location, status changes)
- **Retry Queue:** Failed operations requiring reprocessing
- **Dead Letter Queue:** Permanently failed messages for manual review


---

## 8. System Integration Requirements

### 8.1 Locus API Integration Architecture

#### 8.1.1 Authentication and Security
**Technical Requirement:** TR-001  
**Description:** Secure communication with Locus API using Basic Authentication

**Authentication Specifications:**
- Basic Authentication with credentials shared via secure channels
- HTTPS-only communication for all API endpoints
- API key management and rotation procedures
- Request signing and validation for data integrity
- Error handling for authentication failures and token expiration

**Security Requirements:**
- Secure storage of authentication credentials
- Rate limiting compliance (as per Locus guidelines)
- SSL certificate validation for all requests
- Audit logging for all API interactions
- Data encryption for sensitive information transmission

#### 8.1.2 Core API Integration Endpoints

##### 8.1.2.1 Rider Management APIs
**Endpoint:** `GET /v1/client/{clientId}/rider/{riderId}`
**Purpose:** Retrieve and synchronize DA profile information
**Integration Points:**
- Rider profile synchronization from Locus to SONNY
- Real-time status updates and availability tracking
- Skills and capabilities management
- Team assignment and hierarchy mapping

**Data Structures:**
```json
{
  "riderId": "string",
  "name": "string", 
  "phoneNumber": "string",
  "status": "ACTIVE|INACTIVE",
  "teams": ["teamId"],
  "skills": ["skill1", "skill2"],
  "competency": {
    "rating": "number",
    "experience": "string"
  }
}
```

##### 8.1.2.2 Location Tracking APIs
**Endpoint:** `POST /v1/client/{clientId}/rider-locations`
**Purpose:** Real-time location updates from SONNY to Locus
**Integration Points:**
- Bulk location update capabilities for performance optimization
- Battery status monitoring and reporting
- GPS accuracy and provider information
- Movement tracking and route deviation analysis

**Critical Data Fields:**
- **Location Data:** latitude, longitude, accuracy, timestamp, speed
- **Battery Status:** charge percentage, charging status, expected life
- **GPS Metadata:** provider, GPS enabled status, location validity
- **Rider Context:** riderId, timestamp synchronization

**Location Update Payload:**
```json
{
  "locations": [{
    "location": {
      "lat": "float (mandatory)",
      "lng": "float (mandatory)", 
      "accuracy": "number",
      "provider": "string (mandatory)",
      "timestamp": "int64 (mandatory)",
      "speed": "number",
      "gpsEnabled": "boolean",
      "type": "PLACE",
      "valid": "boolean"
    },
    "batteryStatus": {
      "charge": "integer",
      "chargingStatus": "PLUGGED_USB|PLUGGED_AC|CHARGING|NONE|UNAVAILABLE",
      "timestamp": "int64 (mandatory)"
    },
    "riderId": "string (mandatory)"
  }]
}
```

##### 8.1.2.3 Task Management APIs
**Endpoint:** `POST /v1/client/{clientId}/task/{taskId}/status`
**Purpose:** Task status synchronization and completion tracking
**Integration Points:**
- Real-time task status updates (RECEIVED, WAITING, ACCEPTED, STARTED, ARRIVED, TRANSACTING, COMPLETED, CANCELLED)
- Proof of delivery submission and attachment
- Exception handling and escalation workflows
- SLA tracking and performance monitoring

**Task Status Update Structure:**
```json
{
  "status": "COMPLETED|STARTED|ARRIVED|TRANSACTING|CANCELLED",
  "triggerTime": "ISO-8601 timestamp",
  "checklistValues": {},
  "location": {
    "lat": "number",
    "lng": "number", 
    "accuracy": "number",
    "timestamp": "int64"
  },
  "customFields": {}
}
```

**Endpoint:** `POST /v1/client/{clientId}/task/{taskId}/visit/{visitId}/status`
**Purpose:** Individual visit status updates within multi-stop tasks
**Integration Points:**
- Granular pickup and drop-off tracking
- Visit-specific proof of delivery
- Customer interaction logging
- Time-based performance metrics

##### 8.1.2.4 Tour Management APIs
**Endpoint:** `GET /v1/client/{clientId}/tour/{tourId}`
**Purpose:** Comprehensive tour data retrieval and synchronization
**Integration Points:**
- Complete tour structure with visit sequences
- Planned vs. actual route analysis
- Resource utilization tracking
- Performance analytics and reporting

**Tour Data Structure:**
```json
{
  "id": "string",
  "name": "string",
  "status": "UNASSIGNED|QUEUED|STARTED|COMPLETED",
  "fleetInfo": {
    "riderId": "string",
    "rider": {},
    "vehicleModel": {}
  },
  "tasks": [{
    "taskId": "string",
    "status": {},
    "orderDetail": {
      "lineItems": [],
      "transactionDetail": {}
    },
    "taskGraph": {
      "visits": []
    }
  }],
  "summary": {
    "taskCounts": {},
    "volume": {},
    "resourceUtilization": {}
  }
}
```

##### 8.1.2.5 Proof of Delivery APIs
**Endpoint:** `POST /v1/client/{clientId}/task/{taskId}/custom-fields`
**Purpose:** POD document and metadata upload
**Integration Points:**
- Photo upload and attachment to delivery records
- Digital signature storage and verification
- Customer feedback and notes collection
- Invoice and receipt management

### 8.2 Data Synchronization Strategy

#### 8.2.1 Real-time Synchronization Requirements
**Critical Events (Immediate Sync):**
- Task status changes (Started, Completed, Cancelled)
- Tour start and completion events
- Emergency situations and escalations
- Location updates during active deliveries

**Batch Synchronization (Periodic):**
- Historical location data (every 5 minutes)
- Performance metrics and analytics
- Non-critical metadata updates
- System health and monitoring data

#### 8.2.2 Error Handling and Retry Logic
**HTTP Error Code Handling:**
- **2xx Series:** Success confirmation and logging
- **4xx Series:** Client error analysis and user notification
- **5xx Series:** Server error retry with exponential backoff
- **Network Failures:** Local queue management with persistent retry

**Retry Mechanisms:**
- Exponential backoff strategy (1s, 2s, 4s, 8s, 16s, max 60s)
- Maximum retry attempts: 5 for critical operations, 3 for non-critical
- Circuit breaker pattern for repeated failures
- Manual override capabilities for emergency scenarios

#### 8.2.3 Data Consistency and Conflict Resolution
**Conflict Resolution Rules:**
- Locus system as source of truth for tour assignments
- SONNY system as source of truth for field execution data
- Timestamp-based conflict resolution for concurrent updates
- Manual intervention required for critical data discrepancies

### 8.3 Integration Middleware Architecture

#### 8.3.1 API Gateway Layer
**Purpose:** Centralized API management and routing
**Components:**
- Request/response transformation
- Authentication and authorization
- Rate limiting and throttling
- Logging and monitoring
- Cache management for frequently accessed data

#### 8.3.2 Message Queue System
**Purpose:** Asynchronous processing and reliability
**Features:**
- Dead letter queue for failed messages
- Message persistence for system reliability
- Priority queuing for critical operations
- Monitoring and alerting for queue health

#### 8.3.3 Data Transformation Layer
**Locus to SONNY Mapping:**
- Tour structure conversion to internal format
- Task and visit data normalization
- Location data standardization
- Status code translation and mapping

**SONNY to Locus Mapping:**
- Field execution data formatting
- Photo and document encoding
- Status update standardization
- Error code translation

### 8.4 Backend Infrastructure Requirements

#### 8.4.1 Hosting and Deployment
**Infrastructure Specifications:**
- Cloud-based hosting with auto-scaling capabilities
- Load balancing for high availability
- Database clustering for performance and reliability
- CDN integration for photo and document storage
- Monitoring and alerting for system health

#### 8.4.2 Security and Compliance
**Security Requirements:**
- End-to-end encryption for all data transmission
- Secure API key management and rotation
- Audit logging for all user actions and system events
- Data backup and disaster recovery procedures
- GDPR compliance for personal data handling

#### 8.4.3 Performance and Scalability
**Performance Targets:**
- API response time: < 500ms for 95% of requests
- Concurrent user support: 1000+ active DAs
- Data throughput: 10,000+ location updates per minute
- System availability: 99.9% uptime SLA

---

## 9. First Iteration Scope

### 9.1 Minimum Viable Product (MVP) Definition

#### 9.1.1 Core Functionality
**MVP Scope:**
1. **Authentication System**
   - Basic login with Rider ID/password
   - Integration with Fulfillment Engine for validation
   - Forgot password functionality

2. **Tour Management**
   - Display assigned tours from Locus
   - Basic tour start/stop functionality
   - Individual task visibility and navigation

3. **Task Execution**
   - Pickup task workflow with photo capture
   - Drop-off task workflow with signature and photo
   - Basic proof of delivery submission

4. **Locus Synchronization**
   - Real-time event transmission to Locus dashboard
   - Photo upload and attachment to Locus records
   - Status update synchronization

#### 9.1.2 Excluded from First Iteration
- Advanced route optimization and resequencing
- In-app issue reporting and communication
- Offline functionality beyond basic caching
- Advanced analytics and reporting
- Custom administrative dashboard

### 9.2 Success Criteria for First Iteration

#### 9.2.1 Functional Success Metrics
- 100% successful authentication for active DAs
- Complete tour data synchronization from Locus
- All task completion events successfully transmitted to Locus
- Photo upload success rate > 99%
- Zero operational disruption during transition

#### 9.2.2 User Experience Metrics
- DA login completion time < 30 seconds
- Task completion workflow < 5 minutes per stop
- Photo capture and upload < 2 minutes per delivery
- User satisfaction score > 4.0/5.0 (compared to Locus baseline)

#### 9.2.3 Technical Performance Metrics
- Application startup time < 10 seconds
- Data synchronization latency < 30 seconds
- 99.9% application uptime
- < 1% data synchronization failures

### 9.3 Risk Mitigation for First Iteration

#### 9.3.1 Operational Continuity Risks
**Risk:** Disruption to existing operations during app replacement
**Mitigation:** 
- Parallel operation capability with Locus fallback
- Gradual rollout with pilot DA groups
- 24/7 support during transition period

#### 9.3.2 Data Synchronization Risks
**Risk:** Loss of operational visibility in Locus dashboard
**Mitigation:**
- Comprehensive testing of all Locus integration points
- Real-time monitoring of data synchronization
- Automatic fallback mechanisms for failed transmissions

#### 9.3.3 User Adoption Risks
**Risk:** DA resistance to new application
**Mitigation:**
- User training and onboarding program
- Feedback collection and rapid iteration
- Incentive programs for early adopters

---

## 10. Success Metrics and Acceptance Criteria

### 10.1 Business Success Metrics

#### 10.1.1 Operational Efficiency
- **Delivery Time Reduction:** 15% improvement in average delivery time per stop through optimized workflows
- **Route Optimization:** Measurable tracking of route deviations and efficiency gains via Locus tour analytics
- **Issue Resolution Time:** 50% reduction in average issue resolution time through streamlined reporting
- **Data Collection Improvement:** 100% real-time data capture vs. current end-of-day batch processing
- **Location Accuracy:** Real-time GPS tracking with 99%+ accuracy through Locus API integration

#### 10.1.2 Cost Efficiency and ROI
- **Locus Licensing Optimization:** Reduced mobile app licensing costs while maintaining administrative capabilities
- **Administrative Overhead:** 25% reduction in manual coordination effort through automated data sync
- **Training Costs:** Reduced onboarding time for new DAs with intuitive interface design
- **IT Infrastructure:** Reduced dependency on external vendor support and customization costs
- **Operational Scaling:** Foundation for cost-effective expansion without proportional increase in administrative overhead

#### 10.1.3 Data Quality and Business Intelligence
- **Real-time Visibility:** Complete operational visibility maintained in Locus dashboard through API integration
- **SLA Tracking:** Real-time delivery performance monitoring with automated alerts
- **Route Adherence:** Comprehensive tracking of planned vs. actual routes with deviation analysis
- **Exception Management:** Formal tracking and resolution of delivery exceptions with audit trails
- **Performance Analytics:** Enhanced business intelligence through granular data collection
- **Predictive Insights:** Foundation for advanced analytics and machine learning applications

#### 10.1.4 Strategic Business Value
- **Vendor Independence:** Reduced critical dependency on single vendor for mobile operations
- **Innovation Velocity:** Ability to rapidly implement business-specific improvements
- **Competitive Advantage:** Custom features aligned with actual operational workflows
- **Market Responsiveness:** Faster adaptation to changing business requirements
- **Data Sovereignty:** Enhanced control over operational data and customer information

### 10.2 Technical Acceptance Criteria

#### 10.2.1 Application Performance
- **Startup Performance:** Application launches within 10 seconds on standard Android devices
- **Battery Efficiency:** < 15% battery consumption during 8-hour delivery shift
- **Memory Usage:** < 200MB RAM consumption during active use
- **Storage Requirements:** < 500MB local storage for full operational capability

#### 10.2.2 Locus API Integration Reliability
- **API Success Rate:** 99.9% successful API calls to Locus endpoints
- **Location Update Performance:** Bulk location updates processed within 5 seconds
- **Task Status Sync:** < 30-second latency for critical status updates (STARTED, COMPLETED)
- **POD Upload Success:** 99%+ success rate for proof of delivery photo uploads
- **Tour Data Sync:** Complete tour synchronization within 60 seconds of assignment
- **Error Recovery:** Automatic retry with exponential backoff for 95% of API failures
- **Authentication Reliability:** Zero authentication failures during normal operations
- **Offline Capability:** 4-hour offline operation with complete data recovery upon reconnection

#### 10.2.3 Security and Compliance
- **Data Security:** End-to-end encryption for all sensitive data transmission
- **Authentication Security:** Multi-factor authentication capability
- **Audit Trail:** Complete logging of all user actions and system events
- **Data Privacy:** GDPR compliance for personal data handling

### 10.3 User Experience Acceptance Criteria

#### 10.3.1 Usability Standards
- **Task Completion Rate:** 95% successful task completion without assistance
- **User Error Rate:** < 5% user errors requiring correction or support
- **Learning Curve:** New DAs achieve proficiency within 2 hours of training
- **User Satisfaction:** Minimum 4.0/5.0 satisfaction score in user surveys

#### 10.3.2 Workflow Efficiency
- **Login Process:** Complete authentication within 30 seconds
- **Tour Overview:** Complete tour understanding within 2 minutes
- **Task Execution:** Average 3 minutes per delivery confirmation
- **Issue Reporting:** Problem reporting and escalation within 1 minute

---

## 11. Risk Assessment

### 11.1 Technical Risks

#### 11.1.1 Integration Complexity
**Risk Level:** High  
**Description:** Complex integration with Locus systems may introduce unexpected technical challenges
**Impact:** Potential delays in development timeline and data synchronization issues
**Mitigation Strategies:**
- Comprehensive API documentation and testing
- Dedicated integration testing environment
- Phased integration approach with fallback mechanisms
- Regular communication with Locus technical support team

#### 11.1.2 Data Synchronization Reliability
**Risk Level:** Medium  
**Description:** Real-time data synchronization failures could disrupt operations
**Impact:** Loss of operational visibility and potential service disruptions
**Mitigation Strategies:**
- Redundant synchronization pathways
- Local data persistence with queued retry mechanisms
- Real-time monitoring and alerting systems
- Manual override capabilities for critical scenarios

#### 11.1.3 Mobile Platform Dependencies
**Risk Level:** Medium  
**Description:** Android OS updates and device compatibility issues
**Impact:** Application compatibility problems and user experience degradation
**Mitigation Strategies:**
- Comprehensive device testing matrix
- Conservative minimum OS version requirements
- Regular compatibility testing and updates
- Device management and recommendation policies

### 11.2 Operational Risks

#### 11.2.1 User Adoption Challenges
**Risk Level:** High  
**Description:** DA resistance to new application and workflow changes
**Impact:** Reduced productivity and potential operational disruptions
**Mitigation Strategies:**
- Comprehensive user training and support programs
- Gradual rollout with feedback incorporation
- User champion program with early adopters
- Continuous user experience optimization

#### 11.2.2 Business Continuity During Transition
**Risk Level:** High  
**Description:** Operational disruptions during transition from Locus to SONNY
**Impact:** Service delivery delays and customer satisfaction issues
**Mitigation Strategies:**
- Parallel operation capabilities with fallback options
- Comprehensive testing in production-like environments
- 24/7 support during transition periods
- Rollback procedures for emergency scenarios

#### 11.2.3 Data Loss or Corruption
**Risk Level:** Medium  
**Description:** Critical operational data loss during system transition
**Impact:** Operational blind spots and compliance issues
**Mitigation Strategies:**
- Comprehensive data backup and recovery procedures
- Multi-tier data validation and verification
- Regular data integrity checks and auditing
- Emergency data recovery protocols

### 11.3 Business Risks

#### 11.3.1 Scope Creep and Timeline Extensions
**Risk Level:** Medium  
**Description:** Additional requirements and feature requests extending development timeline
**Impact:** Delayed ROI realization and increased development costs
**Mitigation Strategies:**
- Strict scope management and change control processes
- Regular stakeholder communication and expectation management
- Phased delivery approach with clear milestone definitions
- Dedicated product management and requirement prioritization

#### 11.3.2 Competitive Disadvantage During Development
**Risk Level:** Low  
**Description:** Operational inefficiencies during extended development period
**Impact:** Reduced competitive position and customer satisfaction
**Mitigation Strategies:**
- Rapid MVP delivery with incremental improvements
- Continuous operational optimization during development
- Regular competitive analysis and benchmarking
- Agile development methodology with frequent releases

---

## 12. Glossary

### 12.1 Business Terms

**Delivery Agent (DA):** Field personnel responsible for last-mile delivery of FMCG products to retail customers

**FMCG:** Fast-Moving Consumer Goods - rapidly selling, low-cost products with high turnover rates

**Locus:** Third-party logistics platform currently used for tour planning and DA management

**Route Optimization:** Process of determining the most efficient delivery sequence and path

**SLA (Service Level Agreement):** Defined performance standards for delivery timing and quality

**Tour:** Complete set of pickup and delivery tasks assigned to a single DA for execution

**Proof of Delivery (POD):** Documentation confirming successful delivery, typically including signatures and photos

### 12.2 Technical Terms

**API (Application Programming Interface):** Software interface enabling communication between different systems

**Fulfillment Engine:** Core backend system managing tour assignments, DA profiles, and operational data

**Geofencing:** Location-based service using GPS to create virtual boundaries for operational triggers

**Middleware:** Software layer facilitating communication and data management between different applications

**MVP (Minimum Viable Product):** Initial product version with core functionality for early user feedback

**SDK (Software Development Kit):** Collection of tools and libraries for application development

**Synchronization:** Process of maintaining data consistency across multiple systems in real-time

**Webhook:** HTTP-based callback mechanism for real-time data transmission between systems

### 12.3 Operational Terms

**Batch Processing:** Handling multiple operations simultaneously at scheduled intervals

**Exception Handling:** Process for managing and resolving operational deviations and issues

**Real-time Processing:** Immediate processing and response to operational events as they occur

**Route Deviation:** Difference between planned and actual delivery routes taken by DAs

**Task Completion Rate:** Percentage of assigned delivery tasks successfully completed within specified timeframes

**User Adoption Rate:** Percentage of target users actively utilizing the new system

---

## Document Control

**Document Version:** 1.0  
**Last Updated:** January 2025  
**Next Review Date:** February 2025  
**Document Owner:** Product Management Team  
**Approvers:** 
- Operations Manager
- Technical Lead
- Business Stakeholder

---

*This Software Requirements Specification serves as the foundational document for SONNY Delivery Agent App development and provides comprehensive guidance for all stakeholders involved in the project lifecycle.*
