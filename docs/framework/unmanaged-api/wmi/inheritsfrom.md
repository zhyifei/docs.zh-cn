---
title: InheritsFrom 函数（非托管 API 参考）
description: InheritsFrom 函数确定类或实例是否从特定的父类派生。
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c32c54ec56ea0fe4f4039ca6438a91338edbadb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798453"
---
# <a name="inheritsfrom-function"></a>InheritsFrom 函数
确定当前类或实例是否派生自指定的父类。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
中此参数未使用。

`ptr`  
中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。

`wszAncestor`  
中类的名称。 `wszAncestor`必须指向有效`LPCWSTR`的。

## <a name="return-value"></a>返回值

此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：

|返回的常量  |值  |Description  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | 0 | 当前对象继承自`wszAncestor`。  |
| `WBEM_S_FALSE` | 1 | 当前的对象不是从`wszAncestor`继承的。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszAncestor` 为 `null`。 |
  
## <a name="remarks"></a>备注

此函数包装对[IWbemClassObject：： InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom)方法的调用。

## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
