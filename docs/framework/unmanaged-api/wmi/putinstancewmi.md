---
title: "PutInstanceWmi 函数 （非托管 API 参考）"
description: "PutInstanceWmi 函数创建或更新现有类的实例。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: PutInstanceWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: PutInstanceWmi
helpviewer_keywords: PutInstanceWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7a4ffce4789fb59d84778d02b41910c974216bd
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="putinstancewmi-function"></a>PutInstanceWmi 函数
创建或更新现有类的实例。 实例将写入 WMI 存储库。 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a>参数

`pInst`    
[in]指向要写入的实例的指针。

`lFlags`   
[in]影响此函数的行为的标志的组合。 在中定义以下值*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中： 

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | 如果设置，WMI 不存储任何限定符与**Amended**风格。 </br> 如果不设置，则假定此对象未本地化，以及所有的限定符是 storedwith 此实例。 |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | 如果不存在，或如果它已存在对其进行覆盖，请创建该实例。 |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | 更新的实例。 实例必须存在才能成功的调用。 |
| `WBEM_FLAG_CREATE_ONLY` | 2 | 创建实例。 如果该实例已经存在，则调用将失败。 |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 标志会导致半同步调用。 |

`pCtx`  
[in]通常，此值是`null`。 否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx)可用的提供程序提供请求的类的实例。 

`ppCallResult`  
[out]如果`null`，未使用此参数。 如果`lFlags`包含`WBEM_FLAG_RETURN_IMMEDIATELY`，该函数将立即返回与`WBEM_S_NO_ERROR`。 `ppCallResult`参数接收一个指针，到新[IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx)对象。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | 用户没有权限来更新指定类的实例。 |
| `WBEM_E_FAILED` | 0x80041001 | 发生未知的错误。 |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | 支持此实例的类无效。 |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | `null`已为不能为属性指定`null`，例如标记**索引**或**空白**限定符。 |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | 指定的实例不是有效的。 (例如，调用`PutInstanceWmi`与类返回该值。) |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数不是有效的。 |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | `WBEM_FLAG_CREATE_ONLY`指定了标记，但是该实例已经存在。 |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY`中指定`lFlags`，但该实例不存在。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI 时可能已停止和重新启动。 调用[ConnectServerWmi](connectserverwmi.md)试。 |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。 |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemServices::PutInstance](https://msdn.microsoft.com/library/aa392115(v=vs.85).aspx)方法。

`PutInstanceWmi`函数支持创建实例和更新现有的类的实例。  具体取决于如何`pCtx`设置参数，系统将更新某些或所有实例的属性。 

当实例指向`pInst`所属的子类，Windows 管理调用负责子类派生的类的所有提供程序。 所有这些提供程序必须成功执行原始`PutInstanceWmi`请求才能成功。 首先调用层次结构中支持的最顶层类的提供程序。 调用顺序会继续进行的最顶层类的子类和继续从顶部到底部直到 Windows 管理达到拥有指向的实例的类的提供程序`pInst`。
Windows 管理不调用任何实例的子类别的提供程序。 

当应用程序必须更新实例属于类层次结构，`pInst`参数必须指向包含要修改的属性的实例。 也就是说，考虑所属的目标实例**ClassB**。 **ClassB**实例派生自**ClassA**，和**ClassA**定义该属性**PropA**。 如果应用程序想要对的值进行更改**PropA**中**ClassB**实例，它必须设置`pInst`到该实例，而不是实例**ClassA**.

调用`PutInstanceWmi`不允许抽象类的实例上。

如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。

## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
