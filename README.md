# RASA_masterclass

# RASA_ChatBot

# Command	                    Effect
#### rasa init	        ->      Creates a new project with example training data, actions, and config files.
#### rasa train	        ->      Trains a model using your NLU data and stories, saves trained model in ./models.
#### rasa interactive	  ->      Starts an interactive learning session to create new training data by chatting to your assistant.
#### rasa shell	        ->      Loads your trained model and lets you talk to your assistant on the command line.
#### rasa run	          ->      Starts a server with your trained model.
#### rasa run actions	  ->      Starts an action server using the Rasa SDK.
#### rasa visualize	    ->      Generates a visual representation of your stories.
#### rasa test	        ->      Tests a trained Rasa model on any files starting with test_.
#### rasa data split nlu->      Performs a 80/20 split of your NLU training data.
#### rasa data convert	->      Converts training data between different formats.
#### rasa data validate	->      Checks the domain, NLU and conversation data for inconsistencies.
#### rasa export	      ->      Exports conversations from a tracker store to an event broker.
#### rasa x	            ->      Launches Rasa X in local mode.
#### rasa -h	          ->      Shows all available commands.
#### rasa train --fixed-model-name -> If you want to name your model differently, you can specify the name using the --fixed-model-name<br><br>
#### rasa train --finetune -> To initialize the pipeline with an already trained model and further finutne it to the new training dataset that includes the additional training examples.
#### rasa train --finetune <path to model to finetune /> -> By default, the command picks up the latest model in the models/ directory. If you have a specific model which you want to improve, you may specify the path to this by running<br>
  
#### Finetuning a model usually requires fewer epochs to train machine learning components like “DIETClassifier”, “ResponseSelector” and “TEDPolicy”  
#### You can also finetune an NLU-only or dialogue management-only model by using rasa train nlu --finetune and rasa train core --finetune respectively.
#### If you start the shell with an NLU-only model, rasa shell will output the intents and entities predicted for any message you enter.  
#### rasa shell nlu -> If you have trained a combined Rasa model but only want to see what your model extracts as intents and entities from text.
#### rasa run -> To start a server running your trained model, run:
####rasa run --model models/ -> If you want to load the latest model in a directory, you can specify a directory instead of a file:<br><br><br>
#### -> You can configure the HTTP server to fetch models from another URL by adding it to your endpoints.yml:

endpoints.yml
models:
  url: http://my-server.com/models/default
  wait_time_between_pulls: 10 
  
  
#### rasa test ->   This will test your latest trained model on any end-to-end stories you have defined in files with the test_ prefix. If you want to use a different model, you can specify it using the --model flag.
  
## rasa data split#
To create a train-test split of your NLU training data, run:

#### rasa data split nlu -> This will create a 80/20 split of train/test data by default.
  
#### rasa data convert nlu#
  
  
## You can convert NLU data from

LUIS data format,
WIT data format,
Dialogflow data format,
JSON, or
Markdown
to

YAML or
JSON or
Markdown.
You can start the converter by running:

#### rasa data convert nlu

## Best Practice

### CCD -> Conversation-Driven Development
The principle behind CDD is that in every conversation users are telling you—in their own words—exactly what they want. By practicing CDD at every stage of bot development, you orient your assistant towards real user language and behavio

#### CCD includes following actiosn
Share your assistant with users as soon as possible<br>
Review conversations on a regular basis<br>
Annotate messages and use them as NLU training data<br>
Test that your assistant always behaves as you expect<br>
Track when your assistant fails and measure its performance over time<br>
Fix how your assistant handles unsuccessful conversations
