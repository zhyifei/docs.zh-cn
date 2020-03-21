---
title: PutMethod 函数（非托管 API 引用）
description: PutMethod 函数创建一个方法。
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
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174909"
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

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

`wszName`  
[在]要创建的方法的名称。

`lFlags`  
[in] 保留。 此参数必须为 0。

`pSignatureIn`  
[在]指向包含方法参数[的__Parameters系统类](/windows/desktop/WmiSdk/--parameters)`in`副本的指针。 如果设置为`null`，则忽略此参数。  

`pSignatureOut`  
[在] 指向包含方法参数[的__Parameters系统类](/windows/desktop/WmiSdk/--parameters)`out`副本的指针。 如果设置为`null`，则忽略此参数。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 一个或多个参数无效。 |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0 x80041043 | 在`[in, out]` *pInSignature*和*pOutSignature*对象中指定的方法参数具有不同的限定符。
| `WBEM_E_MISSING_PARAMETER_ID` | 0 x80041036 | 缺少**ID**限定符的规范的方法参数。 |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0 x80041038 | 分配给方法参数的 ID 系列不是连续的，也不是从 0 开始的。 |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0 x80041039 | 方法的返回值具有**ID**限定符。 |
| `WBEM_E_PROPAGATED_METHOD` | 0 x80041034 | 尝试从父类重用现有方法名称，并且签名不匹配。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。 |
  
## <a name="remarks"></a>备注

此函数包装对[IWbemClassObject：:PutMethod 方法的](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)调用。

仅当是 CIM 类定义`ptr`时，才支持此方法调用。 方法操作从指向 CIM 实例的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指针中不可用。

用户无法创建名称以下划线开头或结尾的方法。 这是为系统类和属性保留的。

对于方法，`in`和`out`参数被描述为[IWbemClassObject 对象](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)中的属性。

`[in/out]`可以通过将相同的属性添加到 和`pInSignature``pOutSignature`参数指向的两个对象来定义参数。 在这种情况下，属性共享相同的**ID**限定符值。

[__Parameters](/windows/desktop/WmiSdk/--parameters)类对象中的每个属性除必须具有`ReturnValue`**ID**限定符外，该限定符是标识参数显示顺序的零基数值。 没有两个参数可以具有相同的**ID**值，并且不能跳过**ID**值。 如果发生任一条件，`PutMethod`则函数`WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`将返回 。

## <a name="example"></a>示例

例如，请参阅[IWbemClassObject：:PutMethod 方法](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
