---
title: GetMethod 函数 （非托管 API 参考）
description: GetMethod 函数检索有关方法的信息。
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a913de0ff20fba51295fd8282b58e3953be9bba2
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773954"
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
[in]此参数是未使用。

`ptr`  
[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。

`wszName`  
[in]方法名称。 此参数不能`null`必须指向有效和`LPCWSTR`。

`lFlags`  
[in]保留。 此参数必须为 0。

`ppInSignature`   
[out]指向的地址的指针[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)介绍的方法在 paramteers 的实例。 如果设置为，则忽略此参数`null`。 

`ppOutSignature`  
[out]指向的地址的指针[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例，它描述的方法的 out 参数。 如果设置为，则忽略此参数`null`。 

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | 找不到指定的属性。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)方法。

Windows 管理可以设置[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指向`null`如果方法没有在参数。

在中`ppInSignature`并`ppOutSignature`描述 in 和 out 参数，分别为中的属性`IWbemClassObject`系统类的实例[_Parameters](/windows/desktop/WmiSdk/--parameters)。 中的属性`ppInsignature`名为 **Param * * * n*，其中*n*参数的方法签名中的位置 (如`Param1`， `Param2`，等等。)。 中的属性`ppOutSignature`也名为 **Param * * * n*，并命名为返回值**ReturnValue**。 有关详细信息和示例，请参阅[IWbemClassObject::GetMethod 方法](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)。

## <a name="requirements"></a>要求  
**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
