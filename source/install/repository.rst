.. _repository:

================
Repository Setup
================

Distribution of the OneScape is via the operating system packages for the :ref:`supported platforms <platform>`. First, you need to configure your host to have access to dedicated authenticated customer repositories, then you can install or update OneScape packages.

Access to the software repositories with OneScape is authenticated by the customer's user name and token. Repository definitions below contain the placeholders ``${AUTH}`` where customer's credentials should be put. To simplify the process and to avoid dealing with the repository configurations manually, export your credentials following way before running the next commands.

.. prompt:: bash # auto

    # export AUTH='user:token'

CentOS and RHEL
===============

To add OneScape repository execute the following as root:

**CentOS/RHEL 7**

.. prompt:: bash # auto

    # cat << EOT > /etc/yum.repos.d/onescape.repo
    [onescape]
    name=onescape
    baseurl=https://${AUTH}@enterprise.opennebula.io/repo/onescape/5.10/CentOS/7/\$basearch
    enabled=1
    gpgkey=https://downloads.opennebula.io/repo/repo.key
    gpgcheck=1
    repo_gpgcheck=1
    EOT

**CentOS/RHEL 8**

.. prompt:: bash # auto

    # cat << EOT > /etc/yum.repos.d/onescape.repo
    [onescape]
    name=onescape
    baseurl=https://${AUTH}@enterprise.opennebula.io/repo/onescape/5.10/CentOS/8/\$basearch
    enabled=1
    gpgkey=https://downloads.opennebula.io/repo/repo.key
    gpgcheck=1
    repo_gpgcheck=1
    EOT

Debian and Ubuntu
=================

To add OneScape repository on Debian/Ubuntu execute as root:

.. prompt:: bash # auto

    # wget -q -O- https://downloads.opennebula.io/repo/repo.key | apt-key add -

**Debian 9**

.. prompt:: bash # auto

    # echo "deb https://${AUTH}@enterprise.opennebula.io/repo/onescape/5.10/Debian/9 stable onescape" > /etc/apt/sources.list.d/onescape.list

**Debian 10**

.. prompt:: bash # auto

    # echo "deb https://${AUTH}@enterprise.opennebula.io/repo/onescape/5.10/Debian/10 stable onescape" > /etc/apt/sources.list.d/onescape.list

**Ubuntu 16.04**

.. prompt:: bash # auto

    # echo "deb https://${AUTH}@enterprise.opennebula.io/repo/onescape/5.10/Ubuntu/16.04 stable onescape" > /etc/apt/sources.list.d/onescape.list

**Ubuntu 18.04**

.. prompt:: bash # auto

    # echo "deb https://${AUTH}@enterprise.opennebula.io/repo/onescape/5.10/Ubuntu/18.04 stable onescape" > /etc/apt/sources.list.d/onescape.list
