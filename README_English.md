
# 🚀 Lua Macros for SAMP  
This script allows you to create and run custom macros within the GTA San Andreas (SAMP) game using MoonLoader.  
Macros run sequentially and can include automatic actions, predefined texts, and wait times.<br>  
![](https://i.imgur.com/qzmsrcp.png)<br>  

## ✨ Main Features<br>  
**🔹 1. Macro Profiles**  
- Create and save different sets of macros.<br>  
- Switch between profiles without needing to delete them.<br>  
- Ideal for players who play on multiple servers with different commands.  

**🔹 2. Dynamic Variables**<br>  
These variables can be used in your macros to insert automatic and personalized information, making it easier to create dynamic commands and messages.  

**🔹 3. Multi-language Support**  
- Automatically detects Windows language.  
- Available in Spanish and English.  
- Defaults to English if none is detected.  

## 📜 Macro Syntax  
You can combine the following functions within a macro to automate actions in the game.  

### (chat) text  
Opens the chat and inputs the specified text without sending it.  

Example:  
```
(chat) /arrest  
(1000)  
you are under arrest....  
```
💡 This will open the chat and write /arrest, ready for you to send it manually. The next macro line will continue once you close the chat or send /arrest.  

---  
### (time)  
Sets a wait time before continuing to the next macro command.  
Time is expressed in milliseconds.  

Example:  
```
(1000)  
hello  
(1000)  
hello 2  
```
💡 Waits 1 second before executing the next macro command.  

---  
### Your Character Variables  
You can insert your character’s information anywhere in the macro:  
| Code     | Inserts                     |  
| -------- | --------------------------- |  
| `(id)`   | Your character’s ID         |  
| `(fname)`| Full name                  |  
| `(name)` | Only the first name (no last name) |  

---  
### Nearest Player  
Automatically replaced with the information of the player closest to you:  
| Code       | Inserts                     |  
| ---------- | --------------------------- |  
| `(cid)`    | Player ID                   |  
| `(cfname)` | Full name                   |  
| `(cname)`  | Only the first name (no last name) |  

---  
### Player You Are Aiming At  
Inserts information about the player you are aiming at:  
| Code       | Inserts                     |  
| ---------- | --------------------------- |  
| `(tid)`    | Player ID                   |  
| `(tfname)` | Full name                   |  
| `(tname)`  | Only the first name (no last name) |  

---  
### 📌 Full Macro Example  
```
(chat) /me looks suspiciously at (cfname)  
(1000)  
(chat) Do you have something to hide, (cfname)?  
```
💡 This macro:  
```
Writes in chat: /me looks suspiciously at [nearest player’s name].  
Waits 1 second.  
Writes in chat: Do you have something to hide, [nearest player’s name]?  
```  

---  
## ⚙️ Notes  
- Nearest player variables will not send the command if no player is detected nearby when pressing the key. The same applies to the aiming player variables.  
- You can mix normal text with dynamic variables in the same command.  
- Wait times (time) allow you to synchronize your macros to run smoothly.  
- The (chat) pattern always requires you to close or send the chat command to continue with the next macro.  
