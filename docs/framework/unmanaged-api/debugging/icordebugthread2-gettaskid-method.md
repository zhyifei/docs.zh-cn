---
title: "ICorDebugThread2::GetTaskID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetTaskID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b94478a0dfb8cc4d90dea611620238024634799
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread2gettaskid-method"></a>ICorDebugThread2::GetTaskID 方法
获取此线程上运行的任务的标识符。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pTaskId`  
 [out]指向此 ICorDebugThread2 对象表示在线程上运行的任务标识符的指针。  
  
## <a name="remarks"></a>备注  
 如果线程是与连接关联，仅可以在线程上运行任务。 `GetTaskID`在中，则返回零`pTaskId`线程是否不与连接关联。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
