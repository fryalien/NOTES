**Neovim and Kitty Double Enter**

To address this problem, you can ensure that the `icrnl` setting is enabled by running the command `stty icrnl` in your terminal.

Adding this command to your `.profile` or `.bashrc` file can help maintain the correct terminal settings across sessions.

Additionally, ensure that your terminal settings are configured correctly. You can check your current settings by running `stty -a` and verify that `icrnl is set to on`.
