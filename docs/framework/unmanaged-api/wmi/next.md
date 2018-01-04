---
title: "下一步函数 （非托管 API 参考）"
description: "下一步的函数 retireves 枚举中的下一步属性中。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Next
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Next
helpviewer_keywords: Next function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e59ef3f65b75a91708dc65f7d4e3d811dc2d3f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="next-function"></a>下一步函数
检索到的调用开始枚举中的下一步属性[BeginEnumeration](beginenumeration.md)。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Next (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor     
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`lFlags`  
[in]保留。 此参数必须为 0。

`pstrName`  
[out]一个新`BSTR`，其中包含属性名称。 你可以将此参数设置为`null`如果不需要名称。

`pVal`  
[out]A`VARIANT`填充的属性的值。 你可以将此参数设置为`null`如果不需要值。 如果该函数返回错误代码，`VARIANT`传递给`pVal`左未修改形式。 

`pvtType`  
[out]指向的指针`CIMTYPE`变量 (`LONG`属性的类型放置)。 此属性的值可以是`VT_NULL_VARIANT`，在这种情况下就需要确定属性的实际类型。 此参数还可以为`null`。 

`plFlavor`  
[out]`null`，或接收信息的来源的属性的值。 请参阅有关可能的值 [备注] 部分。 

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 发生了常规错误。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数无效。 |
| `WBEM_E_UNEXPECTED` | 0x8004101d | 没有不需要调用[ `BeginEnumeration` ](beginenumeration.md)函数。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存，可开始新的枚举。 |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 远程过程调用之间的当前进程和失败的 Windows 管理。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 枚举中没有更多属性。 |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx)方法。

此方法也返回系统属性。

如果对象路径、 日期或时间或另一种特殊类型的属性的基础类型，则返回的类型不包含足够的信息。 调用方必须检查`CIMTYPE`来确定属性是否是一个对象引用、 日期或时间或另一种特殊类型的指定属性。

如果`plFlavor`不`null`、`LONG`值接收有关原点的属性的信息，如下所示：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | 属性是标准系统属性。 |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | 类： 从父类继承属性。 </br> 实例： 属性，继承自的父类、 时未修改的实例。  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | 类： 属性所属的派生类。 </br> 实例： 实例; 修改的属性也就是说，已提供的值，或限定符已添加或修改。 |

## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
