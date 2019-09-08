---
title: QualifierSet_Get 函数（非托管 API 参考）
description: QualifierSet_Get 函数获取命名限定符。
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 751694985248346187eff016ef7a4a8054cb1212
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798314"
---
# <a name="qualifierset_get-function"></a>QualifierSet_Get 函数
获取指定的命名限定符。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>参数

`vFunc`   
中此参数未使用。

`ptr`   
中指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例的指针。

`wszName`   
中请求其值的限定符的名称。

`lFlags`   
[in] 保留。 此参数必须为0。

`pVal`   
弄如果成功，则为限定符的正确类型和值。 如果函数失败， `VARIANT`则不会修改指向的。 `pVal` 如果此参数为`null`，则忽略参数。

`plFlavor`   
弄一个指向 LONG 的指针，它接收所请求限定符的限定符风格位。 如果不需要口味信息，此参数可以为`null`。 

## <a name="return-value"></a>返回值

此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：

|返回的常量  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数无效。 |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 指定的限定符不存在。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对[IWbemQualifierSet：： Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get)方法的调用。

## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
