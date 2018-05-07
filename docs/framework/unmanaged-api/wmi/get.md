---
title: Get 函数 （非托管 API 参考）
description: Get 函数将检索指定的属性值。
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f837a526879f80177bc9979e1d7671edfcd8d4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="get-function"></a>Get 函数
如果它存在，请检索指定的属性值。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
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

`wszName`  
[in]属性的名称。

`lFlags` [in]保留。 此参数必须为 0。

`pVal` [out]如果该函数将返回成功，包含的值的`wszName`属性。 `pval`自变量分配的正确类型和值限定符。

`pvtType` [out]如果该函数将返回成功，则包含[CIM 类型的常量](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx)，该值指示属性类型。 其值也可以是`null`。 

`plFlavor` [out]如果该函数将返回成功，则接收原点顺的属性的信息。 其值可以是`null`，或定义中的以下 WBEM_FLAVOR_TYPE 常量之一*WbemCli.h*标头文件： 

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | 属性是标准系统属性。 |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | 类： 从父类继承属性。 </br> 实例： 属性，继承自的父类、 时未修改的实例。  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | 类： 属性所属的派生类。 </br> 实例： 实例; 修改的属性也就是说，已提供的值，或限定符已添加或修改。 |

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 发生了常规错误。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 一个或多个参数不是有效的。 |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 找不到指定的属性。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx)方法。

`Get`函数还可以返回系统属性。

`pVal`自变量分配的正确类型和值限定符和 COM [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx)函数

## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
