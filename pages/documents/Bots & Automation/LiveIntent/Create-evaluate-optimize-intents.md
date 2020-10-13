---
pagename: Create Evaluate and Optimize Intents
categoryName: Bots & automation
subCategoryName: LivePerson Intent Analyzer
indicator: messaging
subtitle: Optimize your intent taxonomy using the Intent Discovery and Optimization tools
level3: ''
permalink: ai-bots-automation-liveperson-intent-analyzer-create-evaluate-and-optimize Intents.html
isTutorial: false
isNew: false

---

New Self Service Intent Discovery and Optimization features enable brands to tune their Intent taxonomy and deploy improved models within minutes. Brands can now easily mine their conversation data to discover and build new intents from one unified interface. They can also correct misclassified messages and feed those annotations back into their model as new training phrases to improve recognition quality.

## How to enable
Intent Discovery & Optimization is enabled by default for all Intent Analyzer customers. If you wish to disable, please contact your LivePerson account team.

## Step 1: Understanding your existing model
When you begin, first take a look at how the existing model is performing. There are a few key things to take note of: coverage, intent names, and the existing training data. 

1. First, to easily gauge the coverage of the current model, visit the Intent Analyzer Dashboard as seen below, and check the “top intents” pie chart:
![](img/IA-Optimize-1.png)

{: .notice}
Look for how much of the pie chart undefined occupies. If it is very low, i.e. ¼ or less of the pie chart, it is unlikely that there will be many intents to discover. Take this into consideration as you proceed. 

2. Go to Intent Builder and check the intent names, and their training data. It is important to read over each message of training data that corresponds to each intent, and verify whether the message fits the name of the intent. If a message is not a clear match to its corresponding intent, remove it from the training data.

3. Once you’ve finished looking over the existing model’s coverage, intent names, and intent training data, you should have a good understanding of the intents that already exist in your model. This is important to keep in mind going forward, as you do not want your future work to overlap with any of the existing intents.

## Step 2: Intent Discovery 
Intent discovery is the task of finding new intents to add to your current taxonomy. This is useful to expand your model’s coverage. Make sure to consider any existing intents (i.e. a starter pack) as you start this process, since you do not want to create an intent that will overlap with one of the existing intents in name or function. 

{: .notice}
Please do not create an intent for COVID-19. COVID-19 is a reason for many consumer intents, but is not an intent in and of itself. If you want to see messages that are related to COVID-19, consider using a keyword search for terms like “coronavirus”, “covid”, “virus”, etc. in Intent Analyzer. This can be helpful in identifying which intents are being impacted the most by COVID-19.

Below is a visual guide for anyone starting the intent discovery process:

* Start by trying to find a pattern or theme in the messages by going to the Intent Analyzer dashboard and filtering by undefined. First click the “Add Filter” button on the top right of Conversation Details in Intent Analyzer.

![](img/IA-Optimize-2.png)

* Next, in the pop up window select “Intents” as your filter type on the left, and “undefined” from the dropdown on the right.
![](img/IA-Optimize-3.png)
Try to look over at least 30 messages. 

* In these messages you may notice a few recurring patterns such as consumers reporting issues logging into their account. Let’s group those similar messages together to make an intent.

* After identifying a few patterns, see if you can group similar messages under a named label that you create. In the above example case, we can take the 3 checked utterances and make an intent named “report login problem”. To name an intent, try to think of a short phrase that could be used to describe the intent. Typically, an intent name has both a verb and a noun.

## Step 3: Finding More Messages
Now that we have discovered and named a few intents, let’s use our full list of intents to classify some consumer messages. These messages will be used as training data to create a model for the intents you’ve discovered. Make sure to determine a few rules for which messages should and should not be classified by each intent, and write them down. These rules are what we call intent “definitions” and will help you stay consistent as you classify messages. Make sure that the definitions of each intent do not overlap each other. Here are a few tips for picking training utterances:

Use real customer utterances for training utterances. Do NOT write your own messages that you think might be similar to a customer message.

Use complete utterances rather than phrases or parts of messages, as customers usually communicate in full messages and you want to match the way they state their intent.

Work on all of your intents simultaneously, including the existing starter pack intents. This way you classify more utterances, more efficiently, without having to go back.  It also helps the model to differentiate between intents, and you can better understand the differences if you read utterances with multiple intents in mind.

There are a few methods that you can use to find more messages:

