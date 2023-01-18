# HR-chatbot-rasa
This repository is for rasa based chatbot answering generic HR related questions. Create new python environment and initialize rasa project as mentioned in readme.txt. Then replace the files with the ones available in this repository for generic HR chatbot..

To use rasa chatbot on Windows 10, follow below steps:

1. Install standalone python3 from Microsoft store. Currently, rasa supports the following Python versions: 3.7, 3.8, 3.9 and 3.10
2. Install Visual Studio, Visual Studio Code. Install python plugin in VS Code also.
3. Check Python installation in VS Code

    python3 --version
    pip3 --version

4. Make sure your pip version is up to date:

    pip3 install -U pip

5. Create a new virtual environment by choosing a Python interpreter and making a .\\venv directory to hold it:

    python3 -m venv ./venv

6. Activate the virtual environment:

    .\venv\Scripts\activate

7. Install Rasa Open Source:

    pip3 install rasa

8. Now, you can now create a new project with:

    rasa init

9. By the above command rasa will start automatically. If you want to start rasa chatbot, just enter below command:

    rasa shell

10. Press Ctrl+C to exit

11. Replace the data folder, domain.yml and credentials.yml with the one available in this repository for HR chatbot. You can update the existing files also as per your chatbot topic. 

12. Retrain the model after updating the nlu.yml, stories.yml and domain.yml

    rasa train

13. To deploy chatbot on telegram: Install ngrok, generate authentication token and start a tunnel. You can install ngrok plug in VS Code as well.
    Follow instructions available on https://ngrok.com/download
    Then write below code lines in credentials.yml with proper indentation.

    telegram:
      access_token: 5633780468:AAHX_byJWXYhgyQjtLLB0Jsrjz-tsl3rbCg
      verify: corona365_bot
      webhook_url: "https://9b9d-2401-4900-1f26-7c69-fd4a-4b80-dd23-a592.ngrok.io/webhooks/telegram/webhook"

    above mentioned access_token is generated from telegram. For this search for BotFather in telegram --> enter /start --> /newbot --> <bot_name> --> <username_bot> --> access token will be generated.
    write <username_bot> in verify section.
    write ngrok tunnel url in webhook_url section. Save the file.

14. run the below command in terminal for deploying on telegram:
    
    rasa run --enable-api --cors "*"

15. For more info, visit https://rasa.com/docs/rasa/installation/installing-rasa-open-source 