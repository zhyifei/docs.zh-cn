---
title: QualifierSet_Delete功能（非托管 API 引用）
description: QualifierSet_Delete函数按名称删除限定符。
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0d2a02ba9d89ba16e776bb73563eaebf8a92f1fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174896"
---
# <a name="qualifierset_delete-function"></a>QualifierSet_Delete 函数
按名称删除指定限定符。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName
);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`[在]指向[IWbem 限定符集实例的](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)指针。

`wszName`[在]要删除的限定符的名称。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszName` 参数无效。 |
|`WBEM_E_INVALID_OPERATION` | 0 x80041016 | 删除此限定符是非法的。 |
|`WBEM_E_NOT_FOUND` | 0 x80041002 | 未找到指定的限定符。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
| `WBEM_S_RESET_TO_DEFAULT` | 0 x40002 | 本地重写已被删除，父对象的原始限定符已恢复作用域。 |

## <a name="remarks"></a>备注

此函数包装对[IWbem 限定符集：:Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete)方法的调用。

由于限定符传播规则，特定限定符可能从另一个对象继承，并且只是在当前类或实例中重写。 在这种情况下，`QualifierSet_Delete`该方法将限定符重置为其原始继承的值。 在这种情况下，函数返回状态代码`WBEM_S_RESET_TO_DEFAULT`。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
