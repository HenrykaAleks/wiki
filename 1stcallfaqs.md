<!-- TITLE: 5GinFIRE Open Call FAQs -->
<!-- SUBTITLE: FAQs -->

# 5GinFIRE Open Call FAQs

* **Is there any Available documentation?**

Please have a look at Deliverables at https://5ginfire.eu/deliverables/ and at this wiki http://wiki.5ginfire.eu

* **Is there any Testbed/Tools documentation?**

Please have a look at the following links:
1. Experimenter Tools (https://5ginfire.eu/facilities-2/)
2. The testbeds (http://wiki.5ginfire.eu/5GinFIREtestbeds)
 
* **Is the core network (i.e. Unified GW) provided as a functionality of the system and deployable through OSM?**

Yes the UGW is the core LTE network. 
So far the VNF UGW is not deployable via OSM MANO and B-COM is still working in the descriptors.
The PNF UGW is already deployed at Bristol site.



* **Is it a hard limitation "Before  awarding any grants to a third party, it will  be  checked whether the  third party is a legal entity with a history of at least three years of commercial operations, and has not been declared insolvent." ?**

YES

* **Which OSM version should be considered, TWO or THREE or FOUR?**

Current infrastructure is based on OSM Release FOUR, which is the version of OSM considered in production state. Nevertheless, OSM Release TWO is still supported. This enables the coexistence of network services, and VxFs developed under both versions of OSM (due to different design criteria, Releases FOUR and TWO of OSM are not fully compatible), as well as the re-creation of experiments carried out during the second year of 5GinFIRE (when only Release TWO was available). 


* **How is the experiment lifecycle working? Will the experimenter be allowed to access directly the OSM launchpad/APIs, or the only interaction allowed is via the 5GinFIRE portal?**

Please check the wiki http://wiki.5ginfire.eu/#the-5-gin-fire-architecture-technologies-services-and-testbeds. Normally the access will be only through the portal.

* **Considering that we would like to instantiate multiple slices, are we allowed to execute them in parallel?**

In 5GinFIRE,*experiment* is the abstraction that is available to experimenters for deployment. The 5GinFIRE MANO platform supports the deployment of simultaneous experiments, being their isolation guaranteed through the Virtualized Infrastructure Managers (VIMs).  

* **Is there a multi-site federated infrastructure, or the different testbeds are seen as individual sites? In the last case, where should be specified the site for deployment?**

The technical solution adopted by 5GinFIRE for the MANO stack considers the utilization of a single orchestration domain, where an NFV orchestrator, implemented with Open Source MANO (OSM), manages and coordinates the creation of network services, being a network service generally defined as a composition of Virtualized Network Functions (VNFs) and/or Virtualized Vertical Functions (VVFs), generally referred to as VxFs. Each of these VxFs may be in turn deployed at any of the NFV infrastructures (NFVI) made available by 5GinFIRE partners. At the time of writing, the MANO platform supports multi-site experimentation activities across different vertical domains:

1)	An infrastructure at the global 5G Telefonica Open Innovation Laboratory (5TONIC) [5], made available by TID and UC3M, to support experimentation with NFV functions and services.
2)	An experimentation facility located at ITAv, providing access to an automotive testbed in the city of Aveiro (Portugal).
3)	An infrastructure made available by UNIVBRIS, supporting experimentation activities over a smart city environment in the city of Bristol (UK).
4)	An experimentation facility at UFU, located at Uberlândia (Brazil), enabling trialling with 5G applications with a particular consideration on the edge network resources.
5)	An infrastructure provided by the NITOS testbed, i.e., 5GVINO, hosted by the University of Thessaly (Greece), which provides access to programmable resources for wireless networking, SDN and cloud computing facilities.
6)	An eHealth experimental vertical facility, eHealth5G, hosted by the Poznan Supercomputing and Networking Center (Poland); this facility supports experimentation in the area of telemedicine and eHealth, offering access to: realistic eHealth equipment; a small Edge Cloud, close to eHealth devices; and a core cloud accessible via MPLS/Optical service provider network.
7)	A reconfigurable radio testbed at Trinity College Dublin (Ireland), Iris, supporting radio hardware, cloud-RAN, NFV, and SDN technologies. This testbed has been extended and made available for experimentation activities in 5GinFIRE. We refer to this testbed extension as WINS_5G.

