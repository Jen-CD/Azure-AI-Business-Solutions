# Intelligent Customer Feedback Analysis with Azure AI Language

## Project Overview
This project demonstrates how to leverage **Azure AI Language** services in analysing customer feedback, with a focus on Sentiment Analysis and Key Phrase Extraction.**Azure AI Language** is a part of the Azure AI services which is capable of performing advanced Natural Language Processing(NLP) over unstructured text emails,online reviews,social media posts,paper articles, business documents, and more to offer following features.
- Named entity recognition: Identifies people, places, events, and more. This feature can also be customized to extract custom categories.
- Entity linking: Identifies known entities together with a link to Wikipedia.
- Personal identifying information (PII) detection: Identifies personally sensitive information, including personal health information (PHI)
- Language detection: Identifies the language of the text and returns a language code such as "en" for English.
- Sentiment analysis and opinion mining: Identifies whether text is positive, negative or neutral.
- Summarization: Summarizes text by identifying the most important information.
- Key phrase extraction: Lists the main concepts from unstructured text.

In this project, Sentiment Analysis and Key Phrase Extraction are performed on a sample set of customer reviews using **Azure AI Language Studio**, all with minimal or no coding. The goal is to showcase the power of no-code AI tools available within the **Azure Foundry Portal**, making them accessible to both technical and non-technical users.

What sets this project apart is its conceptual application of **Agentic AI** principles, illustrating how an AI system can move beyond basic analysis to provide actionable insights from customer feedback, even without complex code. While this version uses the visual interface of Azure Language Studio, the project can be further enhanced by integrating custom Python scripts to automate and scale the workflow.

This is a practical, beginner-friendly example of how real-world AI applications can be built using cloud-based tools with a clear path for future development into more advanced, agent-driven solutions.


## Business Problem

In today's business world or in any industry, customer feedback is a goldmine of insights, but it often comes as vast, unstructured data from different channels like emails, surveys, chat logs, app reviews. (emails, chat logs, social media comments, survey responses). Yet Product Managers and customer support teams struggle to:
- Quickly gauge customer sentiment
- Spot pain points or requests
- Prioritize high impact issues that need immediate attention
- Extract actionable insights without manually reviewing feedback
Failing to generate above insights leads to missed opportunities, delayed fixes, and a reactive approach to product improvement.


## Solution with Azure AI Language

### Azure AI Language
Azure AI Language is a cloud based service that provides advanced Natural Language Processing (NLP) capabilities using pre-trained machine learning models to help applications understand and analyze human text without requiring deep machine learning expertise. It's core capabilities include Sentiment Analysis (determining emotional tone), Key Phrase Extraction (identifying main topics), Named Entity Recognition (categorizing entities like people or places), and Language Detection. It also supports Question Answering and Conversational Language Understanding for building intelligent bots. This service allows developers and business users to extract valuable insights from unstructured text data to solve real world problems like customer feedback analysis and improving customer support with conversational interfaces.

### Azure AI Language Studio
The Azure AI Language Studio is a web-based user interface (UI) within Azure portal for exploring, building, and testing the features of Azure AI Language. Users can interact with Azure AI Language services without needing to write any code, configure APIs in an IDE, or manage dependencies. It facilitates rapid prototyping and experimentation, making AI capabilities accessible even to non-developers. 

### Azure AI Foundry
Azure AI Foundry is the new unified platform for development, training, and deployment of AI models/solutions. While it is possible to provision indvidual AI services resources, Azure AI Foundry brings together various Azure AI services and tools into a single, comprehensive environment streamlining project organization, resource management and data orchestration in AI lifecycle from concept to production. It acts as a central hub for building robust and scalable AI applications incorporating responsible AI practices.

Azure AI Foundry portal is the web-based visual interface of AI Foundry for working with AI projects. It also provides the Azure AI Foundry SDK, which you can use to build AI solutions programmatically.

In this project, it is demonstrated how Azure AI Language in Azure AI Foundry portal is used to perform, 
- Sentiment Analysis: Determining the emotional tone (positive, negative, neutral) of text
- Key Phrase Extraction: Identifying key points or topics within a text
  
## Steps to Replicate This Project

