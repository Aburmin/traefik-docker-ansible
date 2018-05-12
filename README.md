# Ansible : Multiple Websites with Traefik and Docker

This is an [Ansible](https://www.ansible.com) playbook to install multiple Websites on a single Ubuntu server with [Docker](https://www.docker.com) and [Traefik](https://traefik.io).

## Requirements

+ Ansible >= 2.4.0.0

## Applications

This playbook is designed to install a bunch of useful tools :

+ Docker
+ Docker-compose
+ Traefik
+ Vim
+ Git
+ htop
+ ntp
+ Curl
+ ZSH + Oh My Zsh with "ys" theme

## Installing on production

Setup your variables in the ```hosts``` and the ```playbook.yml``` files.

Then run the playbook :

```bash
$ ansible-playbook -i hosts playbook.yml
```

### Example of hosts file

```yaml
# hosts

[webservers]
example.com

[webservers:vars]
ansible_python_interpreter=/usr/bin/python3

gandi_api_key=your-gandi-api-key
acme_email=your@email.com
acme_provider=example # Comment this line to completly disable acme
```

## Installing on virtual machine

You can also test this Playbook on a virtual machine for some tests.

Before starting, you need to install :

+ [Vagrant](https://www.vagrantup.com)
+ [Virtualbox](https://www.virtualbox.org)

Then run :

```bash
$ vagrant up
```

The default IP address is ```192.168.50.4```. You need to setup your ```hosts``` and ```~/.ssh/config``` files to give an SSH access to Ansible into your virtual machine.

You could find more informations in [this article](https://guillaumebriday.fr/utiliser-la-commande-ssh-pour-entrer-dans-une-machine-vagrant) (in French).

## Contributing

There is still a lot of work to do !

Do not hesitate to contribute to the project by adapting or adding features ! Bug reports or pull requests are welcome.

## License

This project is released under the [MIT](http://opensource.org/licenses/MIT) license.
