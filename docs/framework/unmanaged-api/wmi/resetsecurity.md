---
title: ResetSecurity 函数 （非托管 API 参考）
description: ResetSecurity 函数将分配给当前线程的模拟令牌。
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3d87fa10dafba326147bcaa39836b631291ef1c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783131"
---
# <a name="resetsecurity-function"></a>ResetSecurity 函数
将提供的模拟令牌分配给当前线程。   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a>参数

`token`  
[in]要与当前线程关联的模拟令牌。 其值可为 `null`。 

## <a name="return-value"></a>返回值

如果函数成功，返回值是`S_OK`(0)。

如果函数失败，返回值是一个非零错误代码。 若要获得扩展错误信息，请调用[GetErrorInfo](geterrorinfo.md)函数。
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅

- [WMI 和性能计数器 （非托管 API 参考）](index.md)
