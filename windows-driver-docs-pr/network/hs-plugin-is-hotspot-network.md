---
title: HS_PLUGIN_IS_HOTSPOT_NETWORK function
author: windows-driver-content
description: The HS\_PLUGIN\_IS\_HOTSPOT\_NETWORK function is called by the host to determine if a specified network is a hotspot network.
ms.assetid: 24a26ee0-9eb1-49fa-95da-40315a4aab3a
keywords: 
- typedef DWORD (WINAPI HS_PLUGIN_IS_HOTSPOT_NETWORK) function Network Drivers Starting with Windows Vista
ms.author: windowsdriverdev
ms.date: 07/31/2017 
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# HS\_PLUGIN\_IS\_HOTSPOT\_NETWORK function

[!include[Wi-Fi Hotspot Offloading deprecation](wi-fi-hotspot-offloading-deprecation.md)]


The **HS\_PLUGIN\_IS\_HOTSPOT\_NETWORK** function is called by the host to determine if a specified network is a hotspot network.

Syntax
------

```ManagedCPlusPlus
 typedef DWORD (WINAPI *HS_PLUGIN_IS_HOTSPOT_NETWORK)(
  _In_      HS_NETWORK_IDENTITY *pNetworkIdentity,
  _Out_     eHS_NETWORK_STATE   *pNetworkState,
  _Out_opt_ HS_NETWORK_PROFILE  *pNetworkProfile
);
```

Parameters
----------

*\*pNetworkIdentity* \[in\]  
Pointer to the [**HS\_NETWORK\_IDENTITY**](hs-network-identity.md) structure for the network from which the device is to be disconnected.

*\*pNetworkState* \[out\]  
An [**eHS\_NETWORK\_STATE**](ehs-network-state.md) enumeration value that indicates the type of network.

*\*pNetworkProfile* \[out, optional\]  
Pointer to the [**HS\_NETWORK\_PROFILE**](hs-network-profile.md) structure for the network.

Return value
------------

This function is called by the host to communicate with the plugin and does not return a value.

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version</p></td>
<td><p>Windows 10 Mobile</p></td>
</tr>
<tr class="even">
<td><p>Header</p></td>
<td>Hotspotoffloadplugin.h (include Hotspotoffloadplugin.h)</td>
</tr>
</tbody>
</table>

## See also


[**HS\_NETWORK\_IDENTITY**](hs-network-identity.md)

[**eHS\_NETWORK\_STATE**](ehs-network-state.md)

[**HS\_NETWORK\_PROFILE**](hs-network-profile.md)

 

 


--------------------
[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bnetvista\netvista%5D:%20HS_PLUGIN_IS_HOTSPOT_NETWORK%20function%20%20RELEASE:%20%287/31/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")


