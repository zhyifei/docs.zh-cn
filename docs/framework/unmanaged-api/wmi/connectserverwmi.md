---
title: ConnectServerWmi 函数 （非托管 API 参考）
description: ConnectServerWmi 函数使用 DCOM 创建与 WMI 命名空间的连接。
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de8447b9b090fc7f53df23346d61932bcb4dd6ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="connectserverwmi-function"></a>ConnectServerWmi 函数
指定计算机上创建的 WMI 命名空间通过 DCOM 的连接。  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```  
## <a name="parameters"></a>参数

`strNetworkResource` [in]指针到有效`BSTR`包含正确的 WMI 命名空间的对象路径。 请参阅[备注](#remarks)部分以了解更多信息。

`strUser` [in]指向一个有效的指针`BSTR`包含的用户名称。 A`null`值指示当前的安全上下文。 如果用户是从不同的域与当前`strUser`还可以包含反斜杠分隔的域和用户名称。 `strUser` 此外可以将在用户主体名称 (UPN) 设置格式，作为 suhc *userName@domainName*。 请参阅[备注](#remarks)部分以了解更多信息。

`strPassword` [in]指向一个有效的指针`BSTR`包含的密码。 A`null`指示当前的安全上下文。 空字符串 ("") 指示有效长度为零的密码。

`strLocale` [in]指向一个有效的指针`BSTR`，该值指示用于信息检索正确的区域设置。 对于 Microsoft 区域设置标识符，字符串的格式是"MS\_*xxx*"，其中*xxx*以十六进制形式，该值指示的区域设置标识符 (LCID) 是一个字符串。 如果指定了无效的区域设置，该方法返回`WBEM_E_INVALID_PARAMETER`在 Windows 7，其中服务器的默认区域设置改为使用上除外。 如果使用 null1，当前区域设置。 
 
`lSecurityFlags` [in]要传递给标志`ConnectServerWmi`方法。 为零 (0)，此参数值将导致调用`ConnectServerWmi`返回仅后建立到服务器的连接。 这可能导致应用程序未响应无限期地如果服务器将断开。 其他有效值为：

| 返回的常量  | 值  | 描述  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0x40 | 保留以供内部使用。 请勿使用。 |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi` 返回在两分钟或更短。 |

`strAuthority` [in]用户的域名。 可以有下列值：

| 值 | 描述 |
|---------|---------|
| 空白 | 使用 NTLM 身份验证，并使用当前用户的 NTLM 该域。 如果`strUser`指定的域 （推荐位置），它必须不此处指定。 该函数将返回`WBEM_E_INVALID_PARAMETER`如果这两个参数中指定的域。 |
| Kerberos:*主体名称* | 使用 Kerberos 身份验证，并且此参数包含 Kerberos 主体名称。 |
| NTLMDOMAIN:*域名* | 使用 NT LAN 管理器身份验证，并且此参数包含的 NTLM 域名。 |

`pCtx`   
[in]通常，此参数是`null`。 否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx)所需的一个或多个动态类提供程序的对象。 

`ppNamespace`  
[out]当函数返回时，接收一个指针，到[IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx)对象绑定到指定的命名空间。 它被设置为指向`null`时出错。

`impLevel`  
[in]模拟级别。

`authLevel`  
[in]授权级别中。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 发生了常规错误。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数不是有效的。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx)方法。

 有关对默认命名空间，本地访问`strNetworkResource`可以是简单对象路径:"根 \ 默认"或"\\.\root\default"。 用于访问远程计算机上的默认命名空间使用 COM 或 Microsoft 兼容的网络，包含计算机名称:"\\myserver\root\default"。 计算机名称也可以是 DNS 名称或 IP 地址。 `ConnectServerWmi`函数还可以连接运行 IPv6 的计算机使用 IPv6 地址。

`strUser` 不能为空字符串。 如果在指定了域`strAuthority`，它必须不还会包含在`strUser`，或该函数将返回`WBEM_E_INVALID_PARAMETER`。


## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
