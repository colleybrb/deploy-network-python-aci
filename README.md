# Cisco-ACI-Cobra

This project deploys configs from .csv to ACI I used a blend of ACI object inspector, webarya and cobra to deploy network infrastructure. It's not a 100% solution, but you should be able to launch from here in any direction you need. 

Ensure you load cobra from your APIC.

### What it does
* Loads csv
* Checks if config from csv exists
    * Yes: pass
    * No: would you like to see similar items?
        * No: pass
        * Yes: prints all similar items e.g. epg's
        * Would you like to create config
                * No: pass
                * Yes: invoke function that creates config from csv

### Typical Output 
```
enter password: ········
Found: uni/infra/vlanns-[Daniel_Vlan_Pool]-static/fvnsVlanInstP Found: uni/phys-Daniel_Dom/physDomP Found: uni/infra/attentp-PITC_AEP/infraAttEntityP Found: uni/tn-Daniel/fvTenant Found: uni/tn-Daniel/ctx-Daniel/fvCtx Found: uni/infra/nprof-L1001-1002/infraNodeP Found: uni/tn-Daniel/ap-AP/fvAp Found: uni/tn-Daniel/BD-BD-1161/fvBD Found: uni/tn-Daniel/BD-BD-1161/fvSubnet Found: uni/tn-Daniel/ap-AP/epg-EPG-1161/rsdomAtt-[uni/phys-Daniel_Dom]/fvRsDomAtt Found: uni/infra/accportprof-L1001-1002/infraAccPortP Found: uni/tn-Daniel/ap-AP/epg-EPG-1161/rspathAtt-[topology/pod-1/protpaths-1001-1002/pathep-[Test_PO1]]/fvRsPathAtt Found: uni/tn-Daniel/out-L3-Out-Daniel/l3extOut Found: uni/infra/vlanns-[Tim_Vlan]-static/fvnsVlanInstP Found: uni/phys-Tim_Dom/physDomP Found: uni/infra/attentp-PITC_AEP/infraAttEntityP Found: uni/tn-Tim/fvTenant Missing: uni/tn-Tim/ctx-Daniel/fvCtxWould you like to see all classes relating(y or n): n
Would you like to create missing item(y or n): y
creating fvCtx: <?xml version="1.0" encoding="UTF-8"?> <fvTenant name='Daniel' status='created,modified'><fvCtx annotation='' bdEnforcedEnable='no' descr='' ipDataPlaneLearning='enabled' knwMcastAct='permit' name='Daniel' nameAlias='' ownerKey='' ownerTag='' pcEnfDir='ingress' pcEnfPref='enforced' status='created,modified' userdom=':all:' vrfIndex='0'><leakRoutes annotation='' descr='' name='' nameAlias='' status='created,modified' userdom=':all:'></leakRoutes><fvRsVrfValidationPol annotation='' status='created,modified' tnL3extVrfValidationPolName='' userdom='all'></fvRsVrfValidationPol><vzAny annotation='' descr='' matchT='AtleastOne' name='' nameAlias='' prefGrMemb='disabled' status='created,modified' userdom='all'><vzRsAnyToProv annotation='' intent='install' matchT='AtleastOne' prio='unspecified' status='created,modified' tnVzBrCPName='permit-any' userdom=':all:'></vzRsAnyToProv><vzRsAnyToCons annotation='' intent='install' prio='unspecified' status='created,modified' tnVzBrCPName='permit-any' userdom=':all:'></vzRsAnyToCons></vzAny><fvRsOspfCtxPol annotation='' status='created,modified' tnOspfCtxPolName='' userdom='all'></fvRsOspfCtxPol><fvRsCtxToEpRet annotation='' status='created,modified' tnFvEpRetPolName='' userdom='all'></fvRsCtxToEpRet><fvRsCtxToExtRouteTagPol annotation='' status='created,modified' tnL3extRouteTagPolName='' userdom='all'></fvRsCtxToExtRouteTagPol><fvRsBgpCtxPol annotation='' status='created,modified' tnBgpCtxPolName='' userdom='all'></fvRsBgpCtxPol></fvCtx></fvTenant> Missing: uni/infra/nprof-L1001-1003/infraNodePWould you like to see all classes relating(y or n): n
Would you like to create missing item(y or n): n
Found: uni/tn-Tim/ap-AP/fvAp Found: uni/tn-Daniel/BD-BD-1162/fvBD Missing: uni/tn-Tim/BD-BD-1162/fvSubnetWould you like to see all classes relating(y or n): y
Found related: uni/tn-Austin-N/BD-BD-1012/subnet-[10.2.2.1/24] uni/tn-Test/BD-BD-1003/subnet-[10.1.3.1/24] uni/tn-Mirwais/BD-BD-1031/subnet-[10.4.1.1/24] uni/tn-Steve/BD-BD-1071/subnet-[10.8.1.1/24] uni/tn-Steve/BD-BD-1072/subnet-[10.8.2.1/24] uni/tn-Test/BD-BD-1004/subnet-[10.1.4.1/24] uni/tn-Mirwais/BD-BD-1032/subnet-[10.4.2.1/24] uni/tn-Test/BD-BD-1001/subnet-[10.1.1.1/24] uni/tn-Stan_The_Man/BD-BD-1082/subnet-[10.9.2.1/24] uni/tn-Austin-N/BD-BD-1011/subnet-[10.2.1.1/24] uni/tn-Stan_The_Man/BD-BD-1081/subnet-[10.9.1.1/24] uni/tn-Test/BD-BD-1002/subnet-[10.1.2.1/24] uni/tn-Daniel/BD-BD-1161/subnet-[10.17.1.1/24] uni/tn-Daniel/BD-BD-1162/subnet-[10.17.2.1/24]Would you like to create missing item(y or n): y
creating fvSubnet: <?xml version="1.0" encoding="UTF-8"?> <fvBD name='BD-1162' status='created,modified'><fvSubnet annotation='' ctrl='' descr='' ip='10.17.1.1/25' ipDPLearning='enabled' name='' nameAlias='' preferred='no' status='created,modified' userdom=':all:' virtual='no'></fvSubnet></fvBD> Missing: uni/tn-Tim/ap-AP/epg-EPG-1162/rsdomAtt-[uni/phys-Tim_Dom]/fvRsDomAttWould you like to see all classes relating(y or n): n
Would you like to create missing item(y or n): y
creating fvRsDomAtt: <?xml version="1.0" encoding="UTF-8"?> <fvAEPg name='EPG-1162' status='created,modified'><fvRsDomAtt annotation='' bindingType='none' classPref='encap' customEpgName='' delimiter='' encap='unknown' encapMode='auto' epgCos='Cos0' epgCosPref='disabled' instrImedcy='lazy' lagPolicyName='' netflowDir='both' netflowPref='disabled' numPorts='0' portAllocation='none' primaryEncap='unknown' primaryEncapInner='unknown' resImedcy='immediate' secondaryEncapInner='unknown' status='created,modified' switchingMode='native' tDn='uni/phys-Tim_Dom' untagged='no' userdom=':all:' vnetOnly='no'></fvRsDomAtt></fvAEPg> Missing: uni/infra/accportprof-L1001-1003/infraAccPortPWould you like to see all classes relating(y or n): n
Would you like to create missing item(y or n): y
creating infraAccPortP: Create node profile Missing: uni/tn-Tim/ap-AP/epg-EPG-1162/rspathAtt-[topology/pod-1/protpaths-1001-1003/pathep-[Test_PO2]]/fvRsPathAttWould you like to see all classes relating(y or n): y
Found related: uni/tn-Stan_The_Man/ap-AP/epg-EPG-1081/rspathAtt-[topology/pod-1/protpaths-1001-1002/pathep-[Test_PO1]] uni/tn-Mirwais/ap-AP/epg-EPG-1031/rspathAtt-[topology/pod-1/protpaths-1001-1002/pathep-[Test_PO1]] uni/tn-Test/ap-AP/epg-EPG-1004/rspathAtt-[topology/pod-1/protpaths-1017-1018/pathep-[Test_PO2]] uni/tn-Austin-N/ap-Austin-AP/epg-EPG-1011/rspathAtt-[topology/pod-1/protpaths-1001-1002/pathep-[Test_PO1]] uni/tn-Steve/ap-AP/epg-EPG-1072/rspathAtt-[topology/pod-1/protpaths-1017-1018/pathep-[Test_PO2]] uni/tn-Mirwais/ap-AP/epg-EPG-1032/rspathAtt-[topology/pod-1/protpaths-1017-1018/pathep-[Test_PO2]] uni/tn-Austin-N/ap-Austin-AP/epg-EPG-1012/rspathAtt-[topology/pod-1/protpaths-1017-1018/pathep-[Test_PO2]] uni/tn-Test/ap-AP/epg-EPG-1001/rspathAtt-[topology/pod-1/paths-1001/pathep-[eth1/15]] uni/tn-Stan_The_Man/ap-AP/epg-EPG-1082/rspathAtt-[topology/pod-1/protpaths-1017-1018/pathep-[Test_PO2]] uni/tn-Test/ap-AP/epg-EPG-1002/rspathAtt-[topology/pod-1/protpaths-1001-1002/pathep-[Test_PO1]] uni/tn-Test/ap-AP/epg-EPG-1003/rspathAtt-[topology/pod-1/paths-1017/pathep-[PC-12]] uni/tn-Steve/ap-AP/epg-EPG-1071/rspathAtt-[topology/pod-1/protpaths-1001-1002/pathep-[Test_PO1]] uni/tn-Daniel/ap-AP/epg-EPG-1161/rspathAtt-[topology/pod-1/protpaths-1001-1002/pathep-[Test_PO1]] uni/tn-Daniel/ap-AP/epg-EPG-1162/rspathAtt-[topology/pod-1/protpaths-1017-1018/pathep-[Test_PO2]]Would you like to create missing item(y or n): n
Missing: uni/tn-Tim/out-L3-tem/l3extOutWould you like to see all classes relating(y or n): n
Would you like to create missing item(y or n): n
```
### Things it doesn't do
* Check your type or naming convention
* Have a rollback option
* Build L3 outs (even though you might see some references to it), you should only need one and this can crash your enviroment so, probably best not deployed programatically.
 
This notebook has notes from messing around with the objects, and should be useful for you. It also still has bugs, but the team has decided to use postman, and I don't fight upstream too long.

***If you have issues and need help reach out.***
