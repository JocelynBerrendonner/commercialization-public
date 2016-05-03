---
author: joshbax-msft
title: Troubleshooting Device.Input Testing
description: Troubleshooting Device.Input Testing
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d05b5b7d-0830-4249-ba44-a288b81267e9
---

# Troubleshooting Device.Input Testing


To troubleshoot issues that occur with Device.input tests, follow these steps:

1.  Review [Troubleshooting Windows HCK Test Failures](troubleshooting-windows-hck-test-failures.md).

2.  Review one of the following topics, depending on the type of input device that you are testing:

    -   [Fingerprint Reader Testing Prerequisites](fingerprint-reader-testing-prerequisites.md)

    -   [Game Controller Testing Prerequisites](game-controller-testing-prerequisites.md)

    -   [Keyboard Testing Prerequisites](keyboard-testing-prerequisites.md)

    -   [Mouse or other Pointing Device Testing Prerequisites](mouse-or-other-pointing-device-testing-prerequisites.md)

    -   [Sensor Device Testing Prerequisites](sensor-device-testing-prerequisites.md)

    -   [Smart Card Reader Testing Prerequisites](smart-card-reader-testing-prerequisites.md)

3.  Review the [Windows HCK release notes](http://go.microsoft.com/fwlink/p/?linkid=236110) for current test issues.

4.  For a test failure, look for usable information in the Windows HCK Studio test log. If you find usable information, resolve the issue and rerun the test.

### Specific information about keyboard tests

The Device.Input test category does not include specific keyboard tests. However, there are tests in the Device.Fundamentals category that apply to keyboards. For more information, see [Device.Fundamentals Testing](devicefundamentals-testing.md).

### Specific information about mouse or other pointing device tests

The Device.Input test category does not include specific mouse tests. However, the Device.Fundamentals category includes tests that apply to mice. For more information, see [Device.Fundamentals Testing](devicefundamentals-testing.md).

### Specific information about sensor device tests

Currently, known sensor test issues are grouped into the following categories:

-   Test initialization failures

-   Operating system issues

-   Permissions issues

**Test initialization failures**

When the sensor tests start on a test computer, they perform several tests to verify that the environment can be used for testing. If you receive errors that have a TUID of A012D6BB-36BB-4088-AF3F-1BE3C5607928, verify the following:

-   The test computer must be running Windows 8 or Windows 7.

-   The test computer must currently have your test sensor device installed and the device must be operational.

-   The test sensor device must appear as a sensor device in the **Location and Other Sensors** Control Panel.

**Operating system issues**

The sensor tests are only valid on Windows 8 and Windows 7. The tests are not supported on any other version of Windows.

**Permissions issues**

The user who is logged into the client computer must have permissions to access the sensor device for some of the sensor logo tests. To check permissions, follow these steps:

1.  Open the **Location and Other Sensors** Control Panel.

2.  Grant all users access to the sensor device that is being tested. To do this, follow these steps:

    1.  In the **Location and Other Sensors** Control Panel, select the check box next to the sensor device that is being tested.

    2.  Click **Apply**.

**Note**  
You must have administrator permissions on the test system to change the permissions for the sensor test device.

 

## Related topics


[Device.Input Testing](deviceinput-testing.md)

[Troubleshooting Windows HCK](troubleshooting-windows-hck.md)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_hck\p_hck%5D:%20Troubleshooting%20Device.Input%20Testing%20%20RELEASE:%20%284/27/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")




