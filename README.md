## Welcome to GitHub Pages

Glad to meet you guys here, below is the details about lightpaas.</br>
Even people who clone this project would follow the Apache Linsence, but never mind, just treat it as your own.</br>
I will be happy if this helps you.

### File Structure

I don't put any `hosts` file in this repo(so far), so what you could see are just roles seeming like individually.</br>
And I will say, that's it. You may use one of these roles to apply, certainly more than one will be also worked. But please follow guide below. I am not trying to confuse you guys here.</br>
#### common role
This is more like common settings on a Linux host, or you may say Linux OS.

#### zookeeper role
This is zookeeper installation role.

#### mesosphere role
This is a role which will install and setup `docker`, `mesos`, `marathon`.

### How to Work?

You may use those roles individually, i.e., you may just execute deployment of `zookeeper` or `mesosphere`, even `common`.</br>
But make sure you understand the dependency rules among them.

#### Individually

- common -- As said above, it's a common setting role for linux host, you may coustomize it for yourself. This is just a guideline.</br>
Your `hosts` file may like below:</br>
>`[paas]`</br>
>`10.10.100.1`</br>
>`10.10.100.2`</br>
>`10.10.100.3`</br>

And if you wanna coustomize parameters for common setting, just have a look at `defaults/main.yaml` file. </br>
Then, playbook for common role may like:</br>
>`- hosts: paas`</br>
>`  remote_user: root`</br>
>`  roles:`</br>
>`    - common`</br>

- zookeeper -- A zookeeper installation role. It relies on tarball of JDK and Zookeeper, which means we can only install them from tarball. I will update it soon, please give a while. Then, the `hosts` file may like below:</br>
>`[zookeeper]`</br>
>`10.10.100.1`</br>
>`10.10.100.2`</br>
>`10.10.100.3`</br>

And playbook:
>`- hosts: zookeeper`</br>
>`  remote_user: root`</br>
>`  roles:`</br>
>`    - zookeeper`</br>

Make sure you have prepared tarballs for jdk and zookeeper in the right directory defined in `defaults/main.yaml` file.

- mesosphere -- A installation role for `docker`, `mesos` and `marathon`. 

#### Jointly

### Name from?

My name is a special word in Chinese, it could be found in English exactly —— Highlight.</br>
But in China, we put family name in front of first name, so it becomes —— High·Light.</br>
So it is obviously, I choose Light as my first name in English, and keep Family name as it is in Chinese —— Gao.</br>
Now, back to this project, lightpaas, which means Light's PaaS. Yeah, got it?

### Support or Contact

This is a totally personal project, so I am not sure that it could be updated continously. But I will try my best.</br>
If you meet some bug(s), please contact me(gaoliang0806@163.com) without hesitate.</br>
Thanks for your help.
