---
title: 获取对象文本功能（非托管 API 引用）
description: GetObjectText 函数在 MOF 语法中返回对象的文本呈现。
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6881125760e0f1dc38e6b01917d5829edc95e3ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176781"
---
# <a name="getobjecttext-function"></a>GetObjectText 函数
在托管对象格式 （MOF） 语法中返回对象的文本呈现。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

`lFlags`  
[在]通常为 0。 如果`WBEM_FLAG_NO_FLAVORS`指定 （或 0x1），则包含限定符而不包含传播或风味信息。

`pstrObjectText`[出]指向上条目的`null`指针。 返回时，包含对象的`BSTR`MOF 语法呈现的新分配。  

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 出现了一个普遍的失败。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数无效。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的可用内存来完成该操作。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数将调用包起来到[IWbem ClassObject：：getObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext)方法。

返回的 MOF 文本不包含有关对象的所有信息，但仅包含足够的信息，以便 MOF 编译器能够重新创建原始对象。 例如，不包含传播的限定符或父类属性。

以下算法用于重建方法参数的文本：

1. 参数按其标识符值的顺序重新排序。
1. 指定为`[in]`并`[out]`组合到单个参数的参数。

`pstrObjectText`调用函数时必须指向`null`的 指针;它不得指向方法调用之前有效的字符串，因为指针不会被处理。

## <a name="requirements"></a>要求  
**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
