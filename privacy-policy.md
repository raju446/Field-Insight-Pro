# Privacy Policy

Salesforce Field Reference Finder is a browser extension with one narrow purpose: to help users find where a selected Salesforce field is referenced in metadata for the currently open Salesforce org.

The extension communicates directly between the user's web browser and Salesforce servers. No data is sent to the developer or to any other third party.

## Salesforce API Communication

The extension communicates with Salesforce using official Salesforce web service APIs on behalf of the currently logged-in user.

This means the extension can access only the Salesforce data and metadata that the logged-in user has already been granted permission to access in Salesforce.

Salesforce API calls from the extension reuse the Salesforce session used by the browser to access Salesforce. To use this session, the extension requires permission to read Salesforce browser cookie information for Salesforce domains.

The Salesforce session cookie is used only locally in the user's browser to call Salesforce REST and Tooling APIs. The session cookie is not transmitted to the developer, stored on external servers, sold, or shared with third parties.

## Data Access

The extension may access the following information only for its field-reference lookup purpose:

- The active Salesforce tab URL, to identify the currently selected Salesforce org.
- Salesforce session cookie information for Salesforce domains, to authenticate Salesforce API requests.
- Salesforce metadata needed to find field references, such as:
  - Salesforce object names
  - Salesforce field names
  - Apex class and trigger names
  - Flow names
  - Layout names
  - Validation Rule names
  - Lightning Page / FlexiPage names
  - Field-reference search results

The extension does not access or process non-Salesforce websites.

## Data Collection and Sharing

The extension does not collect, sell, transfer, or share user data with third parties.

The extension does not transmit Salesforce session cookies, Salesforce metadata, browsing history, or search results to any external server.

All processing occurs locally in the user's browser and through direct API calls from the browser to the user's Salesforce org.

## Local Storage Policy

The extension may save limited information in the browser's local storage to avoid redundant queries and remember extension preferences.

Local storage may include:

- Selected Salesforce org URL
- Source Salesforce tab identifier
- Extension preferences
- Query or search history, if this feature is enabled
- Saved queries, if this feature is enabled
- Environment type, such as Production or Sandbox
- Temporary debug logs or search results shown in the extension page

The extension does not use local storage to store Salesforce SObject record data such as Account, Contact, Opportunity, Case, or similar business records.

Local storage data remains in the user's browser and is not sent to the developer or any third party.

Users may clear local storage data by clearing browser site data, clearing extension data, or removing the extension.

## Permissions

The extension uses Chrome permissions only for its single purpose.

- **activeTab:** Used to identify the Salesforce tab from which the user launches the extension.
- **cookies:** Used to read the Salesforce session cookie for the selected Salesforce org so Salesforce API calls can be made using the user's existing Salesforce session.
- **storage, if enabled:** Used to temporarily remember the selected Salesforce org URL, source tab, preferences, and related extension state.
- **Salesforce host permissions:** Used to call Salesforce REST and Tooling APIs for field-reference lookup.

## Remote Code

The extension does not use remote code.

All JavaScript, HTML, CSS, and assets are packaged inside the extension. The extension does not load external scripts, execute downloaded code, or use remote-hosted JavaScript libraries.

## User Control

Users can validate the behavior of the extension by inspecting the source code and monitoring network traffic in the browser developer tools.

Users may remove stored extension data by clearing browser storage or uninstalling the extension.
