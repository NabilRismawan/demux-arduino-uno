# Setting Up VSCode
First of all you need to download the [Docker](https://docs.docker.com/desktop/setup/install/windows-install/), then download the Dev Container Extention. 
Open VS Code, go to the Extensions view (Ctrl+Shift+X).
Search for Dev Containers (offered by Microsoft) and click Install.

# Setting Up the Dev Container
Once the prerequisites are met, follow these steps in VS Code.

Step 1: Open Your Project Folder
Open the folder where your project is located (or an empty folder for a new project) in VS Code.

File > Open Folder...

Step 2: Add Dev Container Configuration Files
Now, you'll tell VS Code to create the necessary configuration files.

Open the Command Palette using Ctrl+Shift+P (or Cmd+Shift+P on Mac).

Type Add Dev Container and select the command "Dev Containers: Add Dev Container Configuration Files...".

VS Code will now show you a list of predefined container templates (e.g., Python 3, Node.js, Go, etc.). For a general-purpose environment, a good choice is "Debian" or "Ubuntu". Select one.

You may be asked to choose a version (e.g., bullseye for Debian). The default is usually fine.

You might also be asked to add extra features (like installing Git or the GitHub CLI). You can select any you need or just click OK to continue.

VS Code will create a new folder in your project named .devcontainer containing a devcontainer.json file. This file is the "recipe" for your development environment.

Step 3: Reopen in Container
A notification will pop up in the bottom-right corner of VS Code.

Folder contains a Dev Container configuration file. Reopen to develop in a container.

Click the "Reopen in Container" button.

The first time you do this, it might take a few minutes as Docker needs to download the base image for your container. Once it's done, your entire VS Code window will be running inside the isolated Docker container.

You'll know it worked when you see a green area in the bottom-left corner of the status bar, saying something like "Dev Container: Debian".

# Demux Chip

Example of a basic custom chip for [Wokwi](https://wokwi.com/).

The actual source code for the chip lives in [src/main.c](src/main.c), and the pins are described in [chip.json](chip.json).

## Building

The easiest way to build the project is to open it inside a Visual Studio Code dev container, and then run the `make` command.

## Testing

You can test this project using the [Wokwi extension for VS Code](https://marketplace.visualstudio.com/items?itemName=wokwi.wokwi-vscode). Open the project with Visual Studio Code, press "F1" and select "Wokwi: Start Simulator".

If you want to make changes to the test project firmware, edit [test/blink/blink.ino](test/blink/blink.ino), and then run `make test` to rebuild the .hex file. You'll need the [arduino-cli](https://arduino.github.io/arduino-cli/latest/installation/), which is already installed in the dev container.
