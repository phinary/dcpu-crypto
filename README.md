# dcpu-crypto

This is a library of cryptographic functions for the DCPU-16
processor. I'm focusing on late-80s technology specifically, but later
algorithms may also be implemented.

## License

The dcpu-crypto library is released under the Mozilla Public License,
v. 2.0.

## Functions

### rc4_init

    rc4_init(void *key, int key_len_bytes, int state[129])

Initializes the 129 word state area with the given key for use with
<code>rc_crypt()</code>. The key length is a number of 8-bit bytes.

### rc4_crypt

    rc4_crypt(void *msg, int msg_len_bytes, int state[129])

En/Decrypt the provided message. State is a 129 word area previously
initialized with <code>rc4_init()</code>. The stream position is
maintained within the state, so successive calls to
<code>rc4_crypt()</code> with a given state will be the same as
concatenating the message and performing a single
<code>rc4_crypt()</code> call.
