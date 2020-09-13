if your linter can't see it but you can run the file

maybe it's a path that only works because of your .env file

Your linter doesn't use that. So when you run it, it will run, but not for pytest or your linter...
try to fix your linter by exporting the environment variables you want

As far as I understand it, the VSCode workspace setting python.pythonPath is not to be confused with the environment variable $PYTHONPATH.
python.pythonPath is the path to the python interpreter used for debugging or running the code, while $PYTHONPATH is the environment variable which python uses to search for modules.
There are two different things going on here:
Where the computer looks for the python interpreter - python.pythonPath

And where that inpreter looks for packages - $PYTHONPATH


Host host101
  HostName juliushost101.localnetwork.internalnetwork.tld
  User root
  Port 2222
  IdentityFile ~/.ssh/id_rsa2 # you might have to do this

test it out like this:ssh -F ~/config localhost
You will need sshd in the container for this to work?

config can be"program": "${file}"or"program": "/full/path/to/my/file.py"
"console": "integratedTerminal"or"console": "internalConsole"

