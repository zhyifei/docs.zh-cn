---
title: ConnectServerWmi 函数（非托管 API 参考）
description: ConnectServerWmi 函数使用 DCOM 创建到 WMI 命名空间的连接。
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
ms.openlocfilehash: 2ebb268dcee877f4e9aea0c88852333897030dd1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798751"
---
# <a name="connectserverwmi-function"></a>ConnectServerWmi 函数

通过 DCOM 创建到指定计算机上的 WMI 命名空间的连接。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法

```cpp
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

`strNetworkResource`\
中指向有效`BSTR`的的指针，该指针包含正确的 WMI 命名空间的对象路径。 有关详细信息，请参阅 "[备注](#remarks)" 部分。

`strUser`\
中指向包含用户名的有效`BSTR`的指针。 `null`值指示当前安全上下文。 如果用户来自不同于当前域的域， `strUser`还可以包含用反斜杠分隔的域和用户名。 `strUser`也可以是用户主体名称（UPN）格式，例如`userName@domainName`。 有关详细信息，请参阅 "[备注](#remarks)" 部分。

`strPassword`\
中指向包含密码的有效`BSTR`的指针。 `null`指示当前安全上下文。 空字符串（""）表示有效的零长度密码。

`strLocale`\
中指向有效`BSTR`的指针，该指针指示信息检索的正确区域设置。 对于 Microsoft 区域设置标识符，字符串的格式为 "MS\_*xxx*"，其中*xxx*是十六进制格式的字符串，用于指示区域设置标识符（LCID）。 如果指定了无效的区域设置，则方法`WBEM_E_INVALID_PARAMETER`将返回，但 Windows 7 除外，此时将使用服务器的默认区域设置。 如果为 "null1"，则使用当前区域设置。

`lSecurityFlags`\
中要传递给方法的`ConnectServerWmi`标志。 如果此参数的值为零（0），则仅在建立`ConnectServerWmi`与服务器的连接后才调用返回。 如果服务器中断，这可能导致应用程序不会无限期地响应。 其他有效值为：

| 返回的常量  | 值  | 描述  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0x40 | 保留以供内部使用。 请勿使用。 |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi`返回两分钟或更少的时间。 |

`strAuthority`\
中用户的域名。 可以有下列值：

| 值 | 描述 |
|---------|---------|
| 空白 | 使用 NTLM 身份验证，并使用当前用户的 NTLM 域。 如果`strUser`指定域（建议位置），则不得在此处指定。 如果在这`WBEM_E_INVALID_PARAMETER`两个参数中指定了域，则该函数返回。 |
| Kerberos：*主体名称* | 使用 kerberos 身份验证，并且此参数包含 Kerberos 主体名称。 |
| NTLMDOMAIN：*域名* | 使用 NT LAN 管理器身份验证，此参数包含 NTLM 域名。 |

`pCtx`\
中此参数通常为`null`。 否则，它是指向一个或多个动态类提供程序所需的[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)对象的指针。

`ppNamespace`\
弄当函数返回时，将接收指向绑定到指定命名空间的[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象的指针。 `null`如果出现错误，则将其设置为指向。

`impLevel`\
中模拟级别。

`authLevel`\
中授权级别。

## <a name="return-value"></a>返回值

此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 出现一般错误。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数无效。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存可用来完成此操作。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |

## <a name="remarks"></a>备注

此函数包装对[IWbemLocator：： ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver)方法的调用。

对于对默认命名空间的本地访问`strNetworkResource` ，可以是一个简单的对象路径： "root\default"\\或 ".\root\default"。 若要使用 COM 或 Microsoft 兼容的网络访问远程计算机上的默认命名空间，请包含计算机名称： "\\myserver\root\default"。 计算机名称也可以是 DNS 名称或 IP 地址。 此`ConnectServerWmi`函数还可以使用 ipv6 地址与运行 ipv6 的计算机连接。

`strUser`不能为空字符串。 如果在中`strAuthority`指定了域，则它也不能包含在`strUser`中，或者该函数`WBEM_E_INVALID_PARAMETER`返回。

## <a name="requirements"></a>要求

 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。

 **标头：** WMINet_Utils.idl

 **.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
