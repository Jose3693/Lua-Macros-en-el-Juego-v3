# 🚀Lua Macros for SAMP
This script allows you to create and execute custom macros within the GTA San Andreas (SAMP) game using MoonLoader.
Macros are executed in sequence and can include automated actions, predefined text, and waiting times.<br>
![](https://i.imgur.com/qzmsrcp.png)<br>
## ✨ Main Features<br>
**🔹 1. Macro Profiles**
- Create and save different sets of macros.<br>
- Switch between profiles without deleting them.<br>
- Ideal for players who play on multiple servers with different commands.

**🔹 2. Dynamic Variables**<br>
These variables can be used in your macros to insert automatic and personalized information, making it easier to create dynamic commands and messages.

**🔹 3. Multi-language Support**
- Automatically detects the Windows language and applies it to the mod.
- Available in Spanish and English.
- Defaults to English if none is detected.

## 📜 Macro Syntax
You can combine the following functions within a macro to automate actions in the game.

### (chat) text
Opens the chat and enters the specified text without sending it.

Example:
```
(chat) /arrestar
(1000)
you are under arrest...
```
💡 This will open the chat and type /arrestar, ready for you to send manually. The next macro line will continue once you close the chat or send the /arrestar command.

---
### (time)
Sets a waiting time before continuing to the next macro command.
The time is expressed in milliseconds.

Example:
```
(1000)
hello
(1000)
hello 2
💡 Waits 1 second before executing the next macro.
```
---
### Your Character Variables
You can insert your character's information anywhere in the macro:
| Code      | Inserts                        |
| --------- | ------------------------------ |
| `(id)`    | Your character's ID            |
| `(fname)` | Full name                      |
| `(name)`  | First name only (no surname)   |
| `(zone)`  | Current city and zone name     |
---
### Your Vehicle Variables
You can insert your vehicle's information anywhere in the macro:
| Code      | Inserts                        |
| --------- | ------------------------------ |
| `(vid)`   | Vehicle ID                     |
| `(vname)` | Vehicle model                  |
| `(vplate)`| Vehicle's current plate        |
---
### Nearest Player
Automatically replaced with the information of the player closest to you:
| Code      | Inserts                        |
| --------- | ------------------------------ |
| `(cid)`   | Player ID                      |
| `(cfname)`| Full name                      |
| `(cname)` | First name only (no surname)   |
---
### Player You Are Aiming At
Inserts the information of the player you are currently aiming at:
| Code      | Inserts                        |
| --------- | ------------------------------ |
| `(tid)`   | Player ID                      |
| `(tfname)`| Full name                      |
| `(tname)` | First name only (no surname)   |
---
### 📌 Complete Macro Example
```
(chat) /me looks at (cfname) suspiciously
(1000)
(chat) Do you have something to hide, (cfname)?
```
💡 This macro:
```
Types in chat: /me looks at [nearest player's name] suspiciously.
Waits 1 second.
Types in chat: Do you have something to hide, [nearest player's name]?
```
---
## ⚙️ Notes
- Nearest player variables will not send the command if no player is detected nearby when pressing the key. The same applies for aiming and vehicle variables.
- You can mix normal text with dynamic variables in the same command.
- Waiting times (time) allow you to synchronize your macros for smooth execution.
- The (chat) pattern always requires you to close or send the chat command before continuing to the next macro.
