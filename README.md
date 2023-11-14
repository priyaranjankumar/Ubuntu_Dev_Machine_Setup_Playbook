# Ubuntu Development Machine Setup Playbook

This Ansible playbook automates the setup of a development environment on Ubuntu. Here's a brief overview of the steps it performs:

1. Clears the existing `/tmp` directory.
2. Copies a systemd file from `/usr/share/systemd/tmp.mount` to `/lib/systemd/system/tmp.mount`.
3. Creates a directory at `/etc/systemd/system/tmp.mount.d`.
4. Generates a custom options file for `tmp.mount` at `/etc/systemd/system/tmp.mount.d/options.conf`.
5. Activates and enables `tmp.mount` on boot.
6. Turns on the `ufw` firewall.
7. Disables system crash reports.
8. Sets system swappiness to 0.
9. Limits space used by `journald` to 256M.
10. Executes a distribution upgrade.
11. Installs a variety of tools and packages, including archiving tools, productivity tools, system tools, developer tools, download tools, media packages, and snap packages.
12. Creates a symlink for `bat`.
13. Points `nc` to nmap's netcat implementation.
14. Creates a `.ssh` directory for the user.
15. Generates directories for `golang` and updates `.bashrc` with `GOPATH`.
16. Installs virtualization tools and adds the user to the `docker` and `vboxusers` groups.
17. Enables permanent night light settings.
18. Changes `fstrim` to run daily instead of weekly.
19. Configures `poetry` to create virtualenv directories inside the project directory itself.

Ebter the following command to run the playbook:

```bash
ansible-playbook main.yml -vv -e "{ laptop_mode: True }" -e "local_username=$(id -un)" -K
```

Running the playbook will take some time, so feel free to grab a cup of coffee while you wait. ☕
