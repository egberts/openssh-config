# openssh-config
Latest security settings in OpenSSH configuration files.

# CAVEATS
This stuff is not going to work on macOS Big Sur (11.3; OpenSSH_8.1p1) or lower because Apple OS team actually yanked the support for this 'include' directive keyword OUT of their brand of OpenSSH server.  But you can use "half" of this repo for the client side.  Sorry.

# Organization
The OpenSSH option parameter settings in the ssh_config configuration file has been reorganized to execution-order; not when it was first read from the configuration but when it was first REFERENCED in the executablec code.

Each parameter setting has annotation of their corresponding OpenSSH source code and its line number(s).

# Security
Each uncommented parameter settings have been selected for maximum (albiet restrictive) security.

# Production
You probably should not use this repo for production that leverages SSH as their primary transport protocol as the time it takes to read all these config files would be nooticeable.

If your business model depends on rapid succession of SSH connections, you need
to fire the System Architect/System Engineers for implementing that.

# References
* http://docs.hardentheworld.org/Applications/OpenSSH/
