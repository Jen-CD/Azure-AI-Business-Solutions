# Q&A Solution for FAQs (Using Azure AI Language and Azure Bot Service)

## Project Overview

This project was developed to demonstrate how Azure AI Language’s question answering capability can be utilised to develop a functional  **FAQ Chatbot** (Intelligent Conversational Agent) using a low-code/no-code approach,  which can be further improved to be used in real world business applications. The solution leverages **Azure AI Language**, **Azure AI Language Studio** and **Azure Bot Service** to create the Chatbot bringing conversational intelligence to traditional FAQs enabling users to ask questions in natural language and to receive appropriate answers. 
In the first step, Azure AI Language is utilised to create the knowledge base or the question and answer pairs which is then published to a REST endpoint which can be consumed by a Chatbot or  a client application.
This project addresses  a common business problem of efficiently managing and disseminating information without relying on advanced machine learning and coding expertise. This also demonstrates how modern cloud-based AI services can be used to build essential business applications, making AI accessible through low code, no code approach, including product managers and business analysts.

## Business Problem

In today's business world, organizations constantly face the challenge of effectively handling high volume of repetitive customer or employee queries. These questions, often related to product features, services or policies, consume significant time and resources from support and sales teams. Which in turn results:
- **Operational Inefficiency:** Human resources are tied up answering basic, repetitive questions instead of focusing on complex, high-value tasks.
- **Delayed Customer Support:** Wait time to receive responses or clarifications leads to poor user experience.
- **Inconsistent Information:** Without a single source of truth, different team members may provide slightly varied answers, causing confusion and a lack of trust.
Use of an Intelligent Conversation Agent can automate Question and Answering  process providing immediate and consistent which in turn will lead to improved operational efficiency and user satisfaction. This will also save resources, allowing human experts to handle more important business matters.

## Solution with Azure AI Services

This guide details the modern, low-code/no-code approach to building a fully functional Q&A Chatbot for Frequently Asked Questions (FAQs). 

This project's solution is built on a unified architecture connecting following three core Azure services to deliver a scalable and intelligent Q&A solution.This implementation strategy leverages the Azure AI Language Studio)as the centralized platform, which is Microsoft's current best practice for managing language capabilities.It also minimizes administrative overhead, integrates seamlessly with other Azure AI services (like Azure OpenAI), and provides a unified workspace for development.


**Azure AI Language**
Azure AI Language is a cloud-based service that provides advanced Natural Language Processing (NLP) capabilities using pre-trained machine learning models to help applications understand and analyze human text without requiring deep machine learning expertise. It's core capabilities include Sentiment Analysis (determining emotional tone), Key Phrase Extraction (identifying main topics), Named Entity Recognition (categorizing entities like people or places), and Language Detection. For this project, we utilise the Question Answering feature, which is a model trained to intelligently match a user's question in natural language to a specific answer from a knowledge base.

**Azure AI Language Studio**
The Azure AI Language Studio is a web-based user interface (UI) within Azure portal for exploring, building, and testing the features of Azure AI Language. Users can interact with Azure AI Language services without needing to write any code, configure APIs in an IDE, or manage dependencies. It facilitates rapid prototyping and experimentation, making AI capabilities accessible even to non-developers.

**Azure Bot Service**
Azure Bot Service simplifies the creation and deployment of conversational bots by providing a managed service and tools for integrating with channels such as websites or chat platforms. It enables hosting and running the Q&A chatbot logic, connecting the question answering model with user messages in real time.

## Step-by-Step Implementation Guide

The following steps demonstrate how Azure AI Language Services can be used to build a QnA chatbot that can answer frequently asked questions (FAQs) using content extracted from URLs, documents, or manually defined question–answer pairs.
A chatbot is then deployed using Azure AI Bot Service, enabling it to be accessed through web chat or connected to other channels such as Microsoft Teams.

In this project, an Azure Pay-As-You-Go (PAYG) account is being used. Azure Pay-As-You-Go allows users to provision and use Azure services without upfront costs or long-term commitments. You only pay for the resources you consume, and you can scale up or down as needed. This subscription type is ideal for experimentation, prototyping, and production workloads that require flexibility.

This project follows the following implementation process. The videos provided below correspond to the visual steps in the Azure AI portal.

**Step 1: Create an Azure Free Account/or Pay As You Go (PAYG) account**

