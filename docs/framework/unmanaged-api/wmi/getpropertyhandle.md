---
title: "GetPropertyHandle 函数 （非托管 API 参考）"
description: "GetPropertyHandle 函数返回一个唯一的句柄该 identies 属性。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3af852fb4b9899a7937f288ffb65d8ca84e4aef1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getpropertyhandle-function"></a>GetPropertyHandle 函数
返回一个唯一的句柄，标识属性。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx)实例。

`wszPropertyName`  
[in]包含属性名称的 UTF16 编码 characaters 的以 null 结尾的字符串。   

`pType`  
[out]指向的指针[ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx)表示属性的 CIM 类型的枚举成员。

`pHandle`   
[out]指向一个包含属性句柄整数的指针。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | 找不到指定的属性名称。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数不是有效的。 |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | 请求的属性属于类型是`CIM_OBJECT`或`CIM_ARRAY`。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx)方法。

你可以使用此句柄来标识属性，使用时[IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx)方法读取或写入属性值。

句柄可以检索的属性的所有数据类型以外`CIM_OBJECT`和`CIM_ARRAY`。 返回在类的所有实例的句柄的工作。

## <a name="requirements"></a>惠?  
**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
