---
title: GetMethod 函数（非托管 API 参考）
description: GetMethod 函数检索有关方法的信息。
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9cc185bf8cccb8ed3c24e28954afd86464602d7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798562"
---
# <a name="getmethod-function"></a>GetMethod 函数

检索有关指定方法的信息。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法

```cpp
HRESULT GetMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```

## <a name="parameters"></a>参数

`vFunc`\
中此参数未使用。

`ptr`\
中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。

`wszName`\
中方法名称。 此参数不能`null`为，且必须指向有效`LPCWSTR`的。

`lFlags`\
[in] 保留。 此参数必须为0。

`ppInSignature`\
弄一个指针，指向用于描述方法的 in 参数的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的地址。 如果将此参数设置为`null`，则忽略此参数。

`ppOutSignature`\
弄一个指针，指向用于描述方法的 out 参数的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的地址。 如果将此参数设置为`null`，则忽略此参数。

## <a name="return-value"></a>返回值

此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：

|返回的常量  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | 找不到指定的属性。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存可用来完成此操作。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |

## <a name="remarks"></a>备注

此函数包装对[IWbemClassObject：： GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)方法的调用。

如果该方法在参数中没有，  Windows Management 可以将 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 指针设置为`null`。

在`ppInSignature` `IWbemClassObject`和`ppOutSignature`中，分别介绍了 in 和 out 参数，作为 system 类[_Parameters](/windows/desktop/WmiSdk/--parameters)的实例中的属性。 中`ppInSignature`的属性名为`Param` *n*，其中*n*是参数在方法签名中的位置（例如`Param1`、 `Param2`等）。 中`ppOutSignature`的属性也命名为`Param` *n* `ReturnValue`，返回值为。 有关详细信息和示例，请参阅[IWbemClassObject：： GetMethod 方法](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)。

## <a name="requirements"></a>要求

**适用**请参阅[系统需求](../../get-started/system-requirements.md)。

**标头：** WMINet_Utils.idl

**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
