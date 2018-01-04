---
title: "QualifierSet_Delete 函数 （非托管 API 参考）"
description: "QualifierSet_Delete 函数按名称删除限定符。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Delete
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Delete
helpviewer_keywords: QualifierSet_Delete function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e7b5650a0b47fd8d9b64bb9d0fff3511afe2d43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetdelete-function"></a>QualifierSet_Delete 函数
按名称删除指定的限定符。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`   
[in]指向的指针[IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)实例。

`wszName`   
[in]要删除的限定符的名称。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszName`参数无效。 |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | 删除此限定符是非法的。 |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 找不到指定的限定符。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | 本地重写已删除并从父对象的原始限定符已恢复作用域。 |

## <a name="remarks"></a>备注

此函数包装对的调用[IWbemQualifierSet::Delete](https://msdn.microsoft.com/library/aa391864(v=vs.85).aspx)方法。

由于限定符传播规则，而特定限定符可能已继承自另一个对象和仅在当前类或实例中重写。 在这种情况下，`QualifierSet_Delete`方法将限定符重置为其原始的继承值。 函数将在此情况下返回状态代码`WBEM_S_RESET_TO_DEFAULT`。

## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
