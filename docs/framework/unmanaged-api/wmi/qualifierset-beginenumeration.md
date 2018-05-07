---
title: QualifierSet_BeginEnumeration 函数 （非托管 API 参考）
description: QualifierSet_BeginEnumeration 函数将重置枚举器对象的限定符。
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fac897f743ca452c38282143cdf822b682df1df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="qualifiersetbeginenumeration-function"></a>QualifierSet_BeginEnumeration 函数
将枚举数对象的限定符重置为枚举的开头。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a>参数

`vFunc`   
[in]未使用此参数。

`ptr`   
[in]指向的指针[IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)实例。

`lFlags`   
[in]标志或中所述的值的按位组合[备注](#remarks)部分，用于指定要包含在枚举中的限定符。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `lFlags`参数无效。 |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 第二个调用`QualifierSet_BeginEnumeration`而无需对的干预调用进行[ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md)。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存，可开始新的枚举。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx)方法。

若要枚举所有对象上的限定符，此方法必须调用之前首次调用[QualifierSet_Next](qualifierset-next.md)。 在其中枚举限定符的顺序被保证是固定为给定的枚举。

可以作为传递的标志`lEnumFlags`中定义参数*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中。   

|返回的常量  |值  |描述  |
|---------|---------|---------|
|  | 0 | 返回所有限定符的名称。 |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 返回特定于当前的属性或对象的限定符的名称。 <br/> 属性： 返回仅限定符特定的属性 （包括替代），并不这些限定符传播从类定义。 <br/> 实例： 返回仅特定于实例的限定符的名称。 <br/> 类： 回到派生类 beiong 特定仅限定符。
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | 返回名称的列是限定符传播的另一个对象。 <br/> 属性： 返回仅限定符传播到此属性从类定义中，而不从本身的属性。 <br/> 实例： 从类定义返回仅这些限定符传播。 <br/> 类： 返回仅这些限定符名称从父类继承。 |

## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
