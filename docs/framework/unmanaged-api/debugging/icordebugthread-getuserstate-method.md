---
title: "ICorDebugThread::GetUserState 方法"
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
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9af89f355916f01fad118a4b63b57b23b2671f54
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="8dbd7-102">ICorDebugThread::GetUserState 方法</span><span class="sxs-lookup"><span data-stu-id="8dbd7-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="8dbd7-103">获取此 ICorDebugThread 的当前用户状态。</span><span class="sxs-lookup"><span data-stu-id="8dbd7-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dbd7-104">语法</span><span class="sxs-lookup"><span data-stu-id="8dbd7-104">Syntax</span></span>  
  
```  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8dbd7-105">参数</span><span class="sxs-lookup"><span data-stu-id="8dbd7-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="8dbd7-106">[out]指向 CorDebugUserState 枚举值，用于描述此线程的当前用户状态的按位组合的指针。</span><span class="sxs-lookup"><span data-stu-id="8dbd7-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dbd7-107">备注</span><span class="sxs-lookup"><span data-stu-id="8dbd7-107">Remarks</span></span>  
 <span data-ttu-id="8dbd7-108">用户状态的线程时检查由正在调试的程序，将线程的状态。</span><span class="sxs-lookup"><span data-stu-id="8dbd7-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="8dbd7-109">一个线程可能具有相同的多个状态位。</span><span class="sxs-lookup"><span data-stu-id="8dbd7-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dbd7-110">惠?</span><span class="sxs-lookup"><span data-stu-id="8dbd7-110">Requirements</span></span>  
 <span data-ttu-id="8dbd7-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8dbd7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dbd7-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8dbd7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8dbd7-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8dbd7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8dbd7-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dbd7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
