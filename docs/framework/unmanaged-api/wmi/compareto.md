---
title: "CompareTo 函数 （非托管 API 参考）"
description: "CompareTo 函数比较到另一个 WMI 对象的对象。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 038074b5bb3adc816caa226d3167395758d2ae57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="compareto-function"></a>CompareTo 函数
比较对象和另一个 Windows 管理对象。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`flags`  
[in]指定要考虑进行比较的对象特征的标志的按位组合。 请参阅[备注](#remarks)部分以了解更多信息。

`pCompareTo`  

[in]用于比较的对象。 `pcompareTo`必须为有效[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例; 它不能是`null`。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 发生未知的错误。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数无效。 |
| `WBEM_E_UNEXPECTED` | 0x8004101d | 第二个调用`BeginEnumeration`而无需对的干预调用进行[ `EndEnumeration` ](endenumeration.md)。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
| `WBEM_S_DIFFERENT` | 0x40003 | 对象有不同。 |
| `WBEM_S_SAME` | 0 | 对象相同的基于比较标志。 |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx)方法。

可以作为传递的标志`lEnumFlags`中定义参数*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中。 通过指定以下标志的按位组合，可以指定在比较中涉及的各个特征：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | 忽略源 （服务器和它们的命名空间）。 |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | 忽略所有的限定符 (包括**密钥**和**动态**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | 忽略属性的默认的值。 此标志只适用于的类的比较。 |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | 忽略的限定符特色信息。 此标志仍将限定符考虑在内，但会忽略风格差别如传播规则和重写限制。 |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | 忽略大小写的比较字符串值。 这同时适用于字符串和限定符值。 属性和限定符的名称比较始终是区分大小写，无论是否设置此标志。 |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | 假定要比较的对象都是同一个类的 instanes。 因此，此标志将实例相关信息进行比较。 使用此标志来优化性能。 如果这些对象不属于相同，则结果是类的未定义。 |

或者，你可以指定单个复合标志，如下所示：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | 请考虑在比较中的所有功能。 |

## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
