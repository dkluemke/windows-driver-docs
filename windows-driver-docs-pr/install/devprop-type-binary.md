---
title: DEVPROP_TYPE_BINARY
description: In Windows Vista and later versions of Windows, the DEVPROP_TYPE_BINARY identifier represents the base-data-type identifier that indicates that the data type is an array of BYTE-typed unsigned values.
ms.assetid: ee20f0f1-fff9-41a9-a880-f8f577320e41
keywords: ["DEVPROP_TYPE_BINARY Device and Driver Installation"]
topic_type:
- apiref
api_name:
- DEVPROP_TYPE_BINARY
api_location:
- Devpropdef.h
api_type:
- HeaderDef
---

# DEVPROP_TYPE_BINARY


In Windows Vista and later versions of Windows, the DEVPROP_TYPE_BINARY identifier represents the base-data-type identifier that indicates that the data type is an array of BYTE-typed unsigned values.

Remarks
-------

The DEVPROP_TYPE_BINARY property type cannot be combined with the property-data-type modifiers.

### Setting a Property of this Type

To set a property whose base data type is DEVPROP_TYPE_BINARY, call the corresponding SetupDiSet*Xxx* property function and set the function input parameters as follows:

-   Set the *PropertyType* parameter to DEVPROP_TYPE_BINARY, set the *PropertyBuffer* parameter to a pointer to a buffer that contains an array of BYTE value, and set the *PropertyBufferSize* parameter to the size, in bytes, of the buffer.

-   Set the remaining function parameters as appropriate to set the property.

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>Header</p></td>
<td align="left">Devpropdef.h (include Devpropdef.h)</td>
</tr>
</tbody>
</table>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bdevinst\devinst%5D:%20DEVPROP_TYPE_BINARY%20%20RELEASE:%20%2810/9/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")




