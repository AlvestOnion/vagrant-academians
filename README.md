# Vagrant-Academians

This is a development environment for Academians members which consists of two servers:

* `Web` which serves APIs & Front End, closely mimics [Heroku's cedar stack](https://github.com/ejholmes/vagrant-heroku).
* `Redis` which serve [Redis] for caching and persistent storage.

Anyway, those two servers are equipped with PostgreSQL.

## Installing

Before using this repo, you must have the following prerequisites:

* [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](http://www.vagrantup.com/downloads.html)

## QuickStart

1. Clone this repo
2. `vagrant up`
3. `vagrant ssh`
4. `cd` to `app` directory, and create your dashing project here:
```bash
$ dashing new app # must be app, so web instance will pick your dashing project up.
$ cd app
$ bundle
```
5. On your computer, start sublime text and edit the dashing project inside the `app` directory.
6. To run dashing, run `dashing start`
7. Your dashing project will be avalaible on [127.0.0.1:3030](127.0.0.1:3030)
8. to see `redis`' IP address, `vagrant ssh redis`, and run `ifconfig`.
9. PROFIT

## Limitations

Each VM has 512 MB RAM allocated by default.
