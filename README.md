# Setting Up VSCode
First of all you need to download the [Docker](https://docs.docker.com/desktop/setup/install/windows-install/), then download the Dev Container Extention. 
Open VS Code, go to the Extensions view (Ctrl+Shift+X).
Search for Dev Containers (offered by Microsoft) and click Install.

After you install the Dev Container then Reopen in Container
A notification will pop up in the bottom-right corner of VSCode.

Reopen to develop in a container.

Click the "Reopen in Container" button.

You'll know it worked when you see a green area in the bottom-left corner of the status bar, saying something like "Dev Container: Debian". Then you're all set to build and test the custom chip

# Demux Chip

Example of a basic custom chip for [Wokwi](https://wokwi.com/).

The actual source code for the chip lives in [src/main.c](src/main.c), and the pins are described in [chip.json](chip.json).

## Building

The easiest way to build the project is to open it inside a Visual Studio Code dev container, and then run the `make` command.

## Testing

You can test this project using the [Wokwi extension for VS Code](https://marketplace.visualstudio.com/items?itemName=wokwi.wokwi-vscode). Open the project with Visual Studio Code, press "F1" and select "Wokwi: Start Simulator".

If you want to make changes to the test project firmware, edit [test/blink/blink.ino](test/blink/blink.ino), and then run `make test` to rebuild the .hex file. You'll need the [arduino-cli](https://arduino.github.io/arduino-cli/latest/installation/), which is already installed in the dev container.
