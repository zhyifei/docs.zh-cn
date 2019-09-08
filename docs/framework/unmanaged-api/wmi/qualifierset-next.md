---
title: QualifierSet_Next 函数（非托管 API 参考）
description: QualifierSet_Next 函数检索枚举中的下一个限定符。
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f97a19f236b87a7f4c5b2014aca6ee4abd338c63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798284"
---
# <a name="qualifierset_next-function"></a>QualifierSet_Next 函数
检索枚举中的下一个限定符，该枚举以调用 [QualifierSet_BeginEnumeration ](qualifierset-beginenumeration.md) 函数开始。   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>参数

`vFunc`   
中此参数未使用。

`ptr`   
中指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例的指针。

`lFlags`   
[in] 保留。 此参数必须为0。

`pstrName`   
弄限定符的名称。 如果`null`为，则忽略此参数; 否则`pstrName` ，将不会指向有效`BSTR`或内存泄漏。 如果不为 null，则当函数返回`BSTR` `WBEM_S_NO_ERROR`时，它将始终分配一个新的。

`pVal`   
弄如果成功，则为限定符的值。 如果函数失败， `VARIANT`则不会修改指向的。 `pVal` 如果此参数为`null`，则忽略参数。

`plFlavor`   
弄指向接收限定符风格的长时间的指针。 如果不需要口味信息，此参数可以为`null`。 

## <a name="return-value"></a>返回值

此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：

|返回的常量  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数无效。 |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 调用方未调用[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存可用于开始新的枚举。 |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 枚举中没有剩余限定符。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对[IWbemQualifierSet：： Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)方法的调用。

重复调用`QualifierSet_Next`函数以枚举所有限定符，直到函数返回`WBEM_S_NO_MORE_DATA`。 若要提前终止枚举，请调用[QualifierSet_EndEnumeration](qualifierset-endenumeration.md)函数。

枚举过程中返回的限定符的顺序是不确定的。

## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
