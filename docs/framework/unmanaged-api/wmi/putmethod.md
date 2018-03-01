---
title: "PutMethod 函数 （非托管 API 参考）"
description: "PutMethod 函数创建一个方法。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e97ffcf44a738234f67d9736382c46c42e5b61e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="putmethod-function"></a>PutMethod 函数
创建一个方法。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`wszName`  
[in]要创建的方法名称。 

`lFlags`  
[in]保留。 此参数必须为 0。

`pSignatureIn`  
[in]指向一份[__Parameters 系统类](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx)包含`in`方法的参数。 如果忽略此参数设置为`null`。  

`pSignatureOut`  
[in] 指向一份[__Parameters 系统类](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx)包含`out`方法的参数。 如果忽略此参数设置为`null`。
 

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 一个或多个参数不是有效的。 |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | `[in, out]`方法参数中同时指定*pInSignature*和*pOutSignature*对象具有不同的限定符。
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | 方法参数缺少的规范**ID**限定符。 |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | 分配给方法参数 ID 系列不连续，或不在 0 时不启动。 |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | 一种方法的返回值具有**ID**限定符。 |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | 尝试重用现有方法的父类、 名称和签名不匹配。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。 |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx)方法。

如果仅支持此方法调用`ptr`是 CIM 类定义。 方法操作不能从[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396)指向 CIM 实例的指针。

用户无法创建方法的开头或结尾下划线开头的名称。 这被保留供系统类和属性。

对于方法，`in`和`out`参数为中的属性，请参见[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396)对象。

`[in/out]`参数可以通过将相同的属性添加到指向这两个对象定义`pInSignature`和`pOutSignature`参数。 在这种情况下，属性共用同一个**ID**限定符值。

每个属性[__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx)以外类对象`ReturnValue`必须具有**ID**限定符，标识参数的顺序的从零开始的数字值。 没有两个参数可以具有相同**ID**值，但没有**ID**可以跳过值。 如果任何一种情况发生，`PutMethod`函数返回`WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`。

## <a name="example"></a>示例

有关示例，请参阅[IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx)方法。

## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
