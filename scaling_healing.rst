=======
License
=======

Functest Docs are licensed under a Creative Commons Attribution 4.0
International License.
You should have received a copy of the license along with this.
If not, see <http://creativecommons.org/licenses/by/4.0/>.


====================
About NFV-IFA008
====================

NFV-IFA008 describes the interaction between VNFM and EM/VNF. This documents 
concentrates on interaction of VNFM with VNF throught Ve-Vnfm reference point. 
This clause defines the interfaces exposed by the VNF towards the VNFM over 
the Ve-Vnfm reference point. This interface allows the VNF/EM to invoke VNF 
lifecycle management operations towards the VNFM. 


===============================
Type of Classification Metrics
==============================

Broadly speaking there can be two major classes of Classification Metrics.

1. Functional Metrics

These deal with the function aspect of VNFs. This could include metrics such as
Scaling or Healing aspects of VNFs and so on.

2. Structural Metrics

These deal the structural aspects i.e. the build aspects of VNFs. This could
include metrics such as presence(or absence) of a database in a VNF and so on.


==================
Proposed Metrics
=================

Two very important Functional metrics arise based on the official ETSI 
documentation.

    * Support for Scaling of VNF
        ** Support for Manual scaling - Whether there is support for manual 
           scaling. Manual scaling could range from simple scale in/out to 
           policy based scaling system
        ** Support for Scaling Policy System - An important sub metric would 
           be policy based scaling system. Essentially this would mean operator
           can define scaling magnitudes as policy which would be then be 
           triggered manually.
 
    * Support for Auto scaling - Auto scaling is proactive/reactive 
      approach to scaling. The scaling can be Alarm/Monitoring Triggers 
      whereby the alarm is triggered after a certain threshold is reached.
        ** Support for Reactive/Proactive Autoscaling - This is an important 
        metric to support autoscaling. This essentially means whether the 
        architecture allows scaling the vnf proactively(for instance if a 
        certain alarm is raised before a certain quota of resouces is reached)
        or reactively(for instance if the certain alarm is raised after a 
        certain quota of resource usage is reached).
    
    * Support for Healing VNF - According to official ETSI definition this 
      operation is used to request appropriate correction actions in reaction 
      to a failure. This includes support for policy/rule based fault 
      management system.

    * Support for creation of Deployment Flavor of VNF - Support for creation
      of deployment flavor of VNF is a major requirement of various telco 
      providers. It is not possible to add VDU details to VNFD. Hence this is
      generally carried out using addition of new field to VNFD Templates.


===========
Case Study
===========

In the case study section we select two frameworks which aspire to be ETSI NFV
compliant Management and Orchestration (MANO) Framework.


    * Tacker - Openstack
        ** Tacker is an official OpenStack project building a  ETSI MANO / IFA 
           based general purpose NFV Orchestrator + VNF Manager for OpenStack. 
        ** Tacker currently has supports alarm/monitoring trigger based 
           auto-scaling and policy based scaling for the use cases(vnfs). 
        ** Currently there is no support for proactive/reactive scaling 
           specification.
        ** Tacker allows creation of custom deployment flavors by a adding a
           new field to VNFD namely “host”.

    * OpenBaton
        ** Similar to Tacker, OpenBaton is an ETSI NFV compliant Management and
           Orchestration Framework.
        ** OpenBaton supports manual and autoscaling features. The autoscaling
           engine is written in java and unlike OpenStack runs as an external
           component and communicates with the NFVO via OpenBaton SDK.
        ** It supports field for both proactive and reactive approach to
           autoscaling.
        ** OpenBaton takes support of Openstack deployment for
           creation of custom deployment flavor.
