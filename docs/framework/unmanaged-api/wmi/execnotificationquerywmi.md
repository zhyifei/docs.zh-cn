---
title: ExecNotificationQueryWmi 函数 （非托管 API 参考）
description: ExecNotificationQueryWmi 函数执行一个查询来接收事件。
ms.date: 11/06/2017
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b5c26ab9c273b134915eea39078a83f569bcd32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="execnotificationquerywmi-function"></a>ExecNotificationQueryWmi 函数
执行查询以接收事件。 调用立即返回，并且它们到达时，调用方可以轮询事件返回的枚举数。 释放返回的枚举数取消查询。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ExecNotificationQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a>参数

`strQueryLanguage`    
[in]包含支持 Windows 管理的有效的查询语言的字符串。 它必须是"WQL"，WMI 查询语言的首字母缩写。

`strQuery`  
[in]查询的文本。 此参数不能为`null`。

`lFlags`   
[in]影响此函数的行为的以下两个标志的组合。 在中定义这些值*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中。 

| 返回的常量 | 值  | 描述  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 标志会导致半同步调用。 如果未设置此标志，则调用将失败。 这是因为事件接收连续，这意味着用户必须轮询返回的枚举数。 无限期地阻止此调用，将无法进行。 |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | 该函数返回的只进的枚举器。 通常，只进的枚举器速度更快和使用的内存少于传统枚举器，但它们不允许调用[克隆](clone.md)。 |

`pCtx`  
[in]通常，此值是`null`。 否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx)可由提供的请求的事件提供程序的实例。 

`ppEnum`  
[out]如果未发生错误，接收到的枚举器允许调用方检索中查询的结果集的实例的指针。 请参阅[备注](#remarks)部分以了解更多信息。

`authLevel`  
[in]授权级别中。

`impLevel` [in]模拟级别。

`pCurrentNamespace`   
[in]指向的指针[IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx)对象，表示当前的命名空间。

`strUser`   
[in]用户名。 请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。

`strPassword`   
[in]密码。 请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。

`strAuthority`   
[in]用户的域名。 请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | 用户没有权限查看一个或多个函数可以返回的类。 |
| `WBEM_E_FAILED` | 0x80041001 | 发生未知的错误。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数不是有效的。 |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | 查询指定不存在的类。 |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | 0x80042002 | 已请求中传递的事件太多精度。 必须指定更大的轮询容差。 |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | 0x80042001 | 查询 requess 可以提供比 Windows 管理的详细信息。 这`HRESULT`事件查询导致轮询命名空间中的所有对象的请求时返回。 |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | 查询必须语法错误。 |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | 不支持请求的查询语言。 |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | 查询太过复杂。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI 时可能已停止和重新启动。 调用[ConnectServerWmi](connectserverwmi.md)试。 |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。 |
| `WBEM_E_UNPARSABLE_QUERY` | 0x80041058 | 无法分析查询。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx)方法。

该函数将返回后，调用方定期传递返回`ppEnum`对象传递给[下一步](next.md)函数以了解是否有任何事件。

对于数没有限制`AND`和`OR`关键字可以在 WQL 查询中使用。 大量复杂的查询中使用的 WQL 关键字可能会导致 WMI 返回`WBEM_E_QUOTA_VIOLATION`（或 0x8004106c） 错误代码为`HRESULT`值。 WQL 关键字的限制取决于如何复杂查询是。

如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。

## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
