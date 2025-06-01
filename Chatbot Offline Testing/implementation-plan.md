# N8N AI Sales Analysis Implementation Plan

## Project Overview
An n8n workflow that uses AI agents to analyze sales data and provide insights in response to natural language queries. The system will analyze a static dummy dataset of sales information across categories, regions, and time periods.

## Data Structure
Static CSV data with the following fields:
- `category`: beverages, detergents, oral care, snacks
- `sku`: 2-3 random SKUs per category
- `region`: Cairo, Alexandria, Upper Egypt
- `month`: Jan-23 to May-25
- `target_volume`: Target sales volume for the period
- `target_value`: Target sales value (revenue) for the period
- `actual_volume`: Actual sales volume achieved
- `actual_value`: Actual sales value (revenue) achieved

## Workflow Components

### 1. Entry Points
- **Webhook Trigger**: Receives user queries from external applications
- **N8N Chat Input**: For testing during development

### 2. Data Management
- **Code Node (Data Storage)**: Embeds static CSV data as a string
- **CSV Parser**: Converts string data to structured format
- **Function Node (Data Preprocessing)**:
  - Calculate derived metrics (price = value/volume)
  - Structure data for efficient analysis
  - Create time-based aggregations (monthly, quarterly, annual)

### 3. Context Management
- **Function Node (Conversation History)**: Tracks user interaction history
- **Memory Node**: Stores preprocessed data for quick access
- **Set Node**: Maintains session variables

### 4. Query Processing
- **Function Node (Query Categorization)**: Determines analysis type from user input
- **Split Node**: Routes to appropriate analysis workflows
- **Function Nodes (Data Filtering)**: Selects relevant data subsets based on query

### 5. AI Integration
- **AI Agents Node (Anthropic Claude)**:
  - Input: User query + relevant data context
  - Output: Analysis results and insights
- **AI Agents Node (Follow-up Generator)**:
  - Generates potential follow-up questions based on analysis

### 6. Response Handling
- **Function Node (Response Formatting)**: Structures AI output for readability
- **Merge Node**: Combines insights with follow-up suggestions
- **Webhook Response**: Returns formatted response to user

## Analysis Capabilities

### 1. Value, Volume & Price Analysis
- SKU performance analysis
- Price point optimization insights
- Volume vs. value growth patterns

### 2. Time Period Analysis
- Monthly performance tracking
- Quarterly trend analysis
- Annual performance evaluation
- Year-to-date (YTD) progress

### 3. Hierarchical Analysis
- Category-level performance
- Regional sales breakdown
- Total sales overview
- Individual SKU deep-dives

### 4. Comparative Analysis
- Year-over-Year (YoY) comparison
- Period-over-Period comparison
- Performance vs. Target
- YTD vs. Budget
- Annual projection vs. Budget

## Implementation Steps

1. **Setup & Environment Preparation**
   - Create n8n workflow
   - Set up required nodes
   - Configure webhook endpoints

2. **Data Layer Implementation**
   - Embed static CSV data
   - Implement data parsing logic
   - Build preprocessing functions

3. **AI Integration**
   - Configure Anthropic Claude AI agent nodes
   - Design effective prompts
   - Implement context management

4. **Analysis Logic**
   - Build calculation functions for each analysis type
   - Implement comparison logic
   - Create data aggregation functions

5. **Response Handling**
   - Format AI responses for readability
   - Implement follow-up question generation
   - Structure final output

6. **Testing & Refinement**
   - Test with sample queries
   - Refine prompts and analysis logic
   - Optimize performance

## Demo Considerations
- Focus on simple but effective demonstration
- Use business terminology but maintain accessibility
- Highlight ability to extract insights from basic questions
- Showcase AI's ability to suggest valuable follow-up questions
- Ensure responses are concise but informative

## Implementation Checklist

### 1. Setup & Environment Preparation
- [x] Create new n8n workflow
- [x] Set up webhook trigger node
- [x] Configure n8n chat input node for testing
- [x] Test basic workflow connectivity
- [x] Connect with Anthropic Claude

### 2. Data Layer Implementation
- [x] Create static CSV data structure (using JSON format instead)
- [x] Implement code node for data storage
- [x] Set up data preprocessing code node
  - [x] Implement price calculation logic
  - [x] Set up time-based aggregations
  - [x] Create data structuring functions
- [x] Test data parsing and preprocessing

### 3. Context Management
- [ ] Implement conversation history tracking (optional for demo)
- [ ] Set up memory node for data caching (optional for demo)
- [ ] Configure session variables (optional for demo)
- [ ] Test context persistence (optional for demo)

### 4. Query Processing
- [x] Create query categorization code node
- [x] Set up split node for workflow routing (handled by query type logic)
- [x] Implement data filtering in code node
- [x] Test query processing with sample inputs
- [x] Add UserQueryTemp node for reliable query input

### 5. AI Integration
- [x] Configure Anthropic Claude AI agent node
- [x] Design and implement analysis prompts
- [x] Set up follow-up question generator (handled by AI prompt)
- [x] Test AI response generation
- [x] Implement context management for AI (basic, via prompt)

### 6. Analysis Logic
- [~] Implement value, volume & price analysis functions (basic done, advanced logic in progress)
- [~] Create time period analysis logic (basic done, advanced logic in progress)
- [~] Build hierarchical analysis capabilities (basic filtering, can be expanded)
- [~] Implement comparative analysis functions (in progress: e.g., growth vs. last period)
- [ ] Test all analysis types with sample data
- [~] Implement value growth calculation at all qn_levels and periods (in progress)
- [ ] Implement volume growth calculation at all qn_levels and periods
- [ ] Implement price per unit growth calculation at all qn_levels and periods
- [ ] Implement value performance vs. target at all qn_levels and periods
- [ ] Implement volume performance vs. target at all qn_levels and periods
- [ ] Implement price per unit performance vs. target at all qn_levels and periods
- [ ] Ensure all calculations can be filtered by qn_level (total, category, region, SKU) and period (month, quarter, year, YTD) based on user query
- [ ] Pass only the relevant result and context to the AI for explanation

### 7. Response Handling
- [x] Create response formatting function
- [x] Set up merge node for combining insights (handled in formatting/AI)
- [x] Configure webhook response node (if needed)
- [x] Test end-to-end response flow

### 8. Testing & Refinement
- [ ] Test with sample business queries
- [ ] Refine AI prompts based on results
- [ ] Optimize performance
- [ ] Document known limitations
- [ ] Create user guide for query examples
- [ ] Test each business question at each qn_level and period
- [ ] Refine filtering and calculation logic for edge cases (e.g., missing data, zero targets)
- [ ] Validate AI explanations for clarity and business value

### 9. Documentation
- [ ] Document workflow structure
- [ ] Create troubleshooting guide
- [ ] Add comments to complex functions
- [ ] Update README with setup instructions 