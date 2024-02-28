<-- back to [[3. 25th Jan '24 Thursday#Digital Ocean Setup]]

While saving the rsa key, save it with the name digitalocean and store this in your .ssh directory.
Once you have the public key, paste it in the digital ocean page and name it.
A VM is called a droplet in digital ocean.

Set up a password for the key so that even when we login using the private key, we will need to enter the password to login. So that no one using my laptop can login to the vm.

The permissions for the private key have to be `600 -rw-------` for the private key, so that only the `owner` of the private key can access it. If we don't have this , we will not be able to ssh into the VM.