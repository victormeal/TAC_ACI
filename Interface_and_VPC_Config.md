# Interface and VPC Config

## Configure Interface Profile and Switch Profiles

### Steps:

#### Phase 1.

Create Interface Policy

Create AAEP

Create VLAN Pool

#### Phase 2.

Create Interface Policy Group

Create Physical Domain

#### Phase 3.

Create Interface Profile (Interface Selector)

#### Phase 4.

Create Switch Profile

#### Phase 5.

EGP > Physical DOmain association and Static Port

### GUI Steps

```
Fabric
	Access Policies
		Interfaces
			Leaf Interfaces
				Profiles <right click to create new one>
					Interface Selector
					Name
							Name
							Interface IDs
							Policy Group
				Policy Group
					Leaf Access Port <right click to create new one>
						Name
						Attached Entity Profile
						CDP Policy
						LLDP Policy
						
					VPC Interface  <right click to create new one>
						Name
						Attached Entity Profile
						CDP Policy
						LLDP Policy
						Port Channel Policy
		Switches
			Leaf Switches
				Profiles <right click to create new one>
					Name
					Leaf Selector
						Name
						Blocks
						Policy Group
					Interface Selector Profile
		Policies
			Switch
				Virtual Port Channel default
					<+>
					Name
					ID
					vPC domain policy: default
					Switch 1
					Switch 2
			Interface
				LLDP Interface <right click to create new one>
					Name
					Receive state
					Transmit state
				CDP Interface  <right click to create new one>
					Name
					Admin State
				Port Channel <right click to create new one>
					Name
					Mode
			Global
				Attachable Access Entity Profiles <right click to create new one>
					Name
					
		Pools
			VLAN <right click to create new one>
				Name
				Static Allocation
				Encap Blocks
					Range

		Physical and External Domain
			Physical Domains <right click to create new one>
				Name
				AAEP
				VLAN Pool
```
```
Tenants
	Tenant_Name
		Application Profiles
			Application_Profile_Name
				Application EPGs
					EPG_NAME
						Domains <right click to add physical domain association>
							Physical Domain Profile
						Static Ports <right click to Deploy Static EPG...>
							Path Type (port, PC, VPC)
							Node
							Path
							Port Encap
							Deployment Immediacy
							Mode (trunk, access)
```
