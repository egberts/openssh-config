
# OpenSSH SSH Server Daemon environment names

Following environment names is used by openssh-portable Git commit fbd9729d, Dec 21, 2019.

## SSH Server environment names

Following environment names covers just the SSH Server.

### OS-related environment names

Followings environment names cover the OS aspect of SSH Server.

* COMSPEC - A fallback shell filespec in case SHELL is not defined. (Windows)
* DISPLAY - See pam\_env.conf(5) man page for details.
* PATH - Set to the default PATH, as specified when compiling ssh.  See pam\_env.conf(5) man page for details.
* LANG
* PAM\_CONV - Sets the credential for PAM usage
* PAM\_RHOST - Remote user name that is provided by PAM module. (see pam\_ftp(8))
* PAM\_TTY - Controlling tty indicate the terminal that the user is using to
  connect to the SSH server.  The PAM\_TTY item is likely to be of
  the form "hostname:0" which includes a `:' character in its value. (see
pam_access(8)).
* SHELL - SHELL environment variable indicating the shell binary filespec if
                 it is set or the shell specified by the invoking user's pass‐
                 word database entry.
* SSH_AUTH_INFO_0 - PAM-provided security-sensitive details about terminal session.  Blacklisted if UsePAM is 'yes', may still be leaked if UsePAM is 'no'.
* TERM - Terminal type. Typically set to 'linux' or 'vt100'. Set by getty(8) or init(8).
* TMPDIR - If set, bash uses its value as the name of a directory in which bash creates temporary files for the shell's use.

### SSH Server-specific environment names

Followings environment names cover specifically the SSH protocol.

* AUTHSTATE
* KRB5CCNAME
* SSH_AGENT_PID - holds the SSH agent's process ID.
* SSH_AUTH_SOCK declares the location of unix socket that can be used to forward an authentication request back to the previous host (ex: /tmp/ssh-NjPxt6779/agent.8669).  Only present if using SSH agent forwarding.  A UNIX-domain socket is created and the name of this socket is stored in the SSH_AUTH_SOCK environment variable.  The socket is made accessible only to the current user.  This method is easily abused by root or an‐ other instance of the same user.

## SSH Client

### OS-Specific environment names for SSH Client
* DISPLAY - The DISPLAY variable indicates the location of the X11 server.  It is automatically set by ssh to point to a value of the form “hostname:n”, where “hostname” indicates the host where the shell runs, and ‘n’ is an integer ≥ 1.  ssh uses this special value to forward X11 connections over the secure channel.  The user should normally not set DISPLAY explicitly, as that will render the X11 connection insecure (and will require the user to manually copy any required authorization cookies).
* HOME - Set to the path of the user's home directory.
* LOGNAME - Synonym for USER; set for compatibility with systems that use this variable.
* MAIL - Set to the path of the user's mailbox.
* USER - Set to the name of the user logging in.

### Environment Names for SSH Client
* SSH_ASKPASS - If ssh needs a passphrase, it will read the passphrase from the current terminal if it was run from a terminal.  If ssh does not have a terminal associated with it but DISPLAY and SSH_ASKPASS are set, it will execute the program specified by SSH_ASKPASS and open an X11 window to read the passphrase.  This is particularly useful when calling ssh from a .xsession or related script.  (Note that on some machines it may be necessary to redirect the input from /dev/null to make this work.)
* SSH_CLIENT - Contains remote IP address and its source/destination port numbers (deprecated)
* SSH_CONNECTION shows the source IP and port of the previous host, as well as the local IP and port (ex: 10.22.248.74:44727 10.8.75.110:22). Identifies the client and server ends of the connection.  The variable contains four space-separated values: client IP address, client port number, server IP address, and server port number.
* SSH_ORIGINAL_COMMAND - This variable contains the original command line if a forced command is executed.  It can be used to extract the original arguments.
* SSH_TTY - This is set to the name of the tty (path to the device) associated with the current shell or command.  If the current session has no tty, this variable is not set.
* SSH_TUNNEL - Optionally set by sshd(8) to contain the interface names assigned if tunnel forwarding was requested by the client.
* SSH_USER_AUTH - Optionally set by sshd(8), this variable may contain a pathname to a file that lists the authentication methods successfully used when the session was established, including any public keys that were used.
* TZ - This variable is set to indicate the present time zone if it was set when the daemon was started (i.e. the daemon passes the value on to new connec‐ tions).

## SSH Tools environment name

* SSH_SK_PROVIDER - Specify desired generator when testing candidate moduli for DH-GEX for the ssh-keygen(1).
* SSH_SK_HELPER - ssh-agent(1) helper program for PKCS#11 support
