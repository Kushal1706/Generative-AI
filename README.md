# Generative-AI

Documenting the learning journey of the Generative AI.

What is Generative AI?
Generative AI is an artificial intelligence which can generate the text,image,video or vioces/musics from the prompts or any kind of user inputs.

**AI Models**
There are two type of models:

**1)GPT Models** -- Which are fast and also don't take time to generate.Gives instatnt output.

**2)Reasoning models** -- which are specially made for thinking capabilities,in which the model will think for some seconds and generate the output based on the prompt that are given.

All models work on the basis of the **Neural Network** which is basically the thinking brain of the models, On basis of these Neural Networks weights of information the models are been parameterized like 7b(billion).

**Key Aspects must be known before learning the Generative AI or Models of the AI**

**1)Tokens** -- The smallest unit of the text the model processes,like words or parts of words.

**2)Context** -- The surrounding text or information the model uses to understand and generate relevant responses.

**3)Context Window** -- The maximum number of tokens an LLM can read and use at the same time to generate or predict text. 
for example: GPT 3 : 2048 Tokens allowed
             GPT 4.1 : 10,47,576 Tokens allowed

**4)Inference** -- The process where an LLM takes input text and generates an output based on what it has learned.            

**Prompt Engineering**
Used to improve the capacity of LLMs on a wide range of common and complex tasks such as quesion answering and arithmetic reasoning.

**Prompt**
A prompt is simply the text you send to LLM.

**Elements of the prompt**
1)Instructions
2)Input Data
3)Context
4)Output Indicator

**Zero shot prompting**
Giving the single shot or direct question or prompt as the input 
ex:Write me an email regarding holiday.

**Few Shot Prompting**
Giving the prompt accordingly with the prompt elemnts and give the structure or idea how the output should be when it will get generated.

**Chain of thought prompting**
Chain-of-thought prompting is a technique in AI and natural language processing where a model is guided to produce intermediate reasoning steps explicitly before arriving at a final answer. This approach improves performance in complex reasoning, multi-step problem solving, and logical inference tasks by mimicking human-like stepwise thinking.

**Rules of Thumb and Examples for Prompt Engineering**

Note: the "{text input here}" is a placeholder for actual text/context

**1. Use the latest model**
   
For best results, we generally recommend using the latest, most capable models. Newer models tend to be easier to prompt engineer.

Note: There are some differences to consider when prompting a reasoning model versus prompting a GPT model. More details here.

2. Put instructions at the beginning of the prompt and use ### or """ to separate the instruction and context
   
Less effective ❌:

Summarize the text below as a bullet point list of the most important points.

{text input here}

Better ✅:

Summarize the text below as a bullet point list of the most important points.

Text: """
{text input here}
"""

3. Be specific, descriptive and as detailed as possible about the desired context, outcome, length, format, style, etc
   
Be specific about the context, outcome, length, format, style, etc

Less effective ❌:

Write a poem about OpenAI. 
Better ✅:

Write a short inspiring poem about OpenAI, focusing on the recent DALL-E product launch (DALL-E is a text to image ML model) in the style of a {famous poet}

4. Articulate the desired output format through examples
Less effective ❌:

Extract the entities mentioned in the text below. Extract the following 4 entity types: company names, people names, specific topics and themes.

Text: {text}
Show, and tell - the models respond better when shown specific format requirements. This also makes it easier to programmatically parse out multiple outputs reliably.

Better ✅:

Extract the important entities mentioned in the text below. First extract all company names, then extract all people names, then extract specific topics which fit the content and finally extract general overarching themes

Desired format:
Company names: <comma_separated_list_of_company_names>
People names: -||-
Specific topics: -||-
General themes: -||-

Text: {text}

5. Start with zero-shot, then few-shot, neither of them worked, then fine-tune
✅ Zero-shot

Extract keywords from the below text.

Text: {text}

Keywords:
✅ Few-shot - provide a couple of examples

Extract keywords from the corresponding texts below.

Text 1: Stripe provides APIs that web developers can use to integrate payment processing into their websites and mobile applications.
Keywords 1: Stripe, payment processing, APIs, web developers, websites, mobile applications
##
Text 2: OpenAI has trained cutting-edge language models that are very good at understanding and generating text. Our API provides access to these models and can be used to solve virtually any task that involves processing language.
Keywords 2: OpenAI, language models, text processing, API.
##
Text 3: {text}
Keywords 3:
✅Fine-tune: see fine-tune best practices here.

6. Reduce “fluffy” and imprecise descriptions
Less effective ❌:

The description for this product should be fairly short, a few sentences only, and not too much more.
Better ✅:

Use a 3 to 5 sentence paragraph to describe this product.

7. Instead of just saying what not to do, say what to do instead
   
Less effective ❌:

The following is a conversation between an Agent and a Customer. DO NOT ASK USERNAME OR PASSWORD. DO NOT REPEAT.

Customer: I can’t log in to my account.
Agent:
Better ✅:

The following is a conversation between an Agent and a Customer. The agent will attempt to diagnose the problem and suggest a solution, whilst refraining from asking any questions related to PII. Instead of asking for PII, such as username or password, refer the user to the help article www.samplewebsite.com/help/faq

Customer: I can’t log in to my account.
Agent:

8. Code Generation Specific - Use “leading words” to nudge the model toward a particular pattern
Less effective ❌:

 Write a simple python function that
 1. Ask me for a number in mile
 2. It converts miles to kilometers
In this code example below, adding “import” hints to the model that it should start writing in Python. (Similarly “SELECT” is a good hint for the start of a SQL statement.)

Better ✅:

 Write a simple python function that
 1. Ask me for a number in mile
 2. It converts miles to kilometers
 
import
->(Above prompt engineering steps referred from open ai website)
