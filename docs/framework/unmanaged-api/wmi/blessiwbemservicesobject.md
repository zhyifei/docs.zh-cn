---
title: 祝福IWbem服务对象功能（非托管 API 引用）
description: 祝福IWbem服务对象功能指示用户凭据是否允许访问 IWbem 服务对象
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: fd822f78d29ad3a75fb5e57dd7c23b7049d445b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175026"
---
# <a name="blessiwbemservicesobject-function"></a>BlessIWbemServicesObject 函数
指示用户凭据是否允许访问指定的[IWbem 服务](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a>parameters

`pIWbemServices`\
[在]指向 WMI 服务对象的指针。

`strUser`\
[在]用户名。

`strPassword`\
[在]与`strUser`关联的密码。

`strAuthority`\
[在]用户的域名。 有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。

`impLevel`\
[在]模拟级别。

`authnLevel`\
[在]授权级别。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WinError.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | 一个或多个参数无效。 |
| `E_POINTER` | 0x80004003 | `pIWbemServices` 为 `null`。 |
| `E_FAIL` | 0x80000008 | 发生了未知错误。 |
| `E_OUTOFMEMORY` | 0x80000002 | 可用内存不足以执行操作。 |
| `S_OK` | 0 | 函数调用成功。 |

## <a name="requirements"></a>要求

 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。

 **标题：** WMINet_Utils.idl

 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
