## Low Code / No Code Langflow & Mistral AI Tax Document QA Chatbot


This project demonstrates how to build a question-and-answer chatbot using Langflow, with a document loaded from local memory. Instead of OpenAI, we used Mistral AI for the LLM model.

**Langflow** is a visual framework for building multi-agent and RAG applications. It is Open-source, Python-powered, fully customizable, LLM and vector store agnostic

**Important Note :** Detailed instructions on how to install and build on Langflow are contained on their github [link here](https://github.com/langflow-ai/langflow?utm_source=datastax&utm_medium=referral&utm_campaign=langflow-announcement&utm_content=blog).

### Prerequisites

1. **Langflow installed and running**
  ```shell
     # Make sure you have >=Python 3.10 installed on your system.
     python -m pip install langflow -U
  ```

Then, run Langflow with:

 ```shell
     python -m langflow run
 ```

A successful install and run would show the access link as shown below, which will open in your default browser. I ran the installation through vscode, but feel free to leverage your favorite IDE.

 ![Langflow1](https://github.com/ghwallis/QAwithpdf/assets/36977382/ce00c5e2-2476-4852-8bcd-cf96e2cee3f7)

 2. **Mistral AI API key created**

 You will need to create a Mistral AI account to generate an API key. Please note that Mistral is only free for a limited time after you create an account. Access the console through the [link here](https://console.mistral.ai/api-keys/)
 
  ![MistralAPI](https://github.com/ghwallis/QAwithpdf/assets/36977382/d4744e20-75c0-4bae-a03e-fa4858ad43f5)

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

 ![Langflow2](https://github.com/ghwallis/QAwithpdf/assets/36977382/14874792-f316-49e1-9848-9e7d929565da)


### Setting Up the Mistral AI Component

 1. To create an environment variable for the Mistral AI component, in the Mistral AI API Key field, click the Globe button, and     then click Add New Variable.
 2. In the Variable Name field, enter mistral_api_key.
 3. In the Value field, paste your Mistral AI API Key.
 4. Click Save Variable.
    
  ![MistralAP2](https://github.com/ghwallis/QAwithpdf/assets/36977382/d4439dc9-9a96-471d-9edc-4092544774ba)

### Loading a Document

1. In the Files component, click within the Path field.
2. Select a local file, and then click Open.
3. The file name appears in the field.

 ![MistralAP3](https://github.com/ghwallis/QAwithpdf/assets/36977382/39dab622-7d9d-4740-9dab-223df9e96f0c)
  
### Running the Document QA Flow

1. Click the Run button. The Interaction Panel opens, where you can converse with your bot.
2. Type a message and press Enter.

For this example, we loaded a document on US 482 Regulations regarding methods to determine taxable income in connection with a transfer of intangible property. We asked, "What is an intangible? can you give me some examples?" The bot responded with an accurate summary based on the contents of the document.

![Langflow3](https://github.com/ghwallis/QAwithpdf/assets/36977382/a09c5db5-bfbc-4c0d-b0d4-066ebbf9bda1)

![Langflow4](https://github.com/ghwallis/QAwithpdf/assets/36977382/1f0fc417-c3e8-43f5-9259-e1fb82d95dd8)

### Sharing

Builders have a couple of options to share workflows:

 -  Export workfow in json format. Once exported, worflow can be run
   ```python from langflow.load import run_flow_from_json

      results = run_flow_from_json("path/to/flow.json", input_value="What is an intangile?")
   ```

 - Other methods for further integrastion to other applications.
   
   ![Langflow5](https://github.com/ghwallis/QAwithpdf/assets/36977382/7b58e87c-41bb-4a36-b04c-ea353df65619)


### Conclusion

This project showcases how to leverage Langflow and Mistral AI to create a functional Document QA chatbot that can provide context-aware answers based on the content of a loaded document, such as the US 482 Regulations on methods to determine taxable income in connection with a transfer of intangible property. 

Feel free to reach out if you have any questions/suggestions or ideas for a project. Thanks for reading!
