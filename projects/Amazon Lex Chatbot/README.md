<h1>INTERACTIVE CHATBOT USING AWS LEX</h1>
<h2>Project Overview:</h2>
<ol>Understand the basics of AWS Lex chatbot creation</ol>
<ol>Create a functional chatbot with one intent and related utterances</ol>
<ol>Demonstrate knowledge of Amazon Lex’s user interaction flow.</ol>
<h2>Learning Outcomes:</h2>
<ol>1. Chatbot development</ol>
<ol>2. Problem solving</ol>
<ol>3. Technical knowledge</ol>
<ol>4. Communication and presentation</ol>
<h1>Professional summary</h1>
<p>This project demonstrates a conversational chatbot using Amazon Lex, a service by Amazon Web Services that enables the creation of intelligent, voice-and taxt-based interfaces. The chatbot is designed to understand user intents, process natural language input, and provide automated responses based on predefined logic.</p>
<p>Key features of this project include intent creation, and slot configuration for capturing user input. The bot is tested and deployed using AWS tools, showcasing how conversational AI can be applied to real-world scenarios such as customer support and task automation.</p>
<p>This project highlights practical experience in building serverless applications, working with natural language processing, and designing user-friendly conversational flows in a cloud environment.</p>
<p>Attached below is the project presentation.</p>

[Project 3 Interactive Chatbot Using Amazon Lex 2.pptx](https://github.com/user-attachments/files/26166380/Project.3.Interactive.Chatbot.Using.Amazon.Lex.2.pptx)

<h1>DEPLOYMENT STEPS</h1>
<h2>STEP 1: Creating the chatbot</h2>
<p>To create the chatbot, I go to the aws management console, search for amazon lex, select it the click "create bot"....The chatbot's name is Stem</p>
<p><ol>Bot name: StemBot</ol>
<ol>Creation method: Create a blank bot</ol>
<ol>IAM permissions: Create a new role with basic amazon lex permissions</ol>
<ol>Idle seiion timeout: 5 minutes</ol>
<ol>Language: English</ol>
<ol>Voice: Choose any (optional)</ol>
<ol>Then I click "Create"...below this the picture of the created chatbot</ol></p>
<img width="1305" height="247" alt="Screenshot 2026-03-22 163408" src="https://github.com/user-attachments/assets/9b38b970-979a-4630-88c9-2d28ffb92b7b" />

<h2>STEP 2: Creating a welcome Intent</h2>
<p>An intent represents an action a user wants to perform when they interact with the chatbot. You define intents in amazon lex to recognize user goals, trigger appropriate responses or actions, and collect necessary data</p>
<p>I click "Add intent" then "create intent"</p>

<img width="760" height="429" alt="Screenshot 2026-03-22 165657" src="https://github.com/user-attachments/assets/0ac15ff5-0179-48eb-b176-7e8e9cea6eb2" />

<h3>Adding utterances</h3>
<p>An utterance is a phrase or sentence a user might say to express an intent. Utterances help lex to understand how users express their intent in natural language.</p>
<p>I have provided multiple examples to train lex to recognize variations and match them to the right intent</p>

<img width="804" height="530" alt="Screenshot 2026-03-22 170301" src="https://github.com/user-attachments/assets/d8fc8444-992b-47dd-9999-3e05e20cc4cb" />

<h3>Adding a closing response</h3>
<p>A closing response is the message sent to the user when an intent is fulfilled</p>

<img width="833" height="516" alt="image" src="https://github.com/user-attachments/assets/e3e066a5-0698-4551-9056-f6d66ee40c91" />

<h3>StemBot product after creating the welcome intent</h3>

<img width="333" height="492" alt="image" src="https://github.com/user-attachments/assets/6e25e1a9-65eb-44d9-b708-c9faf218acdc" />

<h2>STEP 3: Adding a fallback intent</h2>
<p>A fallback intent is a catch-all for when the chatbot doesn't understand the user's input or it doesn't match and defined intents.</p>

<img width="1124" height="449" alt="image" src="https://github.com/user-attachments/assets/4b8e9b99-8ef0-46c0-b462-f9442387c624" />

<h3>StemBot product after creating the fallback intent</h3>

<img width="351" height="496" alt="image" src="https://github.com/user-attachments/assets/80cdfb1b-f490-4d78-82a3-f7c1200074b0" />

<h2>STEP 4: Creating the S3Info intent</h2>
<p>The s3info intent gives the user information about amazon s3</p>
<h3>Adding utterances</h3>

<img width="805" height="488" alt="image" src="https://github.com/user-attachments/assets/5c1d2752-8362-4348-958f-e54f589b1875" />

<h3>Adding a closing response</h3>

<img width="797" height="423" alt="image" src="https://github.com/user-attachments/assets/38b0953c-00ef-49d9-8371-dec82785e08f" />

<h3>Final product of stembot after adding a s3info intent</h3>

<img width="343" height="503" alt="image" src="https://github.com/user-attachments/assets/d377eed8-60bc-4d02-9a73-fd428719f6a3" />

<img width="345" height="493" alt="image" src="https://github.com/user-attachments/assets/52b2b6e2-5799-4e20-894c-d3884a075dc9" />

<h2>STEP 5: Creating a S3Quiz intent</h2>
<p>The s3quiz intent handles the questions or interactions related o amazon s3</p>

<h3>Adding utterances</h3>

<img width="777" height="484" alt="image" src="https://github.com/user-attachments/assets/e274c80c-0349-4572-a444-a7cd158873b7" />

<h2>The quiz</h2>
<p>Stem bot gives feedback on correct answers</p>

<img width="350" height="516" alt="Screenshot 2026-04-04 211104" src="https://github.com/user-attachments/assets/7c5d10f2-e7e9-4c3f-907c-70b6aa50eddf" />

<p>Stem bot gives feedback on incorrect responses</p>

<img width="351" height="508" alt="Screenshot 2026-04-04 211227" src="https://github.com/user-attachments/assets/f3c39dad-a1e2-4a20-87d1-b12638fef3f3" />

<p>Stem bot lets the user know that the quiz is complete</p>

<img width="350" height="525" alt="Screenshot 2026-04-04 211416" src="https://github.com/user-attachments/assets/acf90be0-9b35-47f5-a908-2270ce7baf4b" />





























