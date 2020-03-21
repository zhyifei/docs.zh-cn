---
title: QualifierSet_Get函数（非托管 API 引用）
description: QualifierSet_Get函数获取命名的限定符。
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
ms.openlocfilehash: 2f4e2d4518e01f3415b8f17ce5778dd98b2a45c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174883"
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

## <a name="parameters"></a>parameters

`vFunc`[在]此参数未使用。

`ptr`[在]指向[IWbem 限定符集实例的](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)指针。

`wszName`[在]请求其值的限定符的名称。

`lFlags`[在]保留。 此参数必须为 0。

`pVal`[出]成功后，限定符的正确类型和值。 如果函数失败，`VARIANT`则 不修改`pVal`指向 的 。 如果此参数为`null`，则忽略该参数。

`plFlavor`[出]指向 LONG 的指针，该指针接收请求的限定符的限定符的限定符风味位。 如果不需要风味信息，则此参数可以是`null`。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数无效。 |
|`WBEM_E_NOT_FOUND` | 0 x80041002 | 指定的限定符不存在。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对[IWbem 限定符集的调用：：get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get)方法。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
