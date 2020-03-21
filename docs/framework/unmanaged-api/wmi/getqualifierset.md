---
title: 获取限定符集功能（非托管 API 引用）
description: GetQualifierSet 函数检索类或实例的限定符集。
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
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176768"
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

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

`ppQualSet`  
[出]接收允许访问类对象的限定符的接口指针。 `ppQualSet` 不能为 `null`。 如果发生错误，则不返回新对象，并且指针未修改。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 出现了一个普遍的失败。 |
|`WBEM_E_NOT_FOUND` | 0 x80041002 | 指定的方法不存在。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的可用内存来完成该操作。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数为`null`。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对[IWbem ClassObject 的调用：：getQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset)方法。

[IWbemQualifierSet 指针](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)允许调用方添加、编辑或删除这些限定符。 此类添加、编辑或删除的限定符适用于整个实例或类定义。

## <a name="requirements"></a>要求  
**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
