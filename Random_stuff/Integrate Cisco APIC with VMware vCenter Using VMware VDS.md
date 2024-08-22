# Integrate Cisco APIC with VMware vCenter Using VMware VDS

Fabric
	Access Policies
		Pools
			VLAN
				+ Create VLAN Pool
					Name: vCenter_VLANs
					Allocation Mode: Dynamic Allocation
					Encap Blocks: 100-199
					Role: External or On the wire encapsilations
Virtual Netwroking
	VMware
		+ Create vCenter Domain
			Virtual Switch Name: vCenter_VMM
			Virtual Switch: VMware vSphere Distributed Switch (default option)
			Associated Attachable Entity Profile: HOST_AAEP
			Port CHannel Mode: Static Channel - Mode On
			vSwitch Policy: LLDP
		vCenter_VMM
			Controllers
				+ Create vCenter Credential
					Name: Credential
					Username: <the one used to login to vcenter>
					Password: <the one used to login to vcenter>
				+ Create vCenter Controller
					Name: vCenter
					Hostname or IP address: 192.168.10.50
					DVS version: vCenter Default
					Data Center: DC <--- this is same name as the one in vcenter
					Associated credential: Credential

Tenant
	"Sales"
		Application Profiles
			"eCommerce_AP"
				Application EPGs
					"APP_EPG"
						+ Add VMM Domain Association
							VMM Domain Profile: vCenter_VMM
							Deploy Immediacy: On Demand
							Resolution Immediacy: Immediate

