---
title: VerifyClientKey 函数 （非托管 API 参考）
description: VerifyClientKey 函数可确保客户端密钥具有正确的安全。
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4b51fe4510f4172227d9afd049eb6815790a165
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783090"
---
# <a name="verifyclientkey-function"></a>VerifyClientKey 函数
确保客户端密钥具有正确的安全性。  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>返回值

如果函数成功，返回值是`ERROR_SUCCESS`(0)。

如果函数失败，返回值是在中定义了非零错误代码*WinError.h*。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.def  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅

- [WMI 和性能计数器 （非托管 API 参考）](index.md)
