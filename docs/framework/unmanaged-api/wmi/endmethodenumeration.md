---
title: 结束方法枚举函数（非托管 API 引用）
description: EndMethodEee）计数函数终止方法枚举序列。
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 63667d0668f905ded2aedd961be0d1831faf838c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175000"
---
# <a name="endmethodenumeration-function"></a>EndMethodEnumeration 函数
终止以调用[BeginMethodEee 计算函数](beginmethodenumeration.md)开始的枚举序列。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | 0x8004101d | 发生了内部错误。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数将调用包起来到[IWbemClassObject：：结束方法枚举](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration)方法。

调用方使用[BeginMethodEee 枚举函数](beginmethodenumeration.md)开始枚举序列，然后调用[NextMethod 函数](nextmethod.md )，直到`WBEM_S_NO_MORE_DATA`方法返回 。 调用方通过调用`EndMethodEnumeration`完成序列。 调用方可能通过随时调用`EndMethodEnumeration`来提前终止枚举。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
