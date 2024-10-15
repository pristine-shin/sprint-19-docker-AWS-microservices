# Trying Out Alpine Linux

**SOLO PROJECT**

* Install Docker Desktop.
* Launch a Docker container for the `alpine` image in interactive mode running 
  the `sh` shell. You will probably want to store your files in a volume so you
  don't lose them when the container is stopped.
  * Run 
  `docker container run -it --mount source=alpine-project,target=/app alpine sh`
* Install Node.js, Python, and Nano. Here are the
  package names for you and links to their package documentation.
  * [Node.js]
  * [npm]
  * [Python3]
  * [Nano]
* Once you have those installed,
  * Create a simple Express.js application that serves a single HTML page using
    Nano as your console-based text editor.
    * Hint: Change directory to the folder you mounted when running the 
      container (`cd /app`).
    * Hint: To open a file with nano, type `nano «file name»`.
  * Create a simple Flask application that serves a single HTML page using Nano
    as your console-based text editor.
    * Hint: You will need to install `pip` and `pipenv` but there's no alpine
      package for them! You can follow the [Pip Installation] instructions 
      to install it manually. 
      * Remember, if you receive a message that [curl] or any other package is 
         not found, then the first place to check is the [Alpine Package Keeper]
         (`apk`) because that is the easiest way to install.
      * After installing pip, it will be in your home directory, and pip
        will tell you `~/.local/bin` isn't in your path. Do you remember how to
        add a directory to you `PATH`?
      * You'll need to use pip to install pipenv.
    * Hint: The default shell in alpine linux is `ash`. You can install `bash`
      with `apk` if you would like, although you'll have to run it manually each
      time you login. *Bonus*: Change your default shell to bash
* Disconnect from the docker container using `exit`
  * Hint: Each time to you run the container, you will need to reinstall the 
    packages because those are saved only in the (ephemeral) container, and not
    the (persistent) volume.


[Node.js]: https://pkgs.alpinelinux.org/package/v3.12/main/x86/nodejs
[npm]: https://pkgs.alpinelinux.org/package/v3.12/main/x86/npm
[Python3]: https://pkgs.alpinelinux.org/package/v3.12/main/x86/python3
[Nano]: https://pkgs.alpinelinux.org/package/v3.12/main/x86/nano
[curl]: https://pkgs.alpinelinux.org/package/v3.12/main/x86/curl
[Pip Installation]: https://pip.pypa.io/en/stable/installing/
[Alpine Package Keeper]: https://pkgs.alpinelinux.org/packages?name=&branch=v3.12
