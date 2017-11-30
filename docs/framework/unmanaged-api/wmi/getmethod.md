---
title: "GetMethod 函数 （非托管 API 参考）"
description: "GetMethod 函数可检索有关方法的信息。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethod
helpviewer_keywords: GetMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b4e89dabb7f4542a63260445ff2d70edcafc1784
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="getmethod-function"></a>GetMethod 函数
检索有关指定方法的信息。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`wszName`  
[in]方法名。 此参数不能为`null`且必须指向有效`LPCWSTR`。

`lFlags`  
[in]保留。 此参数必须为 0。

`ppInSignature`   
[out]指向的地址的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)描述在 paramteers 到方法的实例。 如果设置为，则忽略此参数`null`。 

`ppOutSignature`  
[out]指向的地址的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)描述对方法的输出参数的实例。 如果设置为，则忽略此参数`null`。 

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | 找不到指定的属性。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx)方法。

可以设置 Windows 管理[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)指向`null`如果此方法不具有任何输入参数。

在`ppInSignature`和`ppOutSignature`分别，为中的属性描述输入和输出参数，`IWbemClassObject`系统类的实例[_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx)。 中的属性`ppInsignature`命名**Param***n*，其中 *n* 是参数 （例如将方法签名中的位置作为`Param1`，`Param2`等。)。 中的属性`ppOutSignature`也称为**Param***n*，和返回值名为**ReturnValue**。 有关详细信息及示例，请参阅[IWbemClassObject::GetMethod 方法](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx)。

## <a name="requirements"></a>要求  
**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