The following steps demonstrate how azure AI language services can be used in Azure AI Foundry portal to perform sentiment analysis and key phrase extraction on a customer reviews extracted from a data set. 

Data source: https://www.kaggle.com/datasets/crowdflower/twitter-airline-sentiment  

In this project the Azure free account is being used. The Azure Free Account allows new users to explore Microsoft Azure services at no cost. It includes $200 in free credit (valid for 30 days) and access to 55+ always free services. Additionally, users get 12 months of free access to popular services like Virtual Machines, Storage, and Databases within specified usage limits.

### 1. **Create an Azure Free Account (if you don't have one)**

- Go to the Azure Free Account page (https://azure.microsoft.com/free).
- Follow the prompts to sign up. You will need a Microsoft account, phone number, and a credit/debit card for identity verification (you won't be charged unless you exceed free limits or upgrade).
- Once signed up, navigate to the Azure Portal.

### 2. **Create a project in Azure AI Foundry portal**

There are two main types of projects within Azure AI Foundry, designed to suit different organizational structures and scales, particularly for generative AI development:

**Foundry Projects:** These are the default and simplest project type, associated with an Azure AI Foundry resource in an Azure subscription.They provide support for the most common AI development tasks to develop generative AI chat apps and agents. It requires minimal amount of administrative resource management, and can be accessed thorugh Azure Foundry portal, making it easy to add connected resources and manage model and agent deployments. These projects are ideal for individuals or smaller teams to quickly explore, build, test, and deploy generative AI solutions.

**Azure AI hub based project**
Hub-based projects are associated with an Azure AI hub resource in an Azure subscription. Azure AI hub resource include an Azure AI Foundry resource, storage and Azure key vault resources, as well as managed compute and support for prompt Flow development. Users can access Hub resource through both Azure AI Foundry portal and Azure Azure Machine learning portal to create projects from the hub. This supports collaboraitve projects and provides centralized governance, resource management, and shared infrastructure, ensuring consistency and control across multiple teams and projects within an enterprise environment.

In this demo, we use  a Foundry project and the following steps explain creating a new Azure AI Foundry resource in Azure AI Foundry portal.

1. Open the Azure AI Foundry portal at https://ai.azure.com and use your Azure credentials to sign in. 
2. In the browser, navigate to https://ai.azure.com/managementCenter/allResources, under All resources and select 'Create new'. Then choose the option to create a new Azure AI Foundry resource.
3. In the Create a project wizard, select 'Azure AI Foundry resource' and click next.Enter a valid name for your project or leave the default.
4. Expand Advanced options to specify the following for the project:
   
Subscription: Select the Azure subscription
Resource group: Select an existing resource group or select 'create new resouce group' and provide a name for the new resource group.
Azure AI Foundry resource: Provide a unique name or leave the default
Region: Select one of the following locations:
East US
France Central
Korea Central
West Europe
West US
Click 'create' and wait for the Foundry resource to be created.

**Follow the video walkthrough:**

https://github.com/user-attachments/assets/760bf30d-6444-448b-9294-0bb6fd86a91d

### 3. **Perform Key Phrase Extraction in Language playground**
1. Once the resource is created, you'll be taken to the resource overview  page.
2. In the left hand menu, select 'playgrounds', from all the options avaiable select 'Language playground'
3. At the top select 'Extract key phrases' tile.
4. Under configuration, select the API version, model version and the language of the text on which the key phrase analysis is perormed.
5. Copy or upload the sample customer review text file in the sample area and select 'Run'.
6. Once completed all the key phrases extrated from the text are shown in the 'Details' pane in the right.You'll see the most important phrases and topics extracted from each feedback entry.

**Follow the video walkthrough:**



https://github.com/user-attachments/assets/dcbe9ba7-4565-4aa6-9fec-d75faea2b556



### 4. **Perform Sentiment Analysis in Language playground**
1. In 'Language Playground', at the top of the page, select 'Analyze sentiment' tile.
2. Similar to previous task, under configuration select select the API version, model version and the language of the text.
3. In the sample are copy or upload the customer review text and select 'Run'.
4. Once completed the overall sentiment(Positive, Negative, Neutral) of the sample text is shown under 'Details' along with a confidence score. The sentiment (Positive, Negative, Neutral) and confidence scores for each piece of review  are also shown below that.

**Follow the video walkthrough:**



https://github.com/user-attachments/assets/4a4b74c4-0d9b-4fb3-92ab-8694a8ea88c3



  
## Sample Data (reviews_data.xlsx)

1. Amber and LaDonna at the Starbucks on Southwest Parkway are always so warm and welcoming. There is always a smile in their voice when they greet you at the drive-thru. And their customer service is always spot-on, they always get my order right and with a smile. I would actually give them more than 5 stars if they were available.
2. ** at the Starbucks by the fire station on 436 in Altamonte Springs, FL made my day and finally helped me figure out the way to make my drink so I'd love it. She took time out to talk to me for 2 minutes to make my experience better than what I'm used to. It was much appreciated! I've had bad experiences one after another at the Starbucks that's closest to me in my work building with my drinks not being great along with not great customer service from specific baristas. Niko was refreshing to speak to and pleasant. The drink was perfect! Store 11956
3. I just wanted to go out of my way to recognize a Starbucks employee Billy at the Franklin Park location! I was running late to work & placed an order at the wrong location and not only did he make my order with a smile he made it within 60 seconds! Thank you SOO much I was having a bad morning and people like you just make this world a better place.
4. Me and my friend were at Starbucks and my card didn't work. Thankful the worker there, paid for our drinks. And was very nice about it, it didn't seem to bother him that he paid for our drinks. This made my day, but made me look like a fool because my card didn't work. All thanks to Dillon. At Shoreline WA in Safeway. Thank you so much Dillon for the help, support and, kindness. I rate this 1000/10 if I could but, other than that, 10/10.
5. I'm on this kick of drinking 5 cups of warm water. I work for Instacart right now and every location of Starbucks I was given free hot water because I asked for it without being charged. I really appreciate Starbucks for giving me the opportunity to do such thing. That's why I give them five stars. They fully have my support. They're super nice and professional and the coffee is great. Go to Starbucks.
6. We had to correct them on our order 3 times. They never got it right then the manager came over to us and said we made her employee uncomfortable because we were trying to correct our order. The manager tried was racist against my stepmom (Chinese) taking over her but when I (**) would talk she would stop talking and listen to me.
7. I have tried Starbucks several different times in different locations just in case it was just the one store. But it's not. If you like coffee that taste like dirt scooped off the ground at a garbage dump, then this is the place for you.
8.	Starbucks near me just launched new fall foods and beverages yesterday. By noon yesterday they were out of all new items. The fall launch is huge and many people look forward to it all year. Maybe if you don't have enough product to last even a couple of days, push back the launch until you do? I was so happy to get the email that it had come out that I left work on my break to brighten my day and so very disappointed to get there at 12:30pm and find out that it was all gone. Please Starbucks, do better.
9. I ordered online for the Reisterstown Rd, St Thomas SC 99000 and they gave me the wrong drink size so ordered a venti they gave me a grande. Just a bit upset that I paid over 5 bucks for a drink and got the wrong thing.
10.	Staff at the Smythe St. Superstore location in Fredericton, NB often seen tired but today, a woman named Senoa (Senora?) was morose, glum, uncommunicative (even after I tried to engage her to sympathize, as there was obviously a bad mood happening), scruffy looking, almost rude. And, the Americano I ordered tastes watery. I go to Starbucks for a treat after a long day. It a difficult experience, to ease stress and have a pleasant experience. I'm going to sell a different location after today's grumpy girl.


## Conceptual Agentic AI Workflow

Moving forward, the passive analysis from Azure AI Languange can be trasformed to proactive and autonomous decision making system by integrating additional Azure tools that enables perception, reasoning, and action which are the core features of Agentic AI. 

While this demo doesn't involve writing code for a fully autonomous agent, the following conceptually demonstrates how we can evolve this into a more intelligent, agent-driven system.

1.	Perception: The agent 'perceives' new incoming customer feedback (simulated by pasting text into Language Studio).

This step can be automated such a way that Agent continuously 'listens' to feedback without manual intervention by using Azure services to automatically ingest real time or batch feedback.
- Azure Logic Apps or Power Automate: Pull feedback from email, CRM (ex Dynamics 365), or social media
- Azure Event Grid / Azure Service Bus: Handle asynchronous data streams.

2.	Reasoning /Analysing: The agaent uses Azure AI Language to analyze the sentiment and extract key phrases. Based on pre-defined (or conceptually learned) rules, it then reasons about the implications of this analysis.
Reasoning can be further enhanced to understand context and category of feedback in addtion to the sentiment with:
- Text Classification (Azure AI Language): Categorize feedback into buckets like “Login Issues”, “Billing”, “Suggestions”.
- Named Entity Recognition (NER): Identify specific brands, dates, or locations.

4.	Action Suggestion/Recommendation: Instead of providing raw data, the agent suggests an action or categorization for the feedback, prioritizing urgent issues.
The following Azure services can be used to automatically trigger autonomous business actions:
- Azure Logic Apps: Send high-priority feedback to engineering via Teams or Jira.
- Azure Functions: Automatically tag or route issues based on category or severity.
- Power Automate Flows: Create support tickets or email alerts based on agent decisions.

5.	Feedback Loop/Learn : In a real business scenario , human review of the suggestions would help the agent to continously improve its rules and action recommendations over time.
For example,a human review interface for oversight can be introduced with Azure Power Apps where:
- Agents propose an action.
- Humans approve, reject, or modify it.
- The feedback is logged and used to update rules or models (RLHF)

This following design illustrates how Azure AI Language for sentiment and key phrase extraction, combined with agentic principles, can transform unstructured customer feedback into actionable insights.

  
![Image](https://github.com/user-attachments/assets/41e93559-bb21-4750-b234-b6964e5a7f30)


## Dashboard: Conceptual Agent Output
| Feedback | Sentiment | Key Phrases | Suggested Action | Priority |
|----------|-----------|-------------|------------------|----------|
| "The new mobile app is fantastic!" | Positive | new mobile app, easy to navigate, fast | Share with Marketing | Low |
| "Customer support was slow..." | Negative | customer support, 30 minutes, unacceptable | Notify Support Lead | High |
| "Recent update broke login..." | Negative | update, login functionality, can't access | Escalate to Engineering | High |
| "Add a budgeting tool..." | Positive | budgeting tool, useful | Consider for Roadmap | Medium |


## Impact & Future Work
This project highlights how cloud AI services can be used to transform raw customer feedback into actionable insights. By utilising these techniques, a business can gain following bebefits.
- Faster identification of critical issues.
- Data-driven prioritization of features and bug fixes.
- Improved customer satisfaction and product quality.
- Operational Efficiency through automated review process
- No-code or low code implementation

**Future extensions to this project could include:**
- Integrating with a real-time feedback stream (e.g., from a CRM or social media).
- Building a dashboard to visualize sentiment trends over time.
- Developing a custom classification model within Azure AI Language to categorize feedback into specific product areas (e.g., "Login Issues," "Feature Requests," "Performance Bugs").
- Implementing a full agentic workflow using Azure Functions or Logic Apps to automate the action suggestions based on sentiment and key phrases.


## Concluding Remarks

Completing this project helped me solidify my understanding of Azure AI and gain hands-on experience with its practical applications.As a Product Manager with a background in Agile methodologies (PRINCE2 Agile Certified) and foundational cloud knowledge (AZ-900 Certified), I am currently focused on upskilling in Azure AI and exploring real-time AI use cases. I hope this project serves as a helpful resource for anyone looking to deepen their knowledge in this area.

By completing the above project , I've gained the following skills:
- Azure Cloud Resource Provisioning-: Ability to set up and manage Azure services.
- Natural Language Processing (NLP): Understanding of sentiment and key information extraction.
- No-Code AI: Demonstrating powerful AI capabilities without writing code.
- Problem-Solving: Applying AI to a real-world business challenge (customer feedback management).
- Agentic AI Principles (Conceptual): Illustrating how AI can move from analysis to suggesting actionable insights.

## About Me
I'm a **Product Manager** transitioning into the AI space. I hold:
- AZ-900 Certified (Azure Fundamentals)
- AI-900 Certified (Azure AI Fundamentals)
- PRINCE2 Agile Practitioner

Follow my journey in LinkedIn at https://www.linkedin.com/in/jinendra-dharmapala/ and check out more projects on this repo.


