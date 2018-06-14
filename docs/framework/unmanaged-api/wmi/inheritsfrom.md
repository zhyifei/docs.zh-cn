---
title: InheritsFrom 函数 （非托管 API 参考）
description: InheritsFrom 函数将确定类或实例派生自特定的父类。
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
ms.openlocfilehash: 87a1c1ee44d3b192747bd785f538c0332300ff50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461410"
---
# <a name="inheritsfrom-function"></a>InheritsFrom 函数
确定当前类或实例派生自指定的父类别。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`wszAncestor`  
[in]类的名称。 `wszAncestor` 必须指向有效`LPCWSTR`。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | 0 | 当前对象继承自`wszAncestor`。  |
| `WBEM_S_FALSE` | 1 | 当前对象不是继承自`wszAncestor`。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszAncestor` 为 `null`。 |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx)方法。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
