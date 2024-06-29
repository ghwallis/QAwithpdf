## Transfer Pricing Document QA Chatbot with Langflow & Mistral AI


This project demonstrates how to build a question-and-answer chatbot using Langflow, with a document loaded from local memory. Instead of OpenAI, we used Mistral AI for the LLM model.

**Important Note :** Detailed instructions on how to install and build on Langflow are contained on the github [link here](https://github.com/langflow-ai/langflow?utm_source=datastax&utm_medium=referral&utm_campaign=langflow-announcement&utm_content=blog).

### Prerequisites

 - Langflow installed and running
 - Mistral AI API key created


### Creating the Document QA Project

From the Langflow dashboard, click New Project.
Select Document QA from the template option. You also have an option to selected a blank canvas to include each of the components listed below.

This creates a basic chatbot flow with the following components:

 - Chat Input
 - Prompt
 - Mistral AI (replacing the OpenAI component)
 - Chat Output
 - Files

The Files component loads a file from your local machine into the Prompt component as {Document}. The Prompt component is instructed to answer questions based on the contents of {Document}. Including a file with the prompt gives the Mistral AI component context it may not otherwise have access to.

### Setting Up the Mistral AI Component

 1. To create an environment variable for the Mistral AI component, in the Mistral AI API Key field, click the Globe button, and     then click Add New Variable.
 2. In the Variable Name field, enter mistral_api_key.
 3. In the Value field, paste your Mistral AI API Key.
 4. Click Save Variable.


### Loading a Document

1. In the Files component, click within the Path field.
2. Select a local file, and then click Open.
3. The file name appears in the field.

TIP: The file must be of an extension type listed here.

### Running the Document QA Flow

1. Click the Run button. The Interaction Panel opens, where you can converse with your bot.
2. Type a message and press Enter.

For this example, we loaded a document on US 482 Regulations regarding methods to determine taxable income in connection with a transfer of intangible property. We asked, "What are the methods to determine taxable income in a transfer of intangible property?" The bot responded with an accurate summary based on the contents of the document.

### Conclusion

This project showcases how to leverage Langflow and Mistral AI to create a functional Document QA chatbot that can provide context-aware answers based on the content of a loaded document, such as the US 482 Regulations on methods to determine taxable income in connection with a transfer of intangible property.
