
# Moduli

# Creating Moduli File

Need to execute the following commands for a safer KexAlgorithms

```
     SSH_MODULI_BITS=4096
     ssh-keygen -G moduli-${SSH_MODULI_BITS}.candidates -b ${SSH_MODULI_BITS}
     ssh-keygen -T moduli.safe \
                -f moduli-${SSH_MODULI_BITS}.candidates \
                -b ${SSH_MODULI_BITS}
     awk '$5 > 3071' moduli-${SSH_MODULI_BITS}.candidates \
                 > moduli-${SSH_MODULI_BITS}
     cp moduli-${SSH_MODULI_BITS} /etc/ssh/moduli
```
