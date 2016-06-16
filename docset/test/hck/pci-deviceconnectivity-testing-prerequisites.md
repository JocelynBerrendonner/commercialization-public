---
author: joshbax-msft
title: PCI Device.Connectivity Testing Prerequisites
description: PCI Device.Connectivity Testing Prerequisites
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1dab8af5-7408-47dc-9e72-e821eaf67934
---

# PCI Device.Connectivity Testing Prerequisites


This section describes the tasks that you must complete before you test a PCI-based test device using the Windows Hardware Certification Kit (Windows HCK).

Before beginning testing, complete the following:

-   [Review the hardware requirements](#bkmk-hck-pci-hr).

-   [Review the software requirements](#bkmk-hck-pci-sr).

-   [Configure the test computer](#bkmk-hck-pci-tc).

## <a href="" id="bkmk-hck-pci-hr"></a>Hardware requirements


The following hardware is required for PCI device testing. You might need additional hardware if the test device includes additional features.

-   One test computer. The test computer must meet Windows HCK prerequisites. See [Windows HCK Prerequisites](windows-hck-prerequisites.md) for more information.

-   One test PCI device.

**Note**  
Additional test hardware will be required depending on that type of PCI device is being tested. For example, if the PCI test device is a graphic adapter, review the Device.Graphics test prerequisites.

 

## <a href="" id="bkmk-hck-pci-sr"></a>Software requirements


The following software is required to run the Device.Connectivity tests:

-   The latest Windows HCK filters or updates.

-   The drivers for the test device.

## <a href="" id="bkmk-hck-pci-tc"></a>Test computer configuration


To configure the test computer for PCI device testing:

1.  Install the appropriate Windows operating system on the test computer and then configure the computer for your test network (the network that contains the Windows HCK Studio and Windows HCK Controller.

2.  Install the test PCI device in the test computer.

3.  Install any required drivers for the test PCI device.

4.  Check that the test PCI device is detected by the test computer.

5.  Install the Windows HCK client application on the test computer.

6.  Using the Windows HCK Studio, create a machine pool, and move the test computer to that pool.

7.  Review the features detected by the Windows HCK Studio and review any additional prerequisites for the features detected for the test device.

Make sure that the test computer is in the ready state before you begin your testing. If a test requires parameters to be set before it is run, a dialog box will be displayed for that test. Review the specific test topic for more information.

Some Windows HCK tests require user intervention. When running tests for a submission, it is a best practice to run the automated tests in a block separately from manual tests. This prevents a manual test from interrupting completion of an automated test.

**Note**  
If a device supports multiple connectivity methods, complete a separate submission for each connectivity method.

 

 

 





