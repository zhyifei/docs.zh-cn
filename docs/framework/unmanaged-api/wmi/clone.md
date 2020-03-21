---
title: 克隆功能（非托管 API 引用）
description: Clone 函数返回一个新对象，该对象是当前对象的完整克隆。
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: cb4951a1f289417482bfa1287028cc66349a5938
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176846"
---
# <a name="clone-function"></a>Clone 函数
返回一个新对象，该对象是当前对象的完整克隆。
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

`ppCopy`  
[出]一个新对象，它是 完全孤独的`ptr`。 `null`如果此参数收到当前对象的副本，则不能。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 出现了一个普遍的失败。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `null`被指定为参数，在此用法中不合法。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存可用于克隆对象。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对[IWbem ClassObject：：克隆](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)方法的调用。

克隆的对象是引用计数为 1 的 COM 对象。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
