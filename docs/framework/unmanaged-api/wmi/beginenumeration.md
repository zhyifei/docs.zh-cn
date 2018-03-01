---
title: "BeginEnumeration 函数 （非托管 API 参考）"
description: "BeginEnumeration 函数将枚举器重置到开头枚举"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 90c3e8448a61145290ea4a75b1d38f7ae010cb9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="beginenumeration-function"></a>BeginEnumeration 函数
将枚举数重置回枚举的开头。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`lEnumFlags`  
[in]标志或中所述的值的按位组合[备注](#remarks)控制包含在枚举中的属性的部分。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 中的标志的组合`lEnumFlags`无效，或者无效指定的参数。 |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 第二个调用`BeginEnumeration`而无需对的干预调用进行[ `EndEnumeration` ](endenumeration.md)。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存，可开始新的枚举。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)方法。

可以作为传递的标志`lEnumFlags`中定义参数*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中。  你可以组合使用任何其他组的任何标志每个组中的一个标志。 但是，同一组中的标志是互斥的。 

**组 1**

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | 包括构成仅密钥的属性。 |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | 包括仅对象引用的属性。 |

**组 2**

返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | 限制对系统属性仅枚举。 |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | 包括本地和传播属性，但枚举中排除系统属性。 |

对于类：

返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | 限制对属性重写的类定义中枚举。 |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | 限制到当前的类定义中重写的属性和新属性的类中定义的枚举。 |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | 一个掩码 （而不是一个标志） 用于针对`lEnumFlags`要检查如果任一值`WBEM_FLAG_CLASS_OVERRIDES_ONLY`或`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`设置。 |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 限制到属性定义或修改在类本身中枚举。 |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 限制从基类继承的属性对枚举。 |

实例：

返回的常量  |“值”  |描述  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 限制到属性定义或修改在类本身中枚举。 |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 限制从基类继承的属性对枚举。 |


## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
