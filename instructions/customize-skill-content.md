# Build An Alexa Hello World Skill
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

This skill gets you started with skill building by providing basic "Hello World" functionality that allows you to rapidly generate a voice response from Alexa.

## Customize the Skill to be Yours

At this point, you should have a working copy of our Hello World skill. Go ahead and make it your own by doing some customizations.

1. **New sentences to respond to your users.** You can change the few responses this basic skill has to get a better feel of how ASK works.

    1. Navigate to the **Code** tab, and expand the project folder on the left to `Skill Code/alexa`

    2. Open **[lambda_function.py](../lambda/py/lambda_function.py)**

    3. This file contains all of the strings for the `en-US` locale. Let's go ahead and change the response Alexa says when we open the skill. This is going to be line `3-4` in the file.

    Here is the block of code we are going to be changing:
    ```py
    ...
    ...,
    WELCOME_MESSAGE = _(
        "Welcome, you can say Hello or Help. Which would you like to try?")
    ...,
    ...,
    ```

    Let's go ahead and change our `WELCOME_MESSAGE` to "Welcome to Hello World Skill! Go ahead and say Hello or Help". Now, lines `3-4` should look like the following:
    ```py
    ...
    ...,
    WELCOME_MESSAGE = _(
        "Welcome to Hello World Skill! Go ahead and say Hello or Help"
    )
    ```

    Now, press **Save**, and **Deploy**, and navigate back to the **Testing** tab. When you reopen your skill, Alexa should say your new message instead!


Normally, you would consider submitting your skill for certification. But, a default "hello world" skill is too simple to provide a valuable end user experience.
Consider starting another skill project, using one of the several other templates we've in the store for you.

