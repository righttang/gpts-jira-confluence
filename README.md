# GPTs-Jira-Confluence Integration Guide

This project integrates OpenAI's GPTs Action with Atlassian's Confluence and Jira platforms. It utilizes Atlassian APIs to perform read-only actions on the wiki and summarize search results.

## Overview

- **Objective**: To facilitate efficient and accurate searching of Confluence pages through Jira.
- **Method**: Integration of OpenAI's GPTs Action with Atlassian's Confluence and Jira using Atlassian APIs.
- **Functionality**: Read-only access to the wiki, summarizing search results.

## Demo

*The demo section will showcase the functionality or provide a link to a demonstration.*

## Setup Instructions

### Step 1: Create a Jira Token

1. **Generate Token**: Visit [Atlassian API Tokens](https://id.atlassian.com/manage-profile/security/api-tokens) to create a new API token.

### Step 2: Encode Your Token with HTTP Basic Auth

1. **Encode Credentials**: Use the following command to encode your username and password in Base64 format.

   ```bash
   echo -n 'myusername:mypassword' | base64
   ```

### Step 3: Create GPTs

1. **Access GPTs Editor**: Go to [GPTs Editor](https://chat.openai.com/gpts/editor).
2. **Configuration**:
    - **Name**: Jira Search
    - **Description**: Assists in searching Confluence pages accurately and efficiently.

3. **Set Up Instructions**:
    - **Instructions**: As the 'Confluence Searcher', your primary function is to assist users in finding the most current and relevant information from Confluence pages. Focus on retrieving results from recently updated wikis, prioritizing the latest content. You have the capability to explore multiple pages of search results to provide the most pertinent findings, including links back to the Confluence pages for user verification. Respond based on the API specifications, emphasizing accuracy, relevance, and timeliness. In cases of unclear or incomplete queries, prompt for clarifications. Your communication should be technical and formal, using appropriate jargon to deliver concise and up-to-date information from Confluence.

4. **Conversation Starters**:
    - Example: "When is the first Olympic games start?"

5. **Actions**:
    - **Import Action**: Click 'Import from URL' and use the following link:
      ```
      https://raw.githubusercontent.com/righttang/gpts-jira-confluence/main/api-spec.json
      ```
    - Update the Spec inline with your wiki address, must ends with `/wiki`. Example:
      ```json
      "url": "https://ai-gold-rush.atlassian.net/wiki"
      ```

6. **Add Authentication**:
    - Click 'API Key'.
    - Choose 'Basic Auth'.
    - Add the key you generated on Step 2.

7. **Privacy Policy**:
    - Include a link to your private policy.

*Once these steps are completed, your integration should be ready to use.*
