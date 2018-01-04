---
title: "ICorDebugMDA::GetOSThreadId 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetOSThreadId
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baec0852e75593c8c3731b9b912d618bf83045c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmdagetosthreadid-method"></a>ICorDebugMDA::GetOSThreadId 方法
获取在其托管调试助手 (MDA) 由的操作系统 (OS) 线程标识符[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)正在执行。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pOsTid`  
 [out]指向 OS 线程标识符的指针。  
  
## <a name="remarks"></a>备注  
 OS 线程而不是 ICorDebugThread 用于允许的情况下在本机线程上或没有尚未进入托管的代码的托管线程上 MDA 激发。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugMDA 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
