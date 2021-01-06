# MapleStory Timekeeper

Super basic bot to create and update a voice channel in a Discord server.

You'll need to register an application with [Discord Developers](https://discord.com/developers/applications) and make sure that you enable it as a **Bot User** from the Bot menu on the left.

## Installation for Linux

1. Build the binary (see [Building On Windows](#building%20on%20windows) if building for Linux on a Windows machine)
2. Copy the binary to any directory you desire and make it executable
3. Copy `config.toml.sample` and remove the `.sample` and update the values
4. Copy `maplestory-timekeeper.service.sample` to `/etc/systemd/system/maplestory-timekeeper.service`
5. Update the contents of `maplestory-timekeeper.conf` with :
    - The User/Group to run as (remove Group if you're not using it)
    - The executable location in `ExecStart`. e.g.: `ExecStart=/../parent-dir/maplestory-timekeeper`
    - The working directory in `WorkingDirectory`. e.g.: `WorkingDirectory=/../parent-dir`
6. Reload daemon configs with `sudo systemctl daemon-reload`
7. Enable the daemon to run on system start `sudo systemctl enable maplestory-timekeeper`
8. Start the bot `sudo systemctl start maplestory-timekeeper`

## Building on Windows

You can build Golang applications on Windows for Linux by running `GOOS=linux GOARCH=amd64 go build`