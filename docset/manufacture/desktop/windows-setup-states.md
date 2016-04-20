---
author: Justinha
Description: Windows Setup States
MS-HAID: 'p\_adk\_online.windows\_setup\_states'
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Windows Setup States
---

# Windows Setup States


There are several states assigned to a Windows® image during installation. This state information can be used to detect automatically the different states and stages of Windows Setup.

## <span id="WindowsSetupStates"></span><span id="windowssetupstates"></span><span id="WINDOWSSETUPSTATES"></span>Windows Setup State Information


The Windows image state is stored in two locations, in the registry and in a file.

-   In the registry:

    KEY: **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\State**

    TYPE: REG\_SZ

    VALUE: *StateName*

-   In a file:

    FILE: %WINDIR%\\Setup\\State\\State.ini

    SECTION: \[State\]

    VALUE: *StateName*

The following table describes the values that exist for *StateName*.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">State name</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IMAGE_STATE_COMPLETE</p></td>
<td align="left"><p>The image has successfully been installed. The <strong>specialize</strong> and <strong>oobeSystem</strong> configuration passes are complete. This image is not deployable to a computer that has a different hardware configuration because it is now hardware-dependent. To deploy this image to a computer that has a different hardware configuration, you must run <strong>sysprep /generalize</strong>.</p></td>
</tr>
<tr class="even">
<td align="left"><p>IMAGE_STATE _UNDEPLOYABLE</p></td>
<td align="left"><p>This is the default state for an image in a given phase of Windows Setup that is not yet complete. If a process queries the IMAGE_STATE value and IMG_UNDEPLOYABLE is returned, the image is in one of the following states:</p>
<ul>
<li><p>Setup is currently running and has not fully completed the phase. Once a given phase is complete, the IMAGE_STATE will be set to an appropriate completion value.</p></li>
<li><p>If queried online when Setup is not running, there was a failure when completing a Setup phase. This image must be reinstalled.</p></li>
<li><p>If queried offline, the image did not finish a phase and will never be deployable.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>IMAGE_STATE_GENERALIZE_RESEAL_TO_OOBE</p></td>
<td align="left"><p>The image has successfully completed the <strong>generalize</strong> configuration pass and will continue into <strong>OOBEsystem</strong> configuration pass when Setup is initiated.</p></td>
</tr>
<tr class="even">
<td align="left"><p>IMAGE_STATE_GENERALIZE_RESEAL_TO_AUDIT</p></td>
<td align="left"><p>The image has successfully completed the <strong>generalize</strong> configuration pass and will continue into audit mode when Setup is initiated.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IMAGE_STATE_SPECIALIZE_RESEAL_TO_OOBE</p></td>
<td align="left"><p>The image has successfully completed the <strong>specialize</strong> pass and will continue into <strong>OOBEsystem</strong> configuration pass when Setup is initiated.</p></td>
</tr>
<tr class="even">
<td align="left"><p>IMAGE_STATE_SPECIALIZE_RESEAL_TO_AUDIT</p></td>
<td align="left"><p>The image has successfully completed the <strong>specialize</strong> configuration pass and will continue into audit mode when Setup is initiated.</p></td>
</tr>
</tbody>
</table>

 

The following examples show how to access state information.

-   To access state information from the registry:

    ``` syntax
    C:\>reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\State /v Imag
    eState

    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\State
        ImageState    REG_SZ    IMAGE_STATE_SPECIALIZE_RESEAL_TO_OOBE
    ```

-   To access state information from a file:

    ``` syntax
    C:\>type %windir%\Setup\State\State.ini
    [State]
    ImageState="IMAGE_STATE_SPECIALIZE_RESEAL_TO_OOBE"
    ```

## <span id="related_topics"></span>Related topics


[Windows Setup Command-Line Options](windows-setup-command-line-options.md)

[Windows Setup Edition Configuration and Product ID Files (EI.cfg and PID.txt)](windows-setup-edition-configuration-and-product-id-files--eicfg-and-pidtxt.md)

[Windows Setup Log Files and Event Logs](windows-setup-log-files-and-event-logs.md)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_adk_online\p_adk_online%5D:%20Windows%20Setup%20States%20%20RELEASE:%20%284/11/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



