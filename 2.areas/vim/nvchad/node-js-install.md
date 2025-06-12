#### Installing Node.js
``` bash
# Download and install nvm:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
# in lieu of restarting the shell
\. "$HOME/.nvm/nvm.sh"
# Download and install Node.js:
nvm install 22
# Verify the Node.js version:
node -v # Should print "v22.14.0".
nvm current # Should print "v22.14.0".
# Verify npm version:
npm -v # Should print "10.9.2".
```
I added the path of the second step directly to my .bashrc file and restarted the shell.

all checks worked after nvm install 22

installed it on .config as usual

[[nvchad-language-servers]]
