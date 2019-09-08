---
title: PutMethod 函数（非托管 API 参考）
description: PutMethod 函数将创建方法。
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2b41cbbade9da5c2095309b9039b8ce2758f6f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798363"
---
# <a name="putmethod-function"></a>PutMethod 函数
创建方法。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
中此参数未使用。

`ptr`  
中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。

`wszName`  
中要创建的方法的名称。 

`lFlags`  
[in] 保留。 此参数必须为0。

`pSignatureIn`  
中一个指针，指向包含`in`方法的参数的[__Parameters 系统类](/windows/desktop/WmiSdk/--parameters)的副本。 如果设置为`null`，则忽略此参数。  

`pSignatureOut`  
中 一个指针，指向包含`out`方法的参数的[__Parameters 系统类](/windows/desktop/WmiSdk/--parameters)的副本。 如果设置为`null`，则忽略此参数。

## <a name="return-value"></a>返回值

此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 一个或多个参数无效。 |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | PInSignature `[in, out]`和*pOutSignature*对象中指定的 method 参数具有不同的限定符。
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | 方法参数缺少**ID**限定符的规范。 |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | 分配给方法参数的 ID 序列不是连续的，或者不是从0开始。 |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | 方法的返回值具有**ID**限定符。 |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | 尝试重用父类的现有方法名称，且签名不匹配。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。 |
  
## <a name="remarks"></a>备注

此函数包装对[IWbemClassObject：:P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)方法的调用。

仅当`ptr`为 CIM 类定义时，才支持此方法调用。 指向 CIM 实例的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指针不提供方法操作。

用户无法创建名称以下划线开头或结尾的方法。 此为系统类和属性保留。

对于方法，和`in` `out`参数被描述为[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)对象中的属性。

通过向`pInSignature`和参数`pOutSignature`指向的两个对象添加相同的属性，可以定义参数。`[in/out]` 在这种情况下，属性共享相同的**ID**限定符值。

除以外`ReturnValue`的[__Parameters](/windows/desktop/WmiSdk/--parameters)类对象中的每个属性都必须具有**ID**限定符，这是一个标识参数出现顺序的从零开始的数字值。 不能有两个参数具有相同的**id**值，也不能跳过任何**id**值。 如果发生上述任一情况， `PutMethod`函数将`WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`返回。

## <a name="example"></a>示例

有关示例，请参阅[IWbemClassObject：:P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)方法。

## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
