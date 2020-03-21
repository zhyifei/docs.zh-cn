---
title: QualifierSet_Next函数（非托管 API 引用）
description: QualifierSet_Next函数在枚举中检索下一个限定符。
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
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174870"
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

## <a name="parameters"></a>parameters

`vFunc`[在]此参数未使用。

`ptr`[在]指向[IWbem 限定符集实例的](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)指针。

`lFlags`[在]保留。 此参数必须为 0。

`pstrName`[出]限定符的名称。 如果`null`忽略 此 参数，则忽略此参数。否则，`pstrName`不应指向有效`BSTR`或发生内存泄漏。 如果不是 null，则函数在返回`BSTR``WBEM_S_NO_ERROR`时始终分配一个新的。

`pVal`[出]成功时，限定符的值。 如果函数失败，`VARIANT`则 不修改`pVal`指向 的 。 如果此参数为`null`，则忽略该参数。

`plFlavor`[出]指向接收限定符味道的 LONG 的指针。 如果不需要风味信息，则此参数可以是`null`。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数无效。 |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 呼叫者未呼叫[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存可用于开始新的枚举。 |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 枚举中不再保留限定符。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对[IWbem 限定符集的调用：：下一个](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)方法。

重复调用函数`QualifierSet_Next`以枚举所有限定符，直到函数返回`WBEM_S_NO_MORE_DATA`。 要提前终止枚举，请调用[QualifierSet_EndEnumeration](qualifierset-endenumeration.md)函数。

枚举期间返回的限定符的顺序未定义。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
