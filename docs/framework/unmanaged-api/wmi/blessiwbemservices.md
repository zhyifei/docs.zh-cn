---
title: BlessIWbemServices 函数（非托管 API 参考）
description: BlessIWbemServices 函数指示用户凭据是否允许对 IWbemServices 类的访问。
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 946d29892052ea69c2a8a3bf11e7be7a1b2d7068
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138779"
---
# <a name="blessiwbemservices-function"></a>BlessIWbemServices 函数
指示用户凭据是否允许访问指定的[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)类。   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a>参数

`pIWbemServices`\
中指向需要其权限的[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象的指针。

`strUser`\
中用户名。

`strPassword`\
中与 `strUser`关联的密码。

`strAuthority`\
中用户的域名。 有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。

`impLevel`\
中模拟级别。

`authnLevel`\
中授权级别。

## <a name="return-value"></a>返回值

此函数返回的以下值是在*winerror.h*头文件中定义的，也可以在代码中将它们定义为常量：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | 一个或多个参数无效。 |
| `E_POINTER` | 0x80004003 | `pIWbemServices` 为 `null`。 | 
| `E_FAIL` | 0x80000008 | 发生了未指定的错误。 |
| `E_OUTOFMEMORY` | 0x80000002 | 内存不足，无法执行此操作。 | 
| `S_OK` | 0 | 函数调用成功。 | 

## <a name="requirements"></a>要求  

 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils .idl  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
