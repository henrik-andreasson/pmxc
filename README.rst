pmxc - a console client for Proxmox VE
======================================

Install on Debian
+++++++++++++++++

.. code:: bash

    sudo apt install python3-pip python3-uvloop python3-aiohttp python3-texttable python3-aiodns python3-chardet virt-viewer
    sudo pip3 install ".[performance,uvloop]"

Using pmxc
++++++++++

First create a remote:

WARNING: If you store the password it will be saved in plain text in ~/.config/pmxc/config.json

.. code:: bash

    $ pmxc remote add -d pve01 https://pve01.fk.jochum.dev root@pam

Now you can list VM's:

.. code:: bash

    $ pmxc qemu list pve01

Or containers:

.. code:: bash

    $ pmxc lxc list pve01


Or open a the virt-viewer on VM id **100**:

.. code:: bash

    $ pmxc qemu spice pve01:100

Or open a shell on the container **101**:

You can exit it with: CTRL+A q

.. code:: bash

    $ pmxc lxc enter pve01:101

Have fun with pmxc i hope you like it as i do :)

Windows
++++++++++++++++++

2018 I had success with babun on Windows, now lacking a Windows box and babun discontinued I don't have any clues.
It should work unter cygwin though.

The version parts
+++++++++++++++++

The first 2 numbers are the Promox VE API pmxc targets to, the next 2 are the pmxc version.

Like 5.2.0.1 means its target for Promox VE 5.2 and its the first release (0.1) for that.

Development
+++++++++++

Linux
-----

Create a venv:

.. code:: bash
    $ sudo apt install virtualenv
    $ virtualenv -p /usr/bin/python3 venv
    $ source venv/bin/activate


.. code:: bash

    $ venv/bin/pip install -e ".[development,performance,uvloop]"

Now use ./venv/bin/pmxc instead of just plain `pmxc`

License
+++++++

MIT


Copyright
+++++++++

Copyright (c) 2018-2020 by René Jochum