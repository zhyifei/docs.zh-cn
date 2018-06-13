---
title: Put 的函数 （非托管 API 参考）
description: Put 函数将新值分配给指定的属性。
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f3ffe27bef6583b733fc04f2f25903d545daa74
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460374"
---
# <a name="put-function"></a>Put 的函数
将指定的属性设置为新值。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```  
HRESULT Put (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`wszName`  
[in]属性的名称。 此参数不能为`null`。

`lFlags`  
[in]保留。 此参数必须为 0。

`pVal`   
[in]指向一个有效的指针`VARIANT`该按钮将变为新的属性值。 如果`pVal`是`null`或指向`VARIANT`类型的`VT_NULL`，该属性设置为`null`。 

`vtType`  
[in]一种`VARIANT`指向`pVal`。 请参阅[备注](#remarks)部分以了解更多信息。
 

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 发生了常规错误。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 一个或多个参数不是有效的。 |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | 无法识别属性类型。 创建类实例，如果该类已存在时，则返回此值。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005 | 实例： 指示`pVal`指向`VARIANT`属性类型不正确。 <br/> 类定义： 的父类、 中已存在的属性和新的 COM 类型是否不同于旧的 COM 类型。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。 |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx)方法。

此函数始终会用一个新覆盖当前的属性值。 如果[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)指向类定义，`Put`创建或更新的属性值。 当[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)指向 CIM 的实例，`Put`更新属性值仅;`Put`无法创建属性值。

`__CLASS`系统属性时才是可写类在创建期间，它可能不能留空。 所有其他系统属性是只读的。

用户无法创建属性的开头或结尾下划线 (_) 开头的名称。 这被保留供系统类和属性。

如果该属性设置的`Put`父类中存在的函数，除非该属性类型与父类类型不匹配，则更改属性的默认值。 如果属性不存在，并且它不是类型不匹配，则该属性为 ceated。

使用`vtType`参数仅在 CIM 类定义中创建新属性时和`pVal`是`null`或指向`VARIANT`类型的`VT_NULL`。 在这种情况下，`vType`参数指定的属性的 CIM 类型。 在每个其他情况下，`vtType`必须为 0。 `vtType` 如果基础对象为实例也必须为 0 (即使`Val`是`null`) 因为属性的类型固定的不能更改。   

## <a name="example"></a>示例

有关示例，请参阅[IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx)方法。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
