---
title: QualifierSet_EndEnumeration函数（非托管 API 引用）
description: QualifierSet_EndEnumeration函数终止枚举。
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c606580ff2e02c5659c14b134b1a17a65651952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176742"
---
# <a name="qualifierset_endenumeration-function"></a>QualifierSet_EndEnumeration 函数
终止从调用[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)函数开始的枚举。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`[在]指向[IWbem 限定符集实例的](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)指针。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，也可以将其定义为代码中的常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对[IWbem 限定符集：：结束枚举方法的](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration)调用。

建议使用此调用，但不是必需的。 它立即释放与枚举关联的资源。

## <a name="requirements"></a>要求  

**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
**标题：** WMINet_Utils.idl  
  
**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
