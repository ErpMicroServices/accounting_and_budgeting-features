# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this module.

## Module Overview

The `accounting_and_budgeting-features` module contains Behavior Driven Development (BDD) feature specifications for the accounting and budgeting domain. This module defines the business requirements and acceptance criteria in Gherkin format, serving as both documentation and executable specifications for the accounting and budgeting functionality.

## Technology Stack

- **Specification Language**: Gherkin (Cucumber)
- **Format**: `.feature` files
- **Purpose**: Business requirements documentation and automated testing specifications

## Project Structure

```
accounting_and_budgeting-features/
├── LICENSE                    # Apache 2.0 license
├── README.md                 # Module documentation
└── *.feature                # Gherkin feature specifications
```

## Feature Organization

This module contains feature files that describe:

### Core Accounting Features
- **General Ledger Management**: Chart of accounts, account hierarchies, and balances
- **Transaction Processing**: Journal entries, posting, and transaction validation
- **Financial Reporting**: Balance sheets, income statements, and custom reports
- **Audit Trail**: Transaction history and compliance requirements

### Budgeting Features
- **Budget Creation**: Budget templates, categories, and approval workflows
- **Budget Monitoring**: Actual vs. budget comparisons and variance analysis
- **Budget Controls**: Spending limits, authorization levels, and alerts
- **Reporting**: Budget performance reports and forecasting

## Development Workflow

### Adding New Features
1. **Business Analysis**: Work with stakeholders to understand requirements
2. **Feature Writing**: Create `.feature` files using Gherkin syntax
3. **Review Process**: Validate scenarios with business stakeholders
4. **Integration**: Ensure features align with database and endpoint specifications

### Feature File Standards
```gherkin
Feature: [Business Capability]
  As a [User Role]
  I want to [Business Goal]
  So that [Business Value]

  Background:
    Given [Common Preconditions]

  Scenario: [Specific Business Scenario]
    Given [Initial Context]
    When [Action Taken]
    Then [Expected Outcome]
```

## Gherkin Writing Guidelines

### Scenario Structure
- **Given**: Set up initial state and context
- **When**: Describe the action or event
- **Then**: Define expected outcomes and validations
- **And/But**: Continue the same step type for readability

### Best Practices
- **Business Language**: Use terms familiar to domain experts
- **Declarative Style**: Focus on what, not how
- **Independent Scenarios**: Each scenario should be self-contained
- **Data Tables**: Use for multiple similar test cases
- **Scenario Outlines**: Parameterize similar scenarios

### Tags for Organization
```gherkin
@accounting @critical
@budgeting @regression
@financial_reporting @integration
```

## Integration Points

### Database Integration
- Features must align with database schema in `accounting_and_budgeting-database`
- Data setup scenarios should match available test data
- Database state validation should be clearly specified

### API Integration
- Features should define expected API behaviors for accounting endpoints
- Request/response formats should be specified in scenarios
- Error handling and edge cases must be covered

### UI Integration
- User interface behaviors should be described from user perspective
- Screen navigation and user interactions should be clearly defined
- Accessibility and usability requirements should be included

## Testing Integration

### Cucumber Test Execution
- Features are executed by corresponding step definition modules
- Database interactions are tested through appropriate database modules
- API testing is handled by endpoint-specific test implementations

### Test Data Management
- Test data requirements should be specified in Given steps
- Data cleanup should be implicit in scenario design
- Shared test data should be documented in Background sections

## Documentation Standards

### Feature Documentation
Each feature file should include:
- **Business justification** in the feature description
- **Acceptance criteria** clearly defined in scenarios
- **Edge cases** and error conditions covered
- **Dependencies** on other features noted

### Scenario Documentation
- **Clear naming**: Scenario names should describe business value
- **Complete coverage**: Happy path, alternative flows, and error cases
- **Maintainable**: Scenarios should be resilient to implementation changes

## Quality Standards

### Review Criteria
- **Business Alignment**: Features must represent real business needs
- **Testability**: All scenarios must be implementable as automated tests
- **Clarity**: Features should be understandable by non-technical stakeholders
- **Completeness**: All major user workflows should be covered

### Maintenance Guidelines
- **Version Control**: All changes should be tracked and reviewed
- **Backward Compatibility**: Changes should not break existing scenarios
- **Refactoring**: Regular cleanup of duplicate or obsolete scenarios
- **Living Documentation**: Features should be updated as requirements evolve

## Important Notes

- **Pure Specification**: This module contains only feature files, no implementation code
- **Domain Focus**: Features are specific to accounting and budgeting business processes
- **Executable Documentation**: Features serve as both requirements and test specifications
- **Stakeholder Communication**: Features should be reviewable by business users
- **Regulatory Compliance**: Consider regulatory requirements in scenario design