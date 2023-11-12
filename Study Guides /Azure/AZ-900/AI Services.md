# Identify Product Options

Definition of Artificial Intelligence (AI):

- Broad classification of computing.
- Allows a software system to perceive its environment and take actions to achieve goals.
- Goal: Create a system that can adapt or learn on its own without explicit programming.

Approaches to AI:

- Deep Learning: Modeled on the neural network of the human mind, enabling learning through experience.
- Machine Learning: Uses existing data to train models, test them, and apply them to new data for forecasting.

Machine Learning Applications:

- Powers product recommendation systems in online shopping.
- Used for fraud detection in credit-card transactions.

Microsoft's Primary Product Offerings:

- Azure Machine Learning: Platform for making predictions, with tools and services for data connection, model training, testing, and deployment.
  - Build > Deliver > Train > Evaluate > Create > Deploy
  - Needs complete control over the design and training of an algorithm using your own data.
- Azure Cognitive Services: Provides pre-built machine learning models for various applications like language processing, speech conversion, vision analysis, and decision-making.
- Azure Bot Service and Bot Framework: Platforms for creating virtual agents that can intelligently communicate with humans.

Azure Machine Learning:

- Offers tools and services for designing, training, testing, and deploying predictive models.
- Provides control over the design and training of algorithms using your own data.

Azure Cognitive Services:

- Pre-built machine learning models for various applications.
- Categories include language services, speech services, vision services, and decision services.
  - Language services: language services, allow your apps to process natural language with pre-built scripts, evaluate sentiment, and learn how to recognize what users want.
  - Speech services: converts speech into text and text into natural sounding speech.
  - Vision services: add recognition and identification capabilities when you're analyzing pictures, videos, and other visual content.
  - Decision servivces: Provide personalized recommendations that get better with use. Also, ensure content moderation to remove offensive or risky material and identify anomalies in your time series data.
- Accessible via APIs, no special machine learning or data science knowledge required.

Azure Bot Service and Bot Framework:

- Platforms for creating virtual agents.
- Use cases include automating simple repetitive tasks and intelligent communication with humans.
- Utilizes other Azure services, such as Azure Cognitive Services.

Use Cases for Bots:

- Shifts simple, repetitive tasks to automated systems.
- Can handle tasks like taking dinner reservations or gathering profile information.

User Interaction with Bots:

- Interaction through text, interactive cards, and speech.
- Can range from quick Q&A to sophisticated conversations.

Overall:

- Microsoft offers a range of AI-related services catering to different needs and audiences.
- These services empower developers to integrate AI capabilities into their applications with varying levels of complexity and customization.

<h2></h2>

# Analyze the decision criteria

Criteria for Choosing an AI Service:

- Analyzing criteria used by experts in selecting AI services for specific business needs.
- Understanding these criteria helps distinguish nuances among products.

Virtual Agent Criteria:

- Consideration: Is the virtual agent intended to interface with humans via natural language?
- Use Azure Bot Service for building virtual agents with natural language interfaces.
- Bot Service integrates knowledge services, natural language processing, and form factors for diverse channel interactions.

Bot Service Solutions:

- Reliance on other AI services, such as natural language understanding and translation.
- Prebuilt, no-code solutions like QnA Maker available for common scenarios.
- Power Virtual Agents integration with Microsoft Power Platform, providing prebuilt connectors for data input.

Power Virtual Agents:

- Utilizes prebuilt connectors for data input.
- Integration with Microsoft Power Platform for building apps and workflows.
- Extensibility through custom workflows with Power Automate.
- Complex interactions can be built with Microsoft Bot Framework.

Content and Meaning Understanding:

- Consideration: Does the service need to understand content and meaning in images, video, audio, or translate text?
- If yes, use Azure Cognitive Services for general-purpose tasks like speech-to-text, search integration, and object identification in images.

Azure Cognitive Services Personalizer:

- Useful for predicting user behavior and providing personalized recommendations in applications.
- Watches user actions to identify usage patterns and predict behavior.

Azure Machine Learning:

- If the app needs to predict future outcomes based on private historical data, use Azure Machine Learning.
- Suitable for analyzing proprietary data, such as years of financial transactions, to discover patterns for new products and services.
- Custom-tailored machine learning models for working with proprietary data.
- Provides maximum flexibility for data scientists and AI engineers using familiar tools on provided data.

Flexibility with Azure Machine Learning:

- Allows data scientists and AI engineers to use familiar tools on provided data for developing deep learning and machine learning models tailored to specific requirements.
