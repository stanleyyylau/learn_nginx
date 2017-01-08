###Let's install Vagrant###
- _Install VirtualBox: https://www.virtualbox.org/_
- _Install Vagrant: http://vagrantup.com/_


###Select a Vagrant Box from https://vagrantcloud.com###
```
#add it to your list of boxes
vagrant box add hashicorp/precise32
#create a new folder for your project & init vagrant
vagrant init hashicorp/precise32
#run your new machine
vagrant up
#ssh into your new machine
vagrant ssh
```

_Now you are connected to a new machine!_

- hit `exit` to disconnect

###Let's make this feel like the real world by adding a fake domain name###
- open the Vagrantfile and uncomment the private_network line & change to your desired IP
    - `config.vm.network "private_network", ip: "22.22.22.22"`
    - run `vagrant reload`
- make a fake domain for that ip
    - run `sudo open /etc/hosts -a "Sublime Text"` to open your /etc/hosts file in Sublime Text
    - add this line to the end of the file and save `22.22.22.22 mytestsite.com`

_Nice! Now going to mytestsite.com will connect to our machine!_

###Let's install nginx so we can see if our "domain" is working###
```
#always update apt-get on a new machine
sudo apt-get update
#install nginx
sudo apt-get install nginx
#start-er up
sudo service nginx start
```

Now, go to mytestsite.com...you should see
_Welcome to nginx!_
