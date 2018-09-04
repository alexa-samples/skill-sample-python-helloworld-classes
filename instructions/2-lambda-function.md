# Build An Alexa Hello World Skill
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

[![Voice User Interface](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/1-locked._TTH_.png)](./1-voice-user-interface.md)[![Lambda Function](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/2-on._TTH_.png)](./2-lambda-function.md)[![Connect VUI to Code](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/3-locked._TTH_.png)](./3-connect-vui-to-code.md)[![Testing](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/4-locked._TTH_.png)](./4-testing.md)[![Next Steps](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/5-locked._TTH_.png)](./5-next-steps.md)

## Setting Up A Lambda Function Using Amazon Web Services

In the [first step of this guide](./1-voice-user-interface.md), we built the Voice User Interface (VUI) for our Alexa skill.  On this page, we will be creating an AWS Lambda function using [Amazon Web Services](http://aws.amazon.com).  You can [read more about what a Lambda function is](http://aws.amazon.com/lambda), but for the purposes of this guide, what you need to know is that AWS Lambda is where our code lives.  When a user asks Alexa to use our skill, it is our AWS Lambda function that interprets the appropriate interaction, and provides the conversation back to the user.

1.  **Go to http://aws.amazon.com and sign in to the console.** If you don't already have an account, you will need to create one.  [If you don't have an AWS account, check out this quick walkthrough for setting it up](https://github.com/alexa/alexa-cookbook/tree/master/aws/set-up-aws.md).

    [![Developer Console](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/2-1-sign-in-to-the-console._TTH_.png)](https://console.aws.amazon.com/console/home)

2.  **Click "Services" at the top of the screen, and type "Lambda" in the search box.**  You can also find Lambda in the list of services.  It is in the "Compute" section.

    [![Lambda](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/2-2-services-lambda._TTH_.png)](https://console.aws.amazon.com/lambda/home)

3.  **Check your AWS region.** AWS Lambda only works with the Alexa Skills Kit in these regions: US East (N. Virginia), US West (Oregon), Asia Pacific (Tokyo)  and EU (Ireland).  Make sure you choose the region closest to your customers.

    ![Check Region](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/2-3-check-region._TTH_.png)

4.  **Click the orange "Create function" button.** It should be near the top of your screen.  (If you don't see this button, it is because you haven't created a Lambda function before.  Click the blue "Get Started" button near the center of your screen.)

    ![Create lambda function](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/2-4-create-a-lambda-function._TTH_.png)

5.  **Click on "Author from scratch".**  We will configure our Lambda function next.
    1. These values will only ever be visible to you, but make sure that you name your function something meaningful. "samplePythonQuiz" is sufficient if you don't have another idea for a name.

    2. From the "Runtime" dropdown select *Python 3.6*

    3. **Set up your Lambda function role.**  If you haven't done this before, we have a [detailed walkthrough for setting up your first role for Lambda](Lambda-Role.md).  If you have done this before, you only need to set an **Existing role**.

6.  **Configure your trigger.** There are many different AWS services that can trigger a Lambda function, but for the purposes of this guide, we need to select "Alexa Skills Kit." from the left hand side.

    Once you have selected Alexa Skills Kit, click the orange **Save** button on the top right corner.

7.  **Finish configuring your function**. Click on your function's name (you'll find it in the middle) and scroll to the bottom of the page, you'll see a Cloud9 code editor.

    We have provided the code for this skill on [GitHub](../lambda) folder. Follow these steps to get the code uploaded to lambda:
    1. Install the ASK Python SDK as per the details mentioned in the [getting-started](https://alexa-skills-kit-python-sdk.readthedocs.io/en/latest/GETTING_STARTED.html) documentation.
    2. Figure out the SDK installation folder. If you have followed the SDK [installation to a specific folder](https://alexa-skills-kit-python-sdk.readthedocs.io/en/latest/GETTING_STARTED.html#option-2-set-up-the-sdk-in-a-specific-folder), then it would be ``ask-sdk``. Else, if you have followed the SDK [Installation through Virtualenv](https://alexa-skills-kit-python-sdk.readthedocs.io/en/latest/GETTING_STARTED.html#option-1-set-up-the-sdk-in-a-virtual-environment), then it would be ``site-packages`` under ``skill/lib/Python3.6``.
    3. Copy the contents of the [lambda](../lambda) folder, to the place where the SDK has been installed. 
    4. Create the zip of the content of the SDK folder (not the folder itself).
    5. Change the **code entry type** dropdown to *Upload a .ZIP file*, select the Runtime appropriate to your system Python version.
    6. Upload the zip created previously.
    7. Change the handler name to ``hello_world.handler`` and click on **Save**.

13. You should see the Amazon Resource Name (ARN) a unique identifier for this function in the top right corner of the page. **Copy the ARN value for this Lambda function** for use in the next section of the guide.

    ![Copy ARN](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/2-12-copy-ARN._TTH_.png)
<!--TODO: THIS IMAGE NEEDS TO BE CUSTOMIZED FOR YOUR SKILL TEMPLATE. -->

[![Next](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/buttons/button_next_connect_vui_to_code._TTH_.png)](./3-connect-vui-to-code.md)
