---
title: PutClassWmi 函数 （非托管 API 参考）
description: PutClassWmi 函数创建一个新类，或更新现有。
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ce887d59d02cfc2e4d8c183aa495dcc1535853c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="putclasswmi-function"></a>PutClassWmi 函数
创建新的类或更新现有。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a>参数

`pObject`    
[in]指向有效的类定义的指针。 它必须使用所有必需的属性值正确初始化。

`lFlags`   
[in]影响此函数的行为的标志的组合。 在中定义以下值*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中： 

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | 如果集，WMI 不存储任何限定符与已修正的风格。 </br> 如果不设置，则假定此对象未本地化，以及所有的限定符是 storedwith 此实例。 |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | 如果不存在，或如果它已存在对其进行覆盖，请创建类。 |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | 更新类。 类必须存在才能成功的调用。 |
| `WBEM_FLAG_CREATE_ONLY` | 2 | 创建类。 如果该类已存在，则调用将失败。 |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 标志会导致半同步调用。 |
| `WBEM_FLAG_OWNER_UPDATE` | 0x10000 | 在调用时，请求提供程序必须指定此标志`PutClassWmi`以指示此类已更改。 |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | 0 | 允许的类，如果有任何派生的类和类的任何实例更新。 同时它还允许出了如果更改只需为重要的限定符，如描述限定符，在所有情况下的更新。 如果类具有实例或更改是对重要限定符，则更新失败。 |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | 0x20 | 允许的类的更新，即使有子类别，只要更改不会使用子类的任何冲突。 例如，此标志将允许新属性添加到中的任何子类未以前提到的基类。 如果类具有实例，则更新失败。 |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | 0x40 | 时存在冲突的子类别，强制实施的类的更新。 例如，如果类限定符定义在子类中，并且基类尝试将同一限定符与一个现有的数值冲突添加此标志将强制更新。 在强制模式下，通过删除子类别中发生冲突的限定符，可解决 tis 冲突。 |

`pCtx`  
[in]通常，此值是`null`。 否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx)可用的提供程序提供请求的类的实例。 

`ppCallResult`  
[out]如果`null`，未使用此参数。 如果`lFlags`包含`WBEM_FLAG_RETURN_IMMEDIATELY`，该函数将立即返回与`WBEM_S_NO_ERROR`。 `ppCallResult`参数接收一个指针，到新[IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx)对象。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | 用户没有创建或修改类的权限。 |
| `WBEM_E_FAILED` | 0x80041001 | 发生未知的错误。 |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | 指定的类不是有效的。 通常情况下，这指示`pObject`指定的实例对象。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数不是有效的。 |
| `WBEM_E_INVALID OPERATION` | 0x80041016 | 指定的类名称无效。 |
| `WBEM_E_CLASS_HAS_CHILDREN` | 0x80041025 | 尝试进行的更改会使子类无效。 |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | `WBEM_FLAG_CREATE_ONLY`指定了标记，但该类已存在。 |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY` 中指定`lFlags`，但找不到类。 |
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | 类的必需的属性不是所有尚未设置。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI 时可能已停止和重新启动。 调用[ConnectServerWmi](connectserverwmi.md)试。 |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemServices::PutClass](https://msdn.microsoft.com/library/aa392113(v=vs.85).aspx)方法。

用户可能不具有名称的开头或结尾下划线 chacater 创建的类

如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。

## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
