---
title: ICorDebugThread::GetUserState 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4deaa3ab4b14fbd32d45841966cfac9e33b9f31
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487845"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="35c62-102">ICorDebugThread::GetUserState 方法</span><span class="sxs-lookup"><span data-stu-id="35c62-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="35c62-103">获取此 ICorDebugThread 的当前用户状态。</span><span class="sxs-lookup"><span data-stu-id="35c62-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35c62-104">语法</span><span class="sxs-lookup"><span data-stu-id="35c62-104">Syntax</span></span>  
  
```  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35c62-105">参数</span><span class="sxs-lookup"><span data-stu-id="35c62-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="35c62-106">[out]一个指向 CorDebugUserState 枚举值，用于描述此线程的当前用户状态的按位组合。</span><span class="sxs-lookup"><span data-stu-id="35c62-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35c62-107">备注</span><span class="sxs-lookup"><span data-stu-id="35c62-107">Remarks</span></span>  
 <span data-ttu-id="35c62-108">用户状态的线程时由正在调试的程序对其进行检查，将线程的状态。</span><span class="sxs-lookup"><span data-stu-id="35c62-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="35c62-109">线程可能有多个状态位设置。</span><span class="sxs-lookup"><span data-stu-id="35c62-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35c62-110">要求</span><span class="sxs-lookup"><span data-stu-id="35c62-110">Requirements</span></span>  
 <span data-ttu-id="35c62-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35c62-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35c62-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35c62-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35c62-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35c62-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35c62-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35c62-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
