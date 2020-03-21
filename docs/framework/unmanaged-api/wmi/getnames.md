---
title: 获取名称功能（非托管 API 引用）
description: GetNames 函数检索对象属性的名称。
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 449f0ce9c291d4bbcad4947214e56ff46f55beed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174948"
---
# <a name="getnames-function"></a>GetNames 函数
检索对象属性的子集或所有名称。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

`wszQualifierName`  
[在]指向有效的`LPCWSTR`指针，用于指定作为筛选器一部分运行的限定符名称。 有关详细信息，请参阅[备注](#remarks)部分。 此参数可以为 `null`。

`lFlags`  
[在]位字段的组合。 有关详细信息，请参阅[备注](#remarks)部分。

`pQualifierValue`[在]指向初始化到筛选器`VARIANT`值的有效结构的指针。 此参数可以为 `null`。

`pstrNames`  
[出]包含`SAFEARRAY`属性名称的结构。 在输入时，此参数必须始终是指向`null`的指针。 有关详细信息，请参阅[备注](#remarks)部分。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 出现了一个普遍的失败。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 一个或多个参数无效，或指定了不正确的标志和参数组合。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的可用内存来完成该操作。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对[IWbem ClassObject 的调用：：getNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames)方法。

返回的命名由标志和参数的组合控制。 例如，函数可以返回所有属性的名称，也可以仅返回键属性的名称。  主筛选器在`lFlags`参数中指定，其他参数因它而异。

中`lFlags`的标志值是位字段

可以作为`lEnumFlags`参数传递的标志是在*WbemCli.h*标头文件中定义的位字段，也可以将它们定义为代码中的常量。  您可以将每个组中的一个标志与任何其他组的任何标志合并。 但是，来自同一组的标志是互斥的。

| 组 1 标志 |值  |说明  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | 返回所有属性名称。 `strQualifierName`未`pQualifierVal`使用。 |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | 仅返回具有`strQualifierName`参数指定名称限定符的属性。 如果使用此标志，则必须指定`strQualifierName`。 |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  仅返回没有`strQualifierName`参数指定名称限定符的属性。 如果使用此标志，则必须指定`strQualifierName`。 |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | 仅返回具有`wszQualifierName`参数指定名称限定符且值与`pQualifierVal`结构指定的值相同的属性。 如果使用此标志，则必须同时指定 a`wszQualifierName`和 。 `pQualifierValue` |

| 组 2 标志 |值  |说明  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | 仅返回定义键的属性的名称。 |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | 仅返回作为对象引用的属性名称。 |

| 组 3 标志 |值  |说明  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 仅返回属于最派生类的属性名称。 从父类中排除属性。 |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 仅返回属于父类的属性名称。 |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | 仅返回系统属性的名称。 |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | 仅返回非系统属性的名称。 |

如果函数返回`SAFEARRAY``WBEM_S_NO_ERROR`，则始终分配新函数，并且`pstrNames`始终设置为指向它。 如果没有与指定筛选器匹配的属性，则返回的数组可以具有 0 个元素。 如果函数返回的值，`WBM_S_NO_ERROR`则不返回新`SAFEARRAY`结构。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
