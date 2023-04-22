---
title: "How To Install And Use Vagrant With Ubuntu 20.04"
seoTitle: "how to install vagrant on your computer"
seoDescription: "how to install and use vagrant with ubuntu"
datePublished: Sat Mar 11 2023 12:44:53 GMT+0000 (Coordinated Universal Time)
cuid: clf3ylkp1000f09ju3ooe1axl
slug: how-to-install-and-use-vagrant-with-ubuntu
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678537670283/6839b465-b304-4ddd-8439-b9e5c2121cc1.jpeg
tags: vagrant, virtual-machine, programming-blogs, developer-tools, virtual-environment

---

## VAGRANT

Vagrant is a tool that helps computer programmers create special virtual environments on their computers to work on their projects. These environments have all the necessary software, tools, and settings needed to work on the project. Vagrant makes it easy to create and share these environments with other team members, so everyone is working on the same setup. It's like having a special workspace just for your project, and Vagrant helps you create it easily.

## TOOLS

There are multiple tools out there that can help you create and manage virtual environments. Technologies using containerization allow one to manage virtual environments as well. In this tutorial, we are going to be using VirtualBox and Vagrant.VirtualBox and Vagrant together allow you to manage and ship isolated development environments.

VirtualBox is a program that allows you to create a "computer inside your computer". It's like having another computer that you can use to install a different operating system (like Windows, Linux or macOS), or to test software without affecting your main computer. You can create multiple virtual computers on your main computer, and each one can have its unique settings, such as how much memory or storage it has. This allows you to experiment and try out new things without worrying about damaging your main computer. Think of VirtualBox as a big box that you can open on your computer, and inside that box, you can create different computers with different settings. It's a great tool for learning, experimenting and testing things without worrying about affecting your main computer.

### HOW TO INSTALL VAGRANT

**MACOS AND WINDOWS:**

1. Download VirtualBox from this [link](https://www.virtualbox.org/wiki/Downloads)
    
2. Follow all the steps to install it
    
3. Download vagrant from this [link](https://developer.hashicorp.com/vagrant/downloads)
    
4. Follow all the steps to install it
    
5. Open your cmd/terminal and execute this command:(this will take some time but we only do it once and then we are done). The below command is used to add Ubuntu 20.04.
    
    `>> vagrant box add ubuntu/focal64`
    
6. Now we need to create a virtual machine(you don’t have to execute this command line every day, only once, to create a new virtual machine). Execute this command in the terminal/ cmd
    
    `>> vagrant init ubuntu/focal64`
    
7. Then run this command too: We are running this command to avoid any issues with the last version of Vagrant (2.2.4 or latest)
    
    `>> vagrant plugin install vagrant-vbguest`
    

**UBUNTU:**

1. Open the terminal application.
    
2. Install the virtual box with the following command:
    
    `$ sudo apt-get install virtualbox`
    
3. Install vagrant with the following command:
    
    `$ sudo apt-get install vagrant`
    
4. Add the Ubuntu 20.04 (Focal) image to your box list: (this step can take time) `$ vagrant box add ubuntu/focal64`
    
5. Now we need to create a virtual machine(you don’t have to execute this command line every day, only once, to create a new virtual machine). Execute this command in the terminal/ cmd
    
    `$ vagrant init ubuntu/focal64`
    

### **VAGRANT COMMANDS**

Here are some of the most common Vagrant commands that you can use in your terminal or command prompt, depending on your operating system:

1. **vagrant up:** This command starts your Vagrant environment.
    
2. **vagrant ssh:** This command connects you to the virtual machine using a secure shell (SSH) connection.
    
3. **vagrant halt:** This command stops your Vagrant environment.
    
4. **vagrant reload:** This command reloads your Vagrant environment, which can be useful if you've made changes to the Vagrant configuration file.
    
5. **vagrant destroy:** This command deletes your Vagrant environment, including any data or changes you've made.
    
6. **vagrant status:** This command shows the current status of your Vagrant environment, including whether it's running or not.
    
7. **vagrant provision:** This command applies any changes you've made to your Vagrant environment since it was last provisioned.
    

There are many other Vagrant commands you can use, depending on your needs.

### **HOW TO INSTALL AND CONFIGURE GIT IN YOUR VAGRANT ENVIRONMENT**

1. Open your terminal /cmd and type the following command to start running our vagrant environment:
    
    `>> vagrant up`
    
2. To access our vagrant environment terminal type the following command in your cmd/ terminal:
    
    `>> vagrant ssh`
    
3. Once you are in the vagrant environment which you now have access to through the shell, you can now install and configure git
    
4. Installing GIT:
    
    `$ sudo apt-get update`
    
    `$ sudo apt-get upgrade`
    
    `$ sudo apt-get install git`
    
5. Once you have installed git in your vagrant environment configure it:
    
    `>> git config --global` [`user.email`](http://user.email) `"your email"`
    
    `>> git config --global` [`user.name`](http://user.name) `"your username"`
    
6. Now access the relevant directory or create one and then clone your repository
    
7. Once you are done using your vagrant environment, you can shut it done using the following commands
    
    i. To get out of the ssh shell execute the following command:
    
    `>> exit`
    
    ii. To shut down the vagrant environment execute the following command in the terminal:
    
    `>> vagrant halt`