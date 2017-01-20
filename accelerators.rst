=======
License
=======

Functest Docs are licensed under a Creative Commons Attribution 4.0
International License.
You should have received a copy of the license along with this.
If not, see <http://creativecommons.org/licenses/by/4.0/>.



===============================
Leveraging Accelerators in VNF
===============================

ETSI GS NFV-IFA 002 talks about design patterns that can be used to help
a VNF leverage an accelerator. It aims to decouple the design of VNF from
the accelearator involved. VNF can probably have constraint with regards to
certain power limitations, CPU core count and so on. Use of accelerator can
help meet these requirements potentially. Any VNF deployed in an NFVI 
environment can suffer performance penalty. Technologies such as Accelerators
can potentially offset the performance cost.

 
==================
Proposed Metrics
=================

The official ETSI documentation talks about two broad classes of VNFs namely

	* Implementation independent executable VNFC
		** These Can leverage a known set of accelerator implementations both in
		   hardware and in software.
		** If a new hardware becomes available the VNF provider needs to change
		   the VNFC and VNFD.
	* Implementation independent VNF 
		** These VNFs make no assumption whatsoever on the underlying NFVI.
		** Should a new hardware become available on the market, the operator will
		   update its NFVI to allow the VNF to make use of the new hardware.


========================
Performance Bottlenecks
========================

	* Driver Level Bottleneck - This pertains to bottleneck corresponding to NFVI
	  Platform
	* Virtual Switch Bottleneck - This pertains to bottleneck corresponding to 
	  Virtual Switch running in Hypervisor
	* Communication Bottleneck - Corresponds to bottlenecks pertaining to
	  communication between Host and Guest OS.
	* Virtual Machine Bottleneck - Delays due to virtualization


======================
Case Study
======================

6WindGate is a properity software for packet processing in tier 1 networks.
