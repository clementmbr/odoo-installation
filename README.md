# 1. Server connection

```bash
# 1. From a terminal, connect to your server as root
# (via ssh key in this case)
ssh root@$YOUR_IP_ADDRESS
# 2. As root user in your server,
# add a sudo user called 'erp' with no login password
adduser --disabled-password erp
# 3. Add user 'erp' to the 'sudo' group (=to become a sudoer)
usermod -aG sudo erp
```

4. Enable the user _erp_ to use `sudo` without providing password by adding the line `erp ALL=(ALL) NOPASSWD: ALL` under `#includedir /etc/sudoers.d` in the _sudoers_ configuration file called _/etc/sudoers_ :

{% code title="/etc/sudoers" %}
```bash
#[...]
#
#includedir /etc/sudoers.d
erp ALL=(ALL) NOPASSWD: ALL
```
{% endcode %}

5. login as user 'erp' and open a byobu session as user 'erp'

```bash
# login as user 'erp'
su - erp
# open a byobu session
erp@your_hostname:~$ byobu
```

{% hint style="info" %}
[Byobu](https://byobu.org/) allows to exit your server without closing running programs :

* type **`byobu`** to open a _byobu_ session and launch programs within _byobu_
* press **`F6`** to exit from _byobu_ without closing running programs
* type **`byobu`** to re-enter _byobu_ with your running programs
* from within _byobu_ type **`exit`** or **`Ctrl+D`** to close both _byobu_ **and** all the running programs

Another advantage in using byobu is that you don't close your session \(and logs  history\) if you are unintentionally disconnected from your server.
{% endhint %}







