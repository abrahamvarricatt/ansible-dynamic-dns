# Dynamic DNS via Ansible

This playbook will make it easy to rent a new server from any provider, install
a basic webserver (to serve HTTP) and update DNS records on Cloudflare.

Refer to https://github.com/abrahamvarricatt/ansible-initial-server-setup for
basic setup.

```
ansible 2.4.3.0
```

## Step 1: Copy SSH private key

Copy the SSH `ansible.pem` file to the `ssh` folder.

```shell
$ cp ??/ansible.pem ssh/ansible.pem
```

## Step 2: Update inventory

Update `inventory/production.yml` to point to our webserver.

```shell
$ vim inventory/production.yml
```

## Step 3: Update Cloudflare credentails

Update `group_vars/vault/secrets.yml` with Cloudflare info.

```shell
$ vim group_vars/vault/secrets.yml
```

## Step 4: Run playbook!

Here is what you need to type on the CLI,

```shell
$ ansible-playbook -i inventory/production.yml site.yml
```
