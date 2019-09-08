---
title: GetQualifierSet 函数（非托管 API 参考）
description: GetQualifierSet 函数检索为类或实例设置的限定符。
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 845d5ea93a06859840c87c65b415ead0f846d538
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798462"
---
# <a name="getqualifierset-function"></a>GetQualifierSet 函数
检索类实例或类定义的限定符集。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
中此参数未使用。

`ptr`  
中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。

`ppQualSet`  
弄接收允许访问类对象限定符的接口指针。 `ppQualSet` 不能为 `null`。 如果发生错误，则不会返回新的对象，并且不会修改指针。 

## <a name="return-value"></a>返回值

此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：

|返回的常量  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 出现一般错误。 |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 指定的方法不存在。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存可用来完成此操作。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数为`null`。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对[IWbemClassObject：： GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset)方法的调用。 

通过[IWbemQualifierSet 指针](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)，调用方可以添加、编辑或删除这些限定符。 此类添加的、编辑或删除的限定符应用于整个实例或类定义。

## <a name="requirements"></a>要求  
**适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
