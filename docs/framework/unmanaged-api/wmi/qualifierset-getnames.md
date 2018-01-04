---
title: "QualifierSet_GetNames 函数 （非托管 API 参考）"
description: "QualifierSet_GetNames 函数从对象或属性检索的限定符的名称。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_GetNames
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_GetNames
helpviewer_keywords: QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6077b448c2644f68d12679cf208ee921c2af119a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetgetnames-function"></a>QualifierSet_GetNames 函数
检索所有的限定符或某些限定符可从当前对象或属性的名称。 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a>参数

`vFunc`   
[in]未使用此参数。

`ptr`   
[in]指向的指针[IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)实例。

`lFlags`   
[in]以下标志或指定要包括在枚举中的名称的值之一。

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|  | 0 | 返回所有限定符的名称。 |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 返回特定于当前的属性或对象的限定符的名称。 <br/> 属性： 返回仅限定符特定的属性 （包括替代），并不这些限定符传播从类定义。 <br/> 实例： 返回仅特定于实例的限定符的名称。 <br/> 类： 回到派生类 beiong 特定仅限定符。
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | 返回名称的列是限定符传播的另一个对象。 <br/> 属性： 返回仅限定符传播到此属性从类定义中，而不从本身的属性。 <br/> 实例： 从类定义返回仅这些限定符传播。 <br/> 类： 返回仅这些限定符名称从父类继承。 |

`pstrNames`[out]一个新`SAFEARRAY`，它包含请求的名称。 该数组可以具有 0 个元素。 如果发生错误，新`SAFEARRAY`不会返回。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数不是有效的。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存，可开始新的枚举。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx)方法。

已检索到的限定符名称后, 你可以每个限定符按名称访问通过调用[QualifierSet_Get](qualifierset-get.md)函数。 

它不是给定的对象，因此具有零个限定符，一个错误中的字符串的数量`pstrNames`返回可为 0，即使该函数将返回`WBEM_S_NO_ERROR`。

## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