First, you can read the unfiltered messages directly from the Conversation Details [dashboard](https://knowledge.liveperson.com/ai-bots-automation-liveperson-intent-analyzer-dashboard.html) in Intent Analyzer.
![](img/IA-Optimize-4.png)

Another method is to use a keyword search to filter your results, as seen below:
![](img/IA-Optimize-5.png)

Lastly, you can use the Intent Discovery feature to find messages that are similar to a message that you select. To start, highlight a message with your mouse and click “discover similar messages” as seen below:
![](img/IA-Optimize-6.png)

After clicking “discover similar messages”, Intent Analyzer will load a new set of messages into the “Messages with Intent” window, all of which are similar to the message that you picked at the beginning:
![](img/IA-Optimize-7.png)

Regardless of which option you choose to find more messages, once you’ve found them, use the dropdowns on the right to classify them, or you can select multiple messages with the checkboxes on the left and reclassify them as a group.
![](img/IA-Optimize-8.png)

{: .notice}
You can also export the utterances using the “Export Table to CSV” as a spreadsheet to Excel or Google Sheets.

![](img/IA-Optimize-9.png)
Once the data has been exported and downloaded onto your local device, you can upload the file into Google Sheets or Excel and begin classifying messages.

## How To Select Training Utterances 

### Optimal number of utterances
For optimal performance, we recommend 60 to 100 training samples per class, but not more than 150 samples due to the potential issue of model overfitting

{: .notice}
Currently, you can only pull a maximum of 500 messages at a time. If you classify 5 messages as an intent out of that set, you will need to pull 5x more data to get enough training utterances for that intent. 

### Utterance diversity
Avoid duplicate keywords or duplicating the same pattern across your data. LP-NLU models take a variety of things into account in predicting labels; trying to guess what those would be will lead to poor results. A better approach is to include diverse utterances created by actual customers.

**Diverse utterances that have a variety of words and structures:**
  * Are there two different passwords for admin and logging in
  * I keep trying to reset my password but it says it needs to confirm my email with an email
  * I have forgotten my 5 digit password
  * Trying to retrieve my username and password

**These utterances are very similar and NOT diverse:**
* Reset my password 
* Please reset my password
* Can you reset my password

## How to Split an Intent

Sometimes an intent is too broad and all encompassing. This can cause an intent to be less actionable and have poor accuracy. A simple way to fix this issue is to split the broad intent into smaller intents. An example of this is splitting the intent ask about credit limit from the Financial Services industry into 3 smaller intents: increase credit limit, decrease credit limit, and request credit limit information. The most important thing to remember is that the new, smaller intents should cover the same conversational space as the original broader intent. Do not give definitions to the new, smaller intents that go beyond the scope of the original broad intent’s definition. To split an intent into smaller intents, first delete the original, broad intent in Intent Builder. Then, gather the messages for the smaller intents just as you typically would for a new intent, and train a new model.

## What are Meta-Intents?
You may notice as you are working on your taxonomy that the number of intents can become difficult to manage if the taxonomy grows too large. In this case, we recommend using meta-intents to help group and sort your intents. Please note that all starter packs come with meta-intents. A meta-intent is a wrapper that can contain many other standard intents. This functionality provides a way to funnel a variety of intents into a single category. When a consumer message matches one of the contained intents, both the standard intent and the meta intent are matched. Please see this link for how to add meta-intents.

## Step 4: Training your new model
Now that you have discovered some intents and found the training data for those intents, you’re ready to train your model. Any time you’ve worked on a model in Intent Analyzer, whether finding training data or adding new intents, make sure to train a new model once you are finished for the day. You should train a new model at the end of every session of work on Intent Analyzer or Intent Builder. This will allow you to see the results of your changes the next time you revisit the model. To train a new model, follow these steps:

1. Open the domain.
2. Click Train in the upper-right corner to start the training.
3. To refresh the page and check on progress, click the Refresh icon in the Training Status column.

![](img/IA-Optimize-10.png)

## Step 5: Evaluating & optimizing your model

After creating your intents and adding training utterances on Intent Builder, confirm that the model is classifying incoming messages correctly. This is a summary of a process to evaluate and optimize your model. This can be performed by CSMs, ETS, or sales personnel and only requires access to the Intent Manager dashboard. Depending on your taxonomy size this process may take about thirty minutes to an hour.

### Check Intents: 
* First navigate to the Intent Analyzer [dashboard](https://knowledge.liveperson.com/ai-bots-automation-liveperson-intent-analyzer-dashboard.html)
![](img/IA-Optimize-11.png)

* In the Intent Analyzer dashboard navigate to “Conversation Details” at the top left.
* click “+ Add Filter” at the top left.
* You should now see the “add filter” menu from the image below.

![](img/IA-Optimize-12.png)

* Now, use the first dropdown menu to select “intents” as your category.

![](IA-Optimize-13.png)

* Then use the second dropdown menu to select which intent you want to filter on.

![](IA-Optimize-14.png)

Once you have an intent filter created, read around 10+ messages in the “Messages with Intent” window and verify that these messages match the current intent you are using as your filter. As you do this please refer to the intent’s definition for guidance (see links to definitions at the end of this document). Make sure to do this for every intent in your taxonomy, and track how many messages are correctly labeled per each intent. If you observe less than 60% correctly labeled messages, please see the “Diagnosis” step below for next steps. For a more accurate assessment of your model, read over a larger number of messages per intent (20+ would be ideal).

![](IA-Optimize-15.png)

In the above example 6 messages were correctly labeled as “report general login issues”, while 2 messages were incorrectly labeled as “report general login issues”. This gives you  6/8 correct, simplified to 3/4 or 75% correct.

**Check Undefined:**
Now, use the “+ Add Filter” button to change the filtering intent to “undefined” which is at the very bottom of the list of intents.

Once you have done this you will need to return to the “Messages with Intent” window as you did in Step 1, and read 50+ of the filtered messages. While doing this make sure to record how many messages are correctly classified as “undefined”. “Undefined” is a label that is applied to messages that cannot be classified by any intent in a given taxonomy. Once you are done, calculate the percentage of correctly classified “undefined” messages.  If you observe less than 60% correctly labeled messages, please see the “Evaluation” step below for next steps.  Reading over a larger number (100+) of “undefined” labeled messages is advised for an accurate assessment, but a minimum of 50 should be sufficient.

### Evaluation:

| Check Intents | Check Undefined | Evaluation |
|---------------|-----------------|------------|
| GOOD (greater than 60% avg correct) | GOOD (greater than 60% correct) | Looks good!| 
| BAD (less than 60% avg correct) | GOOD (greater than 60% correct)| You may have contradictorily labeled messages in your model’s training data and/or not enough training data. Revisit your intent definitions to check for overlap, and/or add additional training data to your intents.|
| GOOD (greater than 60% avg correct) | BAD (less than 60% correct) | Your intents lack variation in the training data. Your model needs a larger variety of messages added for each intent.|
| BAD (less than 60% avg correct) | BAD (less than 60% correct) | Overall performance is poor. Consult the taxonomy team, and consider revising your intents, their definitions, and their training data.|
