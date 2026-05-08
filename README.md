# Field Insight Pro - Salesforce Field Reference Finder

Field Insight Pro is a Chrome extension that helps you find where a Salesforce field is referenced by using your active Salesforce browser session.

No separate Salesforce login is required.

## Overview

This extension connects to the Salesforce org that is already open in Chrome, loads objects and fields, and searches Salesforce metadata for field references.

It is useful when you want to understand field usage before changing, deleting, renaming, or refactoring Salesforce fields.

## Features

- Uses your active Salesforce browser session
- No separate OAuth flow or username/password login
- Detects Salesforce tabs and Salesforce session cookies
- Inspector-style action indicator
  - Grey badge when not on a Salesforce page
  - Blue badge when on a Salesforce page
- Loads all available Salesforce objects through the REST API
- Loads fields for a selected object through the object describe API
- Finds references using Salesforce Tooling API dependencies
- Includes fallback scanning for Lightning Page / FlexiPage field references
- Supports newer FlexiPage metadata structure:
  - `flexiPageRegions`
  - `itemInstances`
  - `fieldInstance`
- Filters and displays common Salesforce metadata references
- Supports table search/filtering
- Allows copying results as CSV
- Allows copying Excel-friendly tab-delimited text
- Allows downloading results as an Excel-compatible file
- Includes hidden debug logs for troubleshooting
- Supports local usage counters if enabled:
  - Extension opens
  - Searches run

## Supported reference types

The extension attempts to detect references in metadata types such as:

| Reference Type | Description |
|---|---|
| `ApexClass` | Apex class references |
| `ApexTrigger` | Apex trigger references |
| `ApexPage` / `VisualforcePage` | Visualforce page references |
| `ApexComponent` / `VisualforceComponent` | Visualforce component references |
| `AuraDefinition` / `AuraDefinitionBundle` | Aura component references |
| `LightningComponentBundle` | Lightning Web Component references |
| `Flow` | Flow references |
| `ValidationRule` | Validation rule references |
| `Layout` | Page layout references |
| `FlexiPage` | Lightning Page references |
| `FlexiPageFieldInstance` | Field placed directly on a Lightning Page |

## FlexiPage / Lightning Page support

Salesforce changed the FlexiPage metadata structure in newer API versions.

Older Lightning Page metadata often exposed field usage through component instances or dependency records. Newer FlexiPage metadata can store field placements inside item instances.

This extension includes a FlexiPage metadata fallback scanner that retrieves the full FlexiPage metadata through the Tooling API and scans:

```text
FlexiPage.Metadata.flexiPageRegions[].itemInstances[].fieldInstance
