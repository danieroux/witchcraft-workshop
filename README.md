# Clojure + Minecraft Workshop, ClojureD 2022


Instructions and sample code for the
[Witchcraft](https://github.com/lambdaisland/witchcraft) (Clojure+Minecraft)
workshop given at ClojureD, June 2022.

## Change the (Minecraft) World with Code

Presenters: Ariel Alexi, Felipe Barros, Arne Brasseur

In this fun and creative workshop you’ll play Minecraft via the REPL. Build amazing structures, add custom player interactions, or spawn exploding chickens.

For best results join the workshop as a pair, so you have one laptop to display the game, and one for the REPL. You can run both on a single laptop, but it’s more fun with two.

We ask participants kindly to install Minecraft (server+client, see below) before the workshop so we can dive into the interesting bits right away, and we don't pull down the conference wifi when the workshop begins.

## Requirements (tl;dr)

- Java 17
- Clojure CLI
- A POSIX compatible shell (to run the install/start scripts)
- An nREPL-capable editor (e.g. VS Code+Calva, Emacs+CIDER, Vim+Conjure, Cursive, ...)

With these you should be able to install

- The Minecraft client 1.18.2
- The PaperMC server

As per the instructions below

### Java 17

Check the output of `java -version`

```
$ java -version
openjdk version "17" 2021-09-14
OpenJDK Runtime Environment (build 17+35-2724)
OpenJDK 64-Bit Server VM (build 17+35-2724, mixed mode, sharing)
```

When unsure look for AdoptOpenJDK for your platform, or use [sdkman](https://github.com/sdkman/sdkman-cli)

```
sdk install java 17-open
sdk use java 17-open
```

### Clojure CLI

Most versions should be fine, we don't use any of the breaking changes that were introduced. e.g.

```
$ clojure --version
Clojure CLI version 1.10.3.967
```

### Getting Minecraft Client, Option 1: scripted

If you have Minecraft already installed then you're all set, if not we provide
two scripts to easily install and run it.

```
bin/install-client
bin/start-client myusername
```

These should work even in offline mode (once installation is completed), so we
can still run the workshop in case the conference wifi gets overloaded. Of
course we expect everyone to have a Minecraft Java Edition player account, which
you get when [buying a copy of the game](https://www.minecraft.net/de-de/store/minecraft-java-edition), which at
the time of writing costs €23.95. Alternatively you can sign up for a “[XBOX PC
Game Pass](https://www.xbox.com/de-DE/xbox-game-pass/pc-game-pass)” for €1 for
the first month, and then immediately cancel.

### Getting Minecraft Client, Option 2: Launcher

Alternatively can also download the official launcher through the [Minecraft.net
site](https://www.minecraft.net/de-de/download) or by installing
[MultiMC](https://multimc.org/), and then creating a new instance.

Note that these last two are only launchers, you will have to go in and from the
launcher install the actual game. We'll be using the latest stable version
1.18.2, so make sure you have that ready and are able to start the game. This
will require Java 17, which you will also need for the workshop.

### Server Setup

We are going to use the [PaperMC](https://papermc.io/) modded Minecraft server,
and add to it the [witchcraft-plugin](https://github.com/lambdaisland/witchcraft-plugin) which
will supply an nREPL inside the Minecraft process that we can then connect to.

Everything is encapsulated in the `bin/start-server` script. This will download
PaperMC and install the Witchcraft-plugin.

## Connecting

Once your server is up and running you can connect to it both from the client
and from your editor.

Client:

- On the main menu click on `Multiplayer`
- Click on `Add Server`
- Server Address: `localhost:25565`
- Save the server, and double click on it in the list

Editor:

- Connect to nREPL at port 25555.

## Understanding the Basics

This workshop is open to anyone, regardless of whether you've actually played
Minecraft before. That said it will help tremendously to be familiar with the
basic concepts and mechanics. This goes for using Witchcraft in general, it pays
off to spend a little bit of time just playing to game before you start
manipulating it with code.

The video series [Minecraft Survival
Guide](https://www.youtube.com/playlist?list=PLgENJ0iY3XBjpNDm056_NSPhIntVMG0P8)
by youtuber Pixlriffs contains a video on almost every aspect and mechanic in
the game, and especially the first few are very instructive for anyone just
starting out

- [The Minecraft Player's Dictionary](https://www.youtube.com/watch?v=u7lE0MG80qw&list=PLgENJ0iY3XBjpNDm056_NSPhIntVMG0P8&index=1)
- [Controls, Keyboard Shortcuts, and F3](https://www.youtube.com/watch?v=bkQqqxpqFo0&list=PLgENJ0iY3XBjpNDm056_NSPhIntVMG0P8&index=2)
- [Video Settings & Accessibility](https://www.youtube.com/watch?v=W6eYr9lkK_s&list=PLgENJ0iY3XBjpNDm056_NSPhIntVMG0P8&index=3)



