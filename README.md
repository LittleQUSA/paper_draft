# 在此处输入标题
#Paper Draft

This is a paper draft for the course CS6480, Advanced Networking at the University of Utah, Fall 2014.

##Motivation
Assuming this, we have some wearable equipment that is connected to a server, providing continuous and low-latency service for us. We may carry it around with us so the server must be accessiable through mobile network. Also, due to the requirement on low latency and the potential private data protection, we hope the server is as "close" to us as possible and as "private" as possible.

##Solution
Inspired by the [SMOG](http://dl.acm.org/citation.cfm?id=2501560.2501573) architecture and the [SMORE](https://www.flux.utah.edu/paper/cho-allthingscellular14) architecture, we propose our solution. In a mobile network, we deploy some SMORE nodes which are the same as the ones in the SMORE paper, offloading the wearable equipments' traffic to a nearby cloud server. In the cloud server, a user's requests are handled by applications running in a VM, which is owned by the user. When the user is moving, his equipment may access differnet eNodeBs, which makes the cloud he previously connected not the "closest" one (based on latency). In that case, we live migrate the user's personal VM to the nearest cloud, providing seamless service to the user.

## Implementation
We will implement the project on [PhantomNet](http://phantomnet.org). Possible tools may include Xen (especially the [live migration](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/5/html/Virtualization/chap-Virtualization-Xen_live_migration.html)), [DRBD](http://www.drbd.org/) (which is used to overcome Xen's limitation in having to use shared storage for VMs.) and so on.




