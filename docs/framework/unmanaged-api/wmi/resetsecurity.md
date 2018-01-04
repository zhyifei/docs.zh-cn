---
title: "ResetSecurity 函数 （非托管 API 参考）"
description: "ResetSecurity 函数将模拟令牌分配给当前线程。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ResetSecurity
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ResetSecurity
helpviewer_keywords: ResetSecurity function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bacee65633d25e705d978d3902a6804516a88bf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="resetsecurity-function"></a>ResetSecurity 函数
将提供的模拟令牌分配给当前线程。   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a>参数

`token`  
[in]要将与当前线程相关联的模拟令牌。 其值可为 `null`。 

## <a name="return-value"></a>返回值

如果函数成功，则返回值是`S_OK`(0)。

如果函数失败，返回值将为非零错误代码。 若要获得扩展的错误信息，调用[GetErrorInfo](geterrorinfo.md)函数。
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
