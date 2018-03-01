---
title: "ICorDebugThread::EnumerateChains 方法"
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
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e6a9637edb4a846b4d10dd6565533a9219ad558
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenumeratechains-method"></a>ICorDebugThread::EnumerateChains 方法
获取包含此 ICorDebugThread 对象中的所有堆栈链的 ICorDebugChainEnum 枚举的接口指针。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppChains`  
 [out]指向的地址的指针`ICorDebugChainEnum`开始 （即，最近） 活动链，此线程中链接的对象，它允许的所有堆栈的枚举。  
  
## <a name="remarks"></a>备注  
 堆栈链表示线程的物理调用堆栈。 以下情况下创建堆栈链边界：  
  
-   托管到非托管或非托管到托管的转换。  
  
-   上下文切换。  
  
-   一个调试器的用户线程劫持。  
  
 在为单一上下文中运行纯托管的代码的线程简单的情况下，存在一对一的对应关系将存在线程堆栈链之间。  
  
 调试器可能需要重新排列为逻辑调用堆栈的所有线程的物理调用堆栈。 这将涉及对所有线程的链通过其调用方/被调用方关系进行排序和重新分组。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
