---
title: "ExecQueryWmi 函数 （非托管 API 参考）"
description: "ExecQueryWmi 函数执行查询以检索对象。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ExecQueryWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ExecQueryWmi
helpviewer_keywords: ExecQueryWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ebd5463fd3b4109203e829da8e3683bbb79cf59
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="execquerywmi-function"></a>ExecQueryWmi 函数
执行查询以检索对象。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ExecQueryWmi (
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
[in]影响此函数的行为的标志的组合。 在中定义以下值*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中： 

| 返回的常量 | 值  | 描述  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | 如果集，该函数检索当前连接的区域设置的本地化命名空间中存储的修正的限定符。 <br/> 如果未设置，函数将检索存储在即时命名空间限定符。 |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 标志会导致半同步调用。 |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | 该函数返回的只进的枚举器。 通常，只进的枚举器速度更快和使用的内存少于传统枚举器，但它们不允许调用[克隆](clone.md)。 |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI 将保留指向 enumration 中的对象的指针，直到它们被释放为止。 | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | 0x100 | 确保任何返回的对象中都有足够的信息，因此该系统属性，如**__PATH**， **__RELPATH**，和**__SERVER**，不是`null`。 |
| `WBEM_FLAG_PROTOTYPE` | 2 | 此标志用于原型制作。 它不会执行查询，并改为返回的对象，如下所示的典型结果对象。 |
| `WBEM_FLAG_DIRECT_READ` | 0x200 | 原因直接访问提供程序而不考虑其父类或任何子类指定的类。 |

建议的标志是`WBEM_FLAG_RETURN_IMMEDIATELY`和`WBEM_FLAG_FORWARD_ONLY`为了获得最佳性能。

`pCtx`  
[in]通常，此值是`null`。 否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx)可用的提供程序提供请求的类的实例。 

`ppEnum`  
[out]如果未发生错误，接收到的枚举器允许调用方检索中查询的结果集的实例的指针。 查询可以具有零个实例的结果集。 请参阅[备注](#remarks)部分以了解更多信息。

`authLevel`  
[in]授权级别中。

`impLevel`[in]模拟级别。

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
| `WBEM_E_INVALID_QUERY` | 0x80041017 | 查询必须语法错误。 |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | 不支持请求的查询语言。 |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | 查询太过复杂。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI 时可能已停止和重新启动。 调用[ConnectServerWmi](connectserverwmi.md)试。 |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。 |
| `WBEM_E_NOT_FOUND` | 0x80041002 | 查询指定不存在的类。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx)方法。

此函数处理中指定的查询`strQuery`参数和创建一个通过其调用方可以访问查询结果的枚举器。 枚举器是一个指向[IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx)接口; 查询结果是通过提供的类对象的实例[IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx)接口。

对于数没有限制`AND`和`OR`关键字可以在 WQL 查询中使用。 大量复杂的查询中使用的 WQL 关键字可能会导致 WMI 返回`WBEM_E_QUOTA_VIOLATION`（或 0x8004106c） 错误代码为`HRESULT`值。 WQL 关键字的限制取决于如何复杂查询是。

如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。

## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
