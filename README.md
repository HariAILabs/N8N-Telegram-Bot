# N8N-Telegram-Bot
This is a workflow which I made using simple n8n nodes. This is the second agent I built using n8n. Hoping to make something innovative in the future 😊.

<img width="1924" height="947" alt="screely-1758951552618" src="https://github.com/user-attachments/assets/a968b6a6-15c0-4ca3-bf0d-e5d4c53ca1b0" />

Pre-requisites:
1. Open Telegram (either in your PC or in your Mobile)
2. Go to "BotFather" account and Start the Chat.
3. Create a new bot with the command ("/newbot")
4. Now it asks you to set a name for your bot.
5. For the Username, it requires you to set something which ends with the word "bot" so keep that in mind.
6. After that, It gives you the URL for your new telegram bot with the Access Token which is very crucial to connect your bot with N8N.
7. Congratulations, you created your first bot!!! 🎉🎉🎉🎉 

## How it works?
This is a workflow which has only 8 nodes, so it's simple and basic (only for someone who is a pro in n8n workflows 😅). Here's how it works:
1. The workflow starts with a 'Telegram Trigger'. It starts to work when it receives a new message in that chat. 
2. The next is a "If" node which splits the input into either True or False based on the condition you set. So in my case, If the received msg is audio, it goes via one route. If not, the other route.
3. In the Audio path, I used "Get File" node of Telegram to download the audio file. Then, I connected Gemini Audio Transcriber node to transcribe the audio. Then I formatted the output and sent that to the AI Agent node to reply to the msg.
4. In the text path, I used the "Edit Field" node to format the output as "text" since the AI Agent innately accepts the input with the name "text" so I used that to change the name of the input.
5. Then I used the AI Agent node, to reply to analyse the input and generate reply for that msg.
6. Then I used "Send Message" node of Telegram to send reply to that message.
