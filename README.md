# contrailvm

A Packer project for building a Contrail VM to build and control and compute nodes for an OpenStack and Contrail lab or demo environment.


> **Note:**

 - This project is experimental.  Please use this at your own risk on isolated non-routable lab networks (per your discretion and skill set).

# Description

The ultimate goal is to be able to quickly install a fresh VM from [HashiCorp Atlas](https://atlas.hashicorp.com/) to build a Contrail and OpenStack lab or demo environment.  Once you've installed the VM, you can:

 - build base Linux installs that are ready for Contrail, using [PXE](http://en.wikipedia.org/wiki/Preboot_Execution_Environment) with Preseed or Kickstart
 - install and Contrail (which includes OpenStack)
 - demo/lab/evaulate/learn about Contrail

This VM runs all OpenStack and Contrail components but the Contrail Compute nodes (also OpenStack compute) and Controller (resides on a compute node by default)

# Target Environment

I am using [Shuttle DS81](http://us.shuttle.com/barebone/Models/DS81.html) for the Control and Compute [nodes](http://www.juniper.net/techpubs/en_US/contrail1.0/topics/concept/components-vnc.html) for demos.  If you were to a) want multiple interfaces, b) server hardware, and more advanced support, you'll need to modify the Packer configuration, as well as the [Chef cookbook](https://github.com/JNPRAutomate/contrailvm-cookbook) to suit your needs.  Feel free to open issues for feature requests on either project.

# Versions

- Contrail: only supporting 2.0+ in the cookbook at this time

- OpenStack: Havana and Icehouse, per Contrail support for each OS

- Host Linux OS:
 - CentOS 6.5 - * only supported OS for now
 - Ubuntu 12.04.4 LTS - next on the list
 - RHEL 7.0 - next
 - Ubuntu 14.04.1 LTS - last

# Quick FAQ

1. Q: When will you support X feature? A: Open a GitHub issue, and I will do my best to take a look at it.
2. Q: Why not just use the Bento VMs and run the cookbook against those?  A: There are some minor tweaks, like downrev minor Linux versions, the use of a non-NAT physical interface for communication with compute nodes, etc.
3. Q: I'm building my own VMs.  Where can I find CentOS 6.5? A: [vault.centos.org](http://vault.centos.org/6.5/isos/x86_64/)
4. Q: What about an exit node from the virtual to physical network A: looking into that...

# More information on Contrail

- [Contrail Documentation](http://www.juniper.net/techpubs/en_US/release-independent/contrail/information-products/pathway-pages/index.html)
- [Contrail TechWiki](https://techwiki.juniper.net/Documentation/Contrail)
- [OpenContrail.org Mailing Lists](http://lists.opencontrail.org/mailman/listinfo)
- [OpenContrail on Github](https://github.com/Juniper?query=contrail)
- [OpenContrail Twitter](https://twitter.com/OpenContrail)