Each site running an experimental infrastructure deploys a Virtualized Infrastructure Manager (VIM), compliant with the OSM software stack. The different sites providing the NFV infrastructures are interconnected, and the experimenter can request, when defining an experiment through the 5GinFIRE portal, which experimental infrastructure should support the execution of each VxF. 

* **Is inter-VNF communication based on classical virtual networking like in OpenStack?**
At this moment, all the sites that provide an experimental infrastructure are using a Virtualized Infrastructure Manager (VIM) based on OpenStack. Virtual networking for VNF communications at each site is enabled by its corresponding OpenStack VIM. 

* **Is OpenStack the VIM/NFVI used in the sites? Which version specifically?**

 The selection of the VIM software is independently taken by each site, with the only requirement to be compliant with OSM Release FOUR. Most sites use an OpenStack VIM, under different versions and configurations.
 
* **Are we allowed to upload specific images on the VIM/NFVI while implementing VNFs?**

Uploading VM images on the VIMs is part of the development/validation process of VNFs, so this will be allowed upon request. 

* **Will the experimenter get access (i.e. SSH) to the deployed instances? If yes, how? Via VPN or public IPs?** 

The 5GinFIRE platform support the controlled access of experimenters to their reources under experimentation (i.e., VNFs). This is done through a VPN access to the platform, and via *ssh* to the VNFs. See [here](http://wiki.5ginfire.eu/tutorials/guide-external-access-experimenters) for more details.
 
* **In case of VPN, are there some firewall rules?**

Yes, firewall rules are configured to control the access to infrastucture resources and deployed VNFs.

* **Will you accept proposals with potential modifications to the OSM tool? If yes, which version should be considered?**

Yes, these acre considered in specific categories of the Open Calls.

* **Will you accept proposals with potential modifications/extensions to the 5GinFIRE portal?**

Yes, these acre considered in specific categories of the Open Calls.

* **How are those extensions supposed to be integrated? Should we consider potential modifications to the components, or should we only use APIs (hopefully with SDKs you may provide)?** 

They can be either services or APIs usage, APIs extensions or modifications. Proposers are free to define

* **In case of extensions based on APIs, are you providing an API description which we could consider for our initial solution design? Please let us know also about any restrictions due to any RBAC mechanism you utilise.** 

    * Regarding the Portal there is an API. Please check the http://wiki.5ginfire.eu/portalarchitecturedesign/portal-api section
    * Regarding OSM there are the ETSI NFV APIs specified and the correspponding OSM version to support

* **Currently we have only noticed that the experiment lifecycle mainly deals with category 1 types of experiment, therefore it is not clear how those potential extensions could be realised and be deployed on demand on top of your platform.**

The extensions can be deployed as services or they can reuse existing APIs (Portal, OSM). Proposers, though, are free to define the deployment they need

* **Will some support be provided about the description files definition?**

Please, check this Wiki. The descriptors are being standardized in format and packaging by ETSI specifications. While technical advice can be provided by 5GinFIRE partners, experimenters/developers are responsible for the proper implementation of their VNFs.

* **Is a successful applicant expected to attend 5GINFIRE review meetings and / or onsite visits (e.g. at the Testbed sites, for integration)?**

Beside review meeting, we would like to invite all successful proposers to a kick-off meeting in May 2018 as well as tutorial session at EUCNC conference (to be confirmed) if appropriate. Reserving some additional resources for additional travels, e.g. to Testbed sites seems reasonable.

* **The budget for the open-call allows the new partners to buy equipment?**

In principle we do not specify a limit for equipment purchases.  This means that this could be done within reasonable limits. The spirit of the call is to put the money into work and not into infrastructure or other equipment.
The main point is whether the purchase is duly justified and that the rest of the budget request is leaving sufficient room for executing the work or operation (in case of 2b).

