---
title: 开始枚举函数（非托管 API 引用）
description: BeginEe枚举函数将枚举器重置为枚举的开头
ms.date: 11/06/2017
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
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176872"
---
# <a name="beginenumeration-function"></a>BeginEnumeration 函数
将枚举器重置回枚举的开头。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a>parameters

`vFunc`\
[在]此参数未使用。

`ptr`\
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

`lEnumFlags`\
[在]控制枚举中包含的属性的[备注](#remarks)部分中描述的标志或值的位组合。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 中`lEnumFlags`的标志组合无效，或指定了无效的参数。 |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 第二次呼叫`BeginEnumeration`是在没有干预调用[`EndEnumeration`](endenumeration.md)的情况下进行的。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存可用于开始新的枚举。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对[IWbemClassObject 的调用：：开始枚举](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)方法。

可在`lEnumFlags`*WbemCli.h*标头文件中定义作为参数传递的标志，也可以将它们定义为代码中的常量。  您可以将每个组中的一个标志与任何其他组的任何标志合并。 但是，来自同一组的标志是互斥的。

**组 1**

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | 仅包含构成密钥的属性。 |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | 仅包含对象引用的属性。 |

**组 2**

一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | 仅将枚举限制为系统属性。 |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | 包括本地和传播属性，但从枚举中排除系统属性。 |

对于类：

一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | 将枚举限制为类定义中重写的属性。 |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | 将枚举限制为当前类定义中重写的属性和类中定义的新属性。 |
| `WBEM_MASK_CLASS_CONDITION` | 0 x 300 | 要针对`lEnumFlags`值应用的蒙版（而不是标志），以检查是否设置了。 `WBEM_FLAG_CLASS_OVERRIDES_ONLY` `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 将枚举限制为在类本身中定义或修改的属性。 |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 将枚举限制为从基类继承的属性。 |

例如：

一直  |值  |说明  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 将枚举限制为在类本身中定义或修改的属性。 |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 将枚举限制为从基类继承的属性。 |

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
