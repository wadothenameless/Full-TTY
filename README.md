# Full-TTY
Switch to a Text Terminal (TTY) and change the shell to bash for an interactive session. Spawn a TTY, configure it, and set up bash. Optimize your terminal usage with this guide, tailored for Capture The Flag (CTF) challenges.
Switching to TTY

First, we check if we are in an interactive TTY (Text Terminal).

```bash
tty
```

If we are not in a TTY, we spawn one with:


```bash
script /dev/null -c bash
```

Now, we suspend the connection with Ctrl+Z to the machine and enter the following command:

```bash
stty raw -echo; fg
```

Press Enter and type the following command:

```bash
reset xterm
```

Now, we can use Ctrl+C, to enable Ctrl+L:

```bash
export TERM=xterm
```

Changing SHELL to bash

Check the type of shell we are using:

bash

echo $SHELL

If we are using a shell other than bash, we can change it by entering the following commands:

First, find the directory where bash is located:

bash

which bash

Export bash:

bash

export SHELL=/path_to_bash/bash

Now, we have bash and an interactive shell.

Finally, configure the rows and columns of the terminal to have the same dimensions as ours.

bash

stty rows 43 columns 169
