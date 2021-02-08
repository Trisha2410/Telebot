# Telebot :Project second semester
Chat-bots can be useful in many aspects of the customer experience, including providing customer service, presenting product recommendations and engaging customers through targeted marketing campaigns. 
According to Forbes, the chat-bot market is forecasted to reach $1.25 billion by 2025.

Chat-bots work by analyzing and identifying the intent of the user and give an appropriate response. The chat-bots work by adopting three classification methods.
- Pattern matching: Matches the pattern to group the text and it produces an appropriate response from the clients.
- Natural language understanding (NLU): Converts the text into structured data for a machine to understand.  It follows three specific concepts : entities, context, and expectations.
- Natural language processing (NLP): Natural Language Processing bots are designed to convert the text or speech inputs of the user into structured data. The data is further used to choose a relevant answer.

There are two types of chat-bots.
1. Retrieval based Chat-bots : A retrieval-based chatbot uses predefined input patterns and responses to select the appropriate response. We can customize the tone and flow of the chatbot to drive our customers with the best experience.

2. Generative based Chatbots: Generative models are not based on some predefined responses. They are based on sequence to sequence neural 	networks. Here we are going to transform input into an output. It needs a large amount of data and it is based on Deep Neural networks.

In this project, we have built a chatbot using deep learning techniques. It is a  retrieval based chatbot using NLTK, Keras, Python, etc.
Files/resources of our project:

- intents.json		  : 	The data file which has predefined patterns and responses.
- chatbot_model.py 	: 	In this Python file, we wrote a script to build the model and train our chatbot.
- words.pkl 		    : 	This is a pickle file in which we store the words Python object	that contains a list of our vocabulary.
- classes.pkl 		  :	  The classes pickle file contains the list of categories.
- chatbot_model.h5	: 	This is the trained model that contains information about the model and has weights of the neurons.
- Telebot.py		    : 	This is the Python script in which we implemented GUI For our chatbot. Users can easily interact with the bot.
- Telebot.db		    :	  The Database, containing the Tariff details.
- database_code.py	: 	This is a python script which will create all the required tables	For the project.

 Functions defined in Telebot.py                  :       Functionality of the Functions
  - def clean_up_sentence(sentence)               :   Takes customer’s input, find the root word and return a list of words “sentence_words”.
  - def bow(sentence, words, show_details=True)   :   Takes customer’s input, calls the “clean_up_sentence(sentence)” and uses the “sentence_words” compare it with the list of words 
                                                      from intens.json and returns a numpy array of 0’s and 1’s (1 represent match).
  - def predict_class(sentence, model)            :   Load the model calls the “def bow(sentence, words, show_details=True)”  passes the  “numpy array ” to the model  and fetch the 
                                                      most probable “tag” along with its probability and returns a list of tag with its probability
  - def chatbot_response(msg)                     :   Takes customer input, calls the “def predict_class(sentence, model)” and then based on the conditions calls the DB functions 
                                                      for insertion and selection of data from the db and finally  calls the “def getResponse(ints, intents_json)” to  get the  
                                                      response and sends it to the “def send(*args)” to  display on the Chat-log
  - def getResponse(ints, intents_json)           :   Based of the tag identified by the “def predict_class(sentence, model)”  selects a random response  and pass it to the “def                       
                                                      chatbot_response(msg)” function
  - def clear_label_image()                       :   Small function to remove the image displayed in the Chat-log window initially
  - def send(*args)                               :   Called whenever customer, presses “Enter key” or clicks the Send Button
  - def clock()                                   :   To display the digital clock.
  - def date()                                    :   To display the current date.
  - def db_insertdata(msg)                        :   Establishes db connection and insert the data_limit  which is  a numerical value in the in the table “data_limit”
  - def db_insertplantype(plan)                   :   Establishes db connection and insert the plan_type which is either prepaid or postpaid in the table “plan_type"
  - def fetchresult()                             :   Establishes db connection and retrieves the traffis based on the values of – plan_type, budget and data_limit.
  - def db_insertbudget(msg)                      :   Establishes db connection and insert the budget which is  a numerical value in the table “budget”

Please refer the Screenshot folder.
