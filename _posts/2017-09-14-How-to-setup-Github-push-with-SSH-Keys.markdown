---
layout: post
title: "How to setup Github push with SSH Keys"
date: 2017-09-14
description: setup Github push with SSH Keys
image: /assets/images/placeholder-22.jpg
author: Dwi Sulfahnur
tags:
  - django
  - python
  - mysql
  - ubuntu
---

Every you push a commit to your repository, you usually have to enter your username and password. It will take much time and effort, In this post, i show you how to push your commit without enter username and password using ssh keys. So how to do it.

### Generating a new ssh key.
Open your terminal
Paste the text below, substituting in your GitHub email address.

{% highlight raw %}
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"{% endhighlight %}

This creates a new ssh key, using the provided email as a label.
When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.
At the prompt, type a secure passphrase.

### Adding your ssh key to the ssh-agents
Start the ssh-agent in the background.

{% highlight raw %}
eval "$(ssh-agent -s)"{% endhighlight %}

Add your SSH private key to the ssh-agent. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_rsa in the command with the name of your private key file.

{% highlight raw %}
ssh-add ~/.ssh/id_rsa{% endhighlight %}


### Adding a new SSH key to your GitHub account

Copy the SSH Key to your clipboard.
in this case, I using xclip tools to copy some text in terminal to my clipboard. so you have to install xclip by typing the following command in your terminal.(I use Ubuntu OS, adjust with your os)

{% highlight raw %}
sudo apt install xclip{% endhighlight %}

{% highlight raw %}
xclip -sel clip < ~/.ssh/id_rsa.pub{% endhighlight %}

In the upper-right corner of any page, click your profile photo, then click Settings.

![Markdowm Image](/assets/images/setup-Github-push-with-SSH-Keys1.png?raw=true)
  

In the user settings sidebar click SSH and GPG keys.

![Markdowm Image](/assets/images/setup-Github-push-with-SSH-Keys2.png?raw=true)

Click New SSH key or Add SSH key.

![Markdowm Image](/assets/images/setup-Github-push-with-SSH-Keys3.png?raw=true)
  
In the "Title" field, add a descriptive label for the new key. For example "My Ubuntu".

![Markdowm Image](/assets/images/setup-Github-push-with-SSH-Keys4.png?raw=true)

Paste your key into the "Key" field.
then, click Add SSH key.

![Markdowm Image](/assets/images/setup-Github-push-with-SSH-Keys5.png?raw=true)
  
If prompted, confirm your GitHub password.

![Markdowm Image](/assets/images/setup-Github-push-with-SSH-Keys6.png?raw=true)

 
### Configure you Github Repository
 
In your terminal, go to your repository directory, then typing the following command. Adjust with your repository address.

{% highlight raw %}
git config remote.origin.url git@github.com:your_username/your_project.git{% endhighlight %}