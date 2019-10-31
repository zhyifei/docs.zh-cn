---
title: SetSecurity 函数（非托管 API 参考）
description: SetSecurity 函数检索当前线程的模拟标记。
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6d27779bcfc97e1c4156b8782896e83d4754491b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120216"
---
# <a name="setsecurity-function"></a>SetSecurity 函数

检索与当前线程关联的模拟令牌。 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a>参数

`pNeedToReset`\
弄当函数返回时，将包含一个指向 `boolean` 的指针，该指针指示是否应通过调用[ResetSecurity](resetsecurity.md)函数来重置令牌。

`token`\
弄当函数返回时，包含指向与当前线程关联的模拟标记的句柄的指针。 如果没有与当前线程关联的标记，则可以 `null` 其值。 

## <a name="return-value"></a>返回值

如果该函数成功，则返回值为 `S_OK` （0）。

如果函数失败，则返回值为非零错误代码。 若要获取扩展的错误信息，请调用[GetErrorInfo](geterrorinfo.md)函数。

## <a name="requirements"></a>要求

 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。

 **标头：** WMINet_Utils .idl

 **.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