If you don't already have one, create an Azure Free Account at https://azure.microsoft.com/free. This provides the necessary free credits and access to the services required to complete this project at no cost. If you already have consumed the free credits you may use a PAYG account.
Azure PAYG allows users to provision and use Azure services without upfront costs or long-term commitments. You only pay for the resources you consume, and you can scale up or down as needed. This subscription type is ideal for experimentation, prototyping, and production workloads that require flexibility.

**Step 2: Create an Azure AI LanguageResource (Azure Portal)**
Azure AI Language provides capabilities for tasks such as entity extraction, sentiment analysis, summarisation, and Custom Question Answering—the latest feature for QnA Maker.

This project uses Custom Question Answering to build a structured knowledge base that powers the chatbot.

Follow these steps to create the required Language resource:

1. Open the Azure Portal and sign in using your Azure credentials.
2. In the search bar, type 'Language service' and select it.
3. Select 'Create' under Language Service.
4. Select the 'Custom question answering' block. Then select 'Continue to create your resource'. You will need to enter the following settings:
    - Subscription: Your Azure subscription
    - Resource group: Choose an existing or select 'create new' and provide a name for the new resource group.
    - Region: Choose a supported region ex West Europe,UK South,East US,West US 
    - Name: Enter a unique name for the resource
    - Pricing tier: Select F0 (free), or S (standard) if F is not available.
    - Azure Search region: Choose a location in the same global region as your Language resource
    - Azure Search pricing tier: Free (F) (If this tier is not available, select Basic (B))
    - Responsible AI Notice: Agree
    - Click next,you may leave default values in nest Tabs; Network,Indentity and Tags and proceed to Review + Create.
    - Select Review + Create, then Create.

Wait for deployment to complete.

**Follow the video walkthrough:**

https://github.com/user-attachments/assets/0f2efb89-df78-42d5-a3d4-53c6313d8b54

**Step 3: Create a Custom Question Answering Project in Language Studio**

Language Studio is the browser-based interface used to create, train, and manage Custom Question Answering projects.

1. Once the resource is created, click 'Go to resource group'
2. Then from the list of resources in the resource group, select the Language resource you've just created.
3. Select 'Overview' in the left side menu and select 'Language Studio'.
4. When prompted provide the details required and select the name of the resource to be used in the QnA project, select 'Done'.
5. In the language studio select 'create new' to create a new project and select the type as 'Custom question answering'
6. Set the language and select 'Next'.
7. Then provide following information in the 'create a project' pane.
       - Name: provide a unique name
       - Description: provide a description for easy identification and management or leave blank
       - Provide a default fallback answer (e.g., “Sorry, I don’t have an answer for that yet.”)
8. Select 'Create project'
   
This will create a project with the name you provided above based on the language resouce created previously.

**Follow the video walkthrough:**


https://github.com/user-attachments/assets/1218704a-1781-4fc3-82b6-575f427e0f73


**Step 4: Add FAQ Sources to Build the Knowledge Base**

Custom Question Answering allows you to build the knowledge base using:
    - Website URLs
    - Documents (PDF, DOCX, TXT)
    - Manually created Q&A pairs

Once the project is created follow the following steps to setup the knowledge base.
1. Click 'Manage sources' in the left hand side menu.
2. In Manage sources click 'Add  source' and click 'Files' from the drop down to add files/documents containing question and answer pairs.
3. Click 'Add file' and select the file from the source, add a source name and click 'Add all'.
4. Repeat steps 2 to 4 to add any other files and URLs.
5. Finally, select 'Chitchat' from the dropdown, select 'Friendly' and then 'Add chit chat' to add built-in capability that allows your chatbot to handle casual, conversational, or small-talk interactions.

**Follow the video walkthrough:**


https://github.com/user-attachments/assets/4885a5a4-3e70-446d-a4b0-1b3674308807



**Step 5: Refine and Improve the Extracted Q&A Pairs**

The knowledge base can be further improved for responses and accuracy by adding new quation and answer pairs, adding alternate questions and follow up prompts.

1. Click 'Edit knowledge base' from the left hand menu, then click + sign under 'Question and answer pairs' and a new QnA pair
2. Select the source this needs to be added along with the question and answer.
3. Optionally add metadata tags, for example, categories like orders, payments, or cancellations).
4. Click 'Done'
5. Then click 'Add alternate question' to provide follow up on an answer by creating a multi-turn conversation that helps the user to refine an answer to a question.
6. It is possible to link more questions related to a particular QnA pair any adding follow up prompts.Click 'Follow up prompts' , then add the prompt to be dislayed and then link existing pair or create a link to a new pair.
7. Tick 'Show in contexual flow only' and click 'Add prompt'.

