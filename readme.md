# Links to projects

1. [esp-open-sdk](https://github.com/pfalcon/esp-open-sdk "buildtools for esp8266")
2. [micropython](https://github.com/micropython/micropython "micropython project")
3. [online help files](https://docs.micropython.org/en/latest/ "help files for building micropython and quick references for some boards")
4. [webrepl project](https://github.com/micropython/webrepl "WebREPL client for MicroPython")
5. [EsPy tool](https://github.com/jungervin/EsPy "Tool for acces esp fs and scripts")

All projects contain build instruction in readme.md file in a root of the project.

# Build sequence

1. buildtools - gcc for esp8266

2. micropython unix
	> micropython/ports/unix$ make

3. micropyth port for esp8266 - esp micropython firmware
	> micropython/ports/esp8266$ make

4. user module hworld - C_Module for micropython
	> micropython/examples/usermodule/hworld$ make
	
	![CompilingUserModule](/make_hworld.png)

5. programm esp board with esptool.py
6. main.py: executed after boot.py, may be used for some actions - connect to local WiFi,
		may be leave esp-board in a AccessPoint mode(connect to eps-board wifi network nedeed)

### Next steps are on Windows with EsPy tool

	![EsPy](/espy_script_comment.png)

7. connect to the board
8. in file manager: copy to esp filesystem main.py and hworld.mpy
9. in interactive window: send to the board <ctrl>+D to restart
10. in interactive window:
	> import webrepl; webrepl.start(password="123456")
11. connect to esp board with local WebREPL page
12. enter password and you may use micropython REPL over WiFi
	![WebREPL](/webrepl_local.png)
