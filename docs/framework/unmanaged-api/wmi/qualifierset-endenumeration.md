---
title: "QualifierSet_EndEnumeration 函数 （非托管 API 参考）"
description: "QualifierSet_EndEnumeration 函数将终止枚举。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d8e6bb24eb471d807af2493f82b6be4f644124f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetendenumeration-function"></a>QualifierSet_EndEnumeration 函数
终止通过调用开始枚举[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)函数。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`   
[in]指向的指针[IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)实例。

## <a name="return-value"></a>返回值

此函数返回以下值用定义*WbemCli.h*标头文件，也可以为常量在中定义你的代码：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx)方法。

此调用是建议，但不是要求。 它立即释放枚举与关联的资源。

## <a name="requirements"></a>惠?  

**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
**标头：** WMINet_Utils.idl  
  
**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
