---
title: NextMethod 函数（非托管 API 引用）
description: NextMethod 函数检索枚举中的下一个方法。
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174922"
---
# <a name="nextmethod-function"></a>NextMethod 函数
检索枚举中的下一个方法，该方法以调用[BeginMethodEa）](beginmethodenumeration.md)开头。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

`lFlags`  
[in] 保留。 此参数必须为 0。

`pName`  
[出]指向调用`null`之前的指针。 当函数返回时，包含方法名称的新地址`BSTR`。

`ppSignatureIn`  
[出]接收指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针的指针，其中包含方法的`in`参数。

`ppSignatureOut`  
[出]接收指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针的指针，其中包含方法的`out`参数。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | 没有调用该[`BeginEnumeration`](beginenumeration.md)函数。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 枚举中没有更多的属性。 |
  
## <a name="remarks"></a>备注

此函数包装对[IWbemClassObject：：NextMethod 方法](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)的调用。

调用方通过调用[BeginMethod 枚举](beginmethodenumeration.md)函数来开始枚举序列，然后调用 [NextMethod] 函数，直到函数返回`WBEM_S_NO_MORE_DATA`。 或者，调用方通过调用[EndMethod 枚举](endmethodenumeration.md)来完成序列。 调用方可以随时调用[EndMethodEa 枚举](endmethodenumeration.md)，从而提前终止枚举。

## <a name="example"></a>示例

有关C++示例，请参阅[IWbemClassObject：：NextMethod 方法](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
