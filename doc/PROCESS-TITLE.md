# Process Title in SSH/SSHD processes

# General SSH process titles
For either SSH server daemon or SSH client process, its process title may be one
of the following:

* <username>@notty - <username> session has no pseudo-tty.
* <username>@/dev/ttyXX - <username> session has connected to a working pseudo-tty.
* <username>@internal-sftp - <username> session has a sftp subsystem working.

## SSH daemon server process

* [accepted]     - Child process is accepting connection
* [net]          - Successful forked of child process and non-inetd (direct) connection
* <username> [priv] - Channel-layer permitted <username> via PermitOpen, PermitListen
* <username>     - Just authenticated as <username>.
* unknown        - Connected using an unknown local user account.
* <username> [net] - SSH user authentication occuring over network.
* unknown [net] - Connected using an unknown remote user account.

## SSH client process

* <username> [accepted] - Newly-created child process now creating a new channel.
* <filespec> [mux] - ControlPath successfully opened and forked (via ssh -f).
* <username> [pam] - PAM authentication underway in PAM thread for SSH user <username>.
* <username> [stopped mux] - SSHMUX_COMMAND_STOP occurred (via ssh -Ostop )
