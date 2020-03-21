---
title: 获取功能（非托管 API 引用）
description: Get 函数检索指定的属性值。
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 67fcfb301eebfcf4ed4fdcaa5c9ddf85c47a6073
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174974"
---
# <a name="get-function"></a>Get 函数

如果指定的属性值存在，则检索该值。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法

```cpp
HRESULT Get (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a>parameters

`vFunc`\
[在]此参数未使用。

`ptr`\
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

`wszName`\
[在]属性的名称。

`lFlags`\
[in] 保留。 此参数必须为 0。

`pVal`\
[出]如果函数成功返回，则包含`wszName`属性的值。 为`pval`限定符分配了正确的类型和值。

`pvtType`\
[出]如果函数成功返回，则包含指示属性类型的[CIM 类型常量](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration)。 其值也可以`null`是 。

`plFlavor`\
[出]如果函数成功返回，则接收有关属性源的信息。 其值可以是`null`，或者*WbemCli.h*标头文件中定义的以下WBEM_FLAVOR_TYPE常量之一：

|一直  |值  |说明  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | 属性是标准系统属性。 |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | 对于类：属性是从父类继承的。 <br> 对于实例：属性虽然从父类继承，但实例尚未修改。  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | 对于类：属性属于派生类。 <br> 对于实例：属性由实例修改;但是，该属性由 实例修改。即，提供了值，或者添加或修改了限定符。 |

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 出现了一个普遍的失败。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 一个或多个参数无效。 |
|`WBEM_E_NOT_FOUND` | 0 x80041002 | 找不到指定的属性。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的可用内存来完成该操作。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |

## <a name="remarks"></a>备注

此函数包装对[IWbem ClassObject 的调用：：get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get)方法。

该`Get`函数还可以返回系统属性。

为`pVal`限定符和 COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit)函数分配了正确的类型和值

## <a name="requirements"></a>要求

 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。

 **标题：** WMINet_Utils.idl

 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
