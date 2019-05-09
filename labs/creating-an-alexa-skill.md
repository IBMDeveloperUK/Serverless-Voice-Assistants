# Creating an Amazon Alexa Skill

### Background

[Alexa](https://developer.amazon.com/alexa) is Amazon's cloud-based voice service. Most people are familiar with the service through using an [Amazon Echo or Echo dot](https://developer.amazon.com/alexa/echo) but the service can also be integrated in to custom internet-connected devices like this talking robotic fish:

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/bRxhgxH6FUI/0.jpg)](https://www.youtube.com/watch?v=bRxhgxH6FUI)

When building a skill for Alexa there are two components - the **skill interface** and the **skill service**.

The **skill interface** processes the speech that comes in from a device. It uses [natural language processing](https://en.wikipedia.org/wiki/Natural_language_processing) to determine the intent of the user and then passes this as a JSON object to the skill service. It also passes JSON responses back in to voice to the user or device.

The **skill service** is the part that actually executes the functionality of your skill. It accepts the JSON from the skill interface, does some stuff, then returns a JSON object back to the skill interface where it can be converted to speech. For our example we are using IBM Functions as our skill service and the Amazon dev platform as our skill interface.

### Creating the skill

#### Getting set up

Before we can create a new Alexa skill we need to create an Amazon developer account:

1. Sign up for an Amazon Developer Account [here](https://developer.amazon.com/).

2. Go to https://developer.amazon.com/alexa/console/ask and click the `Create Skill` button

![create skill](img/create_alexa_skill.png)

3. Put in the name `Business Strategy Generator` and choose **custom** as the model then hit the `create skill` button.

![custom skill](img/select_custom_skill.png)

4. Select **start from scratch** and click the `choose` button.

![start from scratch](img/select_startfromscratch_template.png)

#### Configuring the skill

The skill **invocation name** is what a user will say to an Alexa device to trigger our skill. To make this as realistic as possible, lets change ours to "senior management", so that our skill will be invoked by the phrase "Alexa, ask senior management..."

1. Click on `Invocation` on the left navigation and change the Skill Invocation Name to `senior management` and click `Save Model` (in the top left corner).

![invocation name](img/invocation_name_v1.png)

When you start to build more complex Alexa skills, you need to define the *intents* that your user can utter. An *intent* is essentially a general action a user can perform e.g. "what is the forecast?" or "get my balance!". Since our skill doesn't handle multiple actions we'll just create one intent that will handle all requests.

2. On the left side-bar click on `Intents` and click `+ Add`:

![intents](img/intents.png)

3. Use the name `EveryThingIntent` and hit the `Create custom intent` button.

4. Enter the text `{EveryThingSlot}` in to the text field under "Sample Utterances (0)" and click the plus sign to create the slot:

![sample utterance](img/sample_utterance.png)

5. Scroll down to where it says `Intent Slots` and use the `Select a slot type` dropdown to select the value **BAG_OF_WORDS** for the EveryThingSlot:

![create intent](img/create_everything_intent.png)

6. Click on `Save Model` and then `Build Model` in the top left corner of the console:

![save and build model](img/save_and_build.png)

#### Y

🎉🎉🎉 **Good job, your functionality is all ready to go. Now lets move on to integrating this with some voice assistants.** 🎉🎉🎉

### Next Lab:
[Creating an Amazon Alexa Skill](/labs/creating-an-alexa-skill.md)