---
title: "GetNames 函数 （非托管 API 参考）"
description: "GetNames 函数检索的对象的属性的名称。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetNames
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetNames
helpviewer_keywords: GetNames function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80284900c318a3776168b781ce2e0e5e4a68f96d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getnames-function"></a>GetNames 函数
检索的子集或所有对象的属性的名称。 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`wszQualifierName`  
[in]指向一个有效的指针`LPCWSTR`指定筛选器的一部分运行的限定符名称。 有关详细信息，请参阅[备注](#remarks)部分。 此参数可以为 `null`。 

`lFlags`  
[in]位域的组合。 有关详细信息，请参阅[备注](#remarks)部分。

`pQualifierValue`   
[in]指向一个有效的指针`VARIANT`结构初始化为筛选器值。 此参数可以为 `null`。 

`pstrNames`  
[out]A`SAFEARRAY`结构，其中包含属性名称。 在进入时，此参数必须始终为指向的指针`null`。 请参阅[备注](#remarks)部分以了解更多信息。 

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 发生了常规错误。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 一个或多个参数是无效，或未指定的标志和参数的正确组合。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx)方法。

由标志和参数的组合控制返回的命名。 例如，函数可以返回所有属性的名称或键属性的名称。  中指定主筛选器`lFlags`参数，并使用其他参数不同，具体取决于它。

中的标志值`lFlags`是位域


可以作为传递的标志`lEnumFlags`自变量是在中定义的位域*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中。  你可以组合使用任何其他组的任何标志每个组中的一个标志。 但是，同一组中的标志是互斥的。 

| 组 1 标志 |“值”  |描述  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | 返回所有属性名。 `strQualifierName`和`pQualifierVal`未使用。 |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | 返回具有指定的名称的限定符的唯一属性`strQualifierName`参数。 如果使用此标志，你必须指定`strQualifierName`。 |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  返回不具有指定的名称的限定符的唯一属性`strQualifierName`参数。 如果使用此标志，你必须指定`strQualifierName`。 |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | 返回具有指定的名称的限定符的属性`wszQualifierName`参数和也有等于指定的值`pQualifierVal`结构。 如果使用此标志，则必须将同时指定`wszQualifierName`和`pQualifierValue`。 |

| 组 2 标志 |“值”  |描述  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | 返回仅定义的键的属性的名称。 |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | 返回唯一属性的名称是对象的引用。 |

| 组 3 标志 |“值”  |描述  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 返回属于派生程度最高的类添加的属性名称。 从父类中排除属性。 |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 返回属于父类添加的属性名称。 |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | 返回系统属性的名称。 |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | 返回仅非系统属性的名称。 |

函数始终分配一个新`SAFEARRAY`如果它返回`WBEM_S_NO_ERROR`，和`pstrNames`始终设置为指向它。 如果没有属性与指定筛选器匹配，则返回的数组可以有 0 个元素。 如果该函数返回值以外`WBM_S_NO_ERROR`，新`SAFEARRAY`结构，则不返回。
 
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
