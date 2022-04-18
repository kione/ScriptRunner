ScriptRunner
============

Inspired by https://www.youtube.com/watch?v=BLkjVzc5u6E "Controlling Websphere through Minecraft" I found this project. Great work from Thomas (trichner). Testet in various Minecraft server versions.

This is a Bukkit/Spigot Minecraft plugin that bridges bash scripts and batch files with minecraft.

The plugin adds two new commands:

`/sh [script] [args]`
starts a script asynchronously, you will be notified when the script exits. Use this command for scripts that might take some time.


`/bsh [script] [args]`
starts a script synchronously. This will block the servers main thread until the script exits. If the script isn't very
short, this might timeout the whole server. Use it wisely.


The output of your scripts is appended to a file named `lastlog.txt` in the plugins folder. All scripts you want to run have to be in the plugins data folder i.e. `plugins/ScriptRunner/` and need appropriate file permissions. Only scripts in this folder can be executed and script naming is whitelisted. Valid characters in a script filename are: A-Z,a-z,0-9, '-', '_', '.'


INSTALLATION:

You will need maven, so install it. After that clone the code to your server. Inside the directory you now should find pom.xml
which is necessary for your command 
```
mvn package
```
The plugin will be packaged to scriptrunner-0.1.6.jar to target/
```
cp target/scriptrunner-0.1.6.jar /minecraftserver/plugins/
```
You now should restart/start your mc server, this will generate the ScriptRunner directory. This directory will host your scripts and a lastlog

Executing /sh script.sh via the minecraft terminal requires you to be op.