**Follow the video walkthrough:**



https://github.com/user-attachments/assets/f4372d23-8e99-417e-b215-efe2f8b677b8


**Step 6: Test the Knowledge Base**

You can test the knowledge base with the following steps before deployment.

1. After the changes have been saved, click the test button and this will open the test pane.
2. Enter sample questions to check the responses and greetings, small talk to check chitchat responses.
3. Return to 'Edit knowledge base' to improve the flow and answers.
4. Close the test pane once complete.
5. Select 'Deploy knowledge base' and proceed to create a chat bot.


**Step 7: Create a Chatbot Using Azure AI Bot Service**

Azure AI Bot Service enables you to convert your published knowledge base into a functioning chatbot.

1. Once the deployment is complete, select 'Create a bot'under next steps in the 'Deploy knowledge base' pane.
2. Then accept the validation of the code by clicking 'Yes, I trust the authors'
3. Provide the following in the 'Custom deployment' pane:
    - Subscription: Your subscription
    - Resource group: Use the same group as your Language resource
    - Bot handle: select a uniqu name or leave the default e.g., customer-faq-bot
    - Pricing Tier: Select free plan (F0)
    - Microsoft App ID: Set the access to Azure Bot resources (new or existing)
4. Click 'Next' to provide Web App details
    - App name: This the name of the bot.
    - Select the SDK language
    - Select App service plan, new or existing
    - Copy the 'Language resource key' (Go to the language resource, click 'Keys and Endpoint' under 'Resource Managment'. This is required to authernticate the request coming though the bot.
    - Leave the default values in the rest of the fields under 'App settings' and 'Language servie details'
    - Click 'Review + Create'
  
**Follow the video walkthrough:**


https://github.com/user-attachments/assets/2ea489a2-be64-437d-9f16-bc1326629e51

  
**Step 8: Test and fine tune the Chatbot**

Once the bot resource is created open the bot resource.
1. Click 'Bot profile' in the left hand side menu. You can add an icon, display name and the description.
2. Then select 'Test in Web Chat'. Ask sample questions to verify the answers and the flow including the greestings, infomal dialogues added with 'Chit chat'.
3. If changes are needed, return to Language Studio, update and republish.

  
**Follow the video walkthrough:**


https://github.com/user-attachments/assets/6eb0d93e-92e3-47cf-989f-f8ff00ed1c44


**Step 9: Embed the web chat code in the html page/Website**

1. Click 'Channels' under 'Settings'. This opens the list of channels already connected, and shows the health status and other channels available for connetion.
2. Click 'Web Chat', 'Default site' under 'Sites'. This opens the 'Configure the site' pane.
3. Copy the code under 'Embedded code' section and the secret key.In the code replace 'YOUR_SECRET_HERE' with the secret key.
4. Now copy and paste iframe code in the web site/html page you need the chat bot to run. Update and publish the page.


**Follow the video walkthrough:**



https://github.com/user-attachments/assets/40ef0116-c38f-4ad0-bd57-2de0d4ad75ee




## Concluding Remarks

Completing this Q&A Chatbot project allowed me to strengthen my understanding of Azure AI Language and gain hands-on experience with conversational AI, natural language understanding, and knowledge-based question answering.This project helped connect theory to implementation and showed how Azure AI Language can be applied to create intelligent support experiences. I hope this serves as a useful reference for anyone exploring real-world conversational AI using Microsoft Azure technologies.

By completing this project, I developed the following skills:

- Question Answering with Azure AI Language – Building knowledge bases and returning precise answers from FAQ content.
    
- Conversational AI – Designing interactive chat experiences that understand natural language questions.
    
- Azure AI Language Studio – Creating, configuring, and testing language features without writing code.
    
- No-Code AI Solution Development – Demonstrating how real business use cases can be implemented without complex machine learning development.
    
- Customer Self-Service Automation Thinking – Understanding how conversational interfaces reduce support workload and improve accessibility to organizational knowledge.




## About Me

I'm a Product Manager transitioning into the AI space. I hold:

- AZ-900 Certified (Azure Fundamentals)
- AI-900 Certified (Azure AI Fundamentals)
- PRINCE2 Agile Practitioner

Follow my journey in LinkedIn at https://www.linkedin.com/in/jinendra-dharmapala/ and check out more projects on this repo.


































