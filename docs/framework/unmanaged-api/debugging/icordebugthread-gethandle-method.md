---
title: "ICorDebugThread::GetHandle 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c7a932d04fef438e19176af565c92e0673339e02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgethandle-method"></a>ICorDebugThread::GetHandle 方法
获取此 ICorDebugThread 的活动部分当前句柄。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
#### <a name="parameters"></a>参数  
 `phThreadHandle`  
 [out]为此线程的活动部分的句柄 HTHREAD 指向的指针。  
  
## <a name="remarks"></a>备注  
 在过程执行，并可能在不同线程的不同部分时可能会变化句柄。  
  
 调试 API 将拥有此句柄。 调试器应使用它之前对它进行复制。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
