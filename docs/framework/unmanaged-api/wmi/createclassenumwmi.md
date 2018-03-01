---
title: "CreateClassEnumWmi 函数 （非托管 API 参考）"
description: "CreateClassEnumWmi 函数将返回满足指定的条件的所有类的枚举数。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2058bad61af79244d211afb6a7661ca1642db070
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="createclassenumwmi-function"></a>CreateClassEnumWmi 函数
返回满足指定的选择条件的所有类的枚举数。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
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

`strSuperclass`    
[in]如果不是`null`或留空，指定的名称的父类; 枚举器返回仅的此类的子类。 如果它是`null`或空白和`lFlags`为 WBEM_FLAG_SHALLOW，则返回仅顶级类 （与任何父类的类）。 如果它是`null`或空白和`lFlags`是`WBEM_FLAG_DEEP`，命名空间中返回所有类。

`lFlags`   
[in]影响此函数的行为的标志的组合。 在中定义以下值*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中： 

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | 如果集，该函数检索当前连接的区域设置的本地化命名空间中存储的修正的限定符。 <br/> 如果未设置，函数将检索存储在即时命名空间限定符。 |
| `WBEM_FLAG_DEEP` | 0 | 枚举在层次结构，但不是此类包含所有子类。 |
| `WBEM_FLAG_SHALLOW` | 1 | 枚举包括的此类仅纯实例，并排除的子类，可提供此类中找不到属性的所有实例。 |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 标志会导致半同步调用。 |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | 该函数返回的只进的枚举器。 通常，只进的枚举器速度更快和使用的内存少于传统枚举器，但它们不允许调用[克隆](clone.md)。 |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI 将保留指向 enumration 中的对象的指针，直到它们被释放为止。 | 

建议的标志是`WBEM_FLAG_RETURN_IMMEDIATELY`和`WBEM_FLAG_FORWARD_ONLY`为了获得最佳性能。

`pCtx`  
[in]通常，此值是`null`。 否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx)可用的提供程序提供请求的类的实例。 

`ppEnum`  
[out]接收枚举数的指针。

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

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | 用户没有权限查看一个或多个函数可以返回的类。 |
| `WBEM_E_FAILED` | 0x80041001 | 发生未知的错误。 |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | `strSuperClass` 不存在。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数不是有效的。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI 时可能已停止和重新启动。 调用[ConnectServerWmi](connectserverwmi.md)试。 |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[iwbemservices:: Createclassenum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx)方法。

如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。

## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
