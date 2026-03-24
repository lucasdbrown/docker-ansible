# Docker Ansible
Simple Ansible project to install Docker Engine and Docker Compose plugin on:
- Debian
- Kali
- Red Hat family

Install Verification:
- checks `docker version`
- checks `docker compose version`
- runs a `hello-world` container
- runs a temporary Compose test
- removes temporary test files after validation

## Quick start (for running locally)

Clone it, then run:

```bash
chmod +x run.sh
./run.sh
```

## Run against a remote host

Edit `inventory/hosts.ini`.

Example:

```ini
[docker_hosts]
server1 ansible_host=192.168.1.50 ansible_user=myuser
```

Then run:

```bash
./run.sh
```

If your remote user needs sudo:

```bash
./run.sh -K
```

## What the Ansible does

1. Adds the official Docker repo
2. Installs Docker Engine
3. Installs Docker Compose plugin
4. Starts and enables Docker
5. Verifies Docker works
6. Verifies Compose works
7. Cleans up temporary test artifacts

## Requirements

You need Ansible installed on the control machine.

Example:

```bash
python3 -m pip install ansible
```