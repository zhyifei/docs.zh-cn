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
ms.openlocfilehash: 06ff8f0f13d7710d2d3d59aac4b5fdcadfe707be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418387"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="8060e-102">ICorDebugThread::GetUserState 方法</span><span class="sxs-lookup"><span data-stu-id="8060e-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="8060e-103">获取此 ICorDebugThread 的当前用户状态。</span><span class="sxs-lookup"><span data-stu-id="8060e-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8060e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8060e-104">Syntax</span></span>  
  
```  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8060e-105">参数</span><span class="sxs-lookup"><span data-stu-id="8060e-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="8060e-106">[out]指向 CorDebugUserState 枚举值，用于描述此线程的当前用户状态的按位组合的指针。</span><span class="sxs-lookup"><span data-stu-id="8060e-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8060e-107">备注</span><span class="sxs-lookup"><span data-stu-id="8060e-107">Remarks</span></span>  
 <span data-ttu-id="8060e-108">用户状态的线程时检查由正在调试的程序，将线程的状态。</span><span class="sxs-lookup"><span data-stu-id="8060e-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="8060e-109">一个线程可能具有相同的多个状态位。</span><span class="sxs-lookup"><span data-stu-id="8060e-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8060e-110">要求</span><span class="sxs-lookup"><span data-stu-id="8060e-110">Requirements</span></span>  
 <span data-ttu-id="8060e-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8060e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8060e-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8060e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8060e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8060e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8060e-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8060e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
