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
ms.openlocfilehash: f7d3325c8aee44849ff1fb7a6cc06a0ed7c2c6f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769105"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="98b08-102">ICorDebugThread::GetUserState 方法</span><span class="sxs-lookup"><span data-stu-id="98b08-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="98b08-103">获取此 ICorDebugThread 的当前用户状态。</span><span class="sxs-lookup"><span data-stu-id="98b08-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98b08-104">语法</span><span class="sxs-lookup"><span data-stu-id="98b08-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98b08-105">参数</span><span class="sxs-lookup"><span data-stu-id="98b08-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="98b08-106">[out]一个指向 CorDebugUserState 枚举值，用于描述此线程的当前用户状态的按位组合。</span><span class="sxs-lookup"><span data-stu-id="98b08-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98b08-107">备注</span><span class="sxs-lookup"><span data-stu-id="98b08-107">Remarks</span></span>  
 <span data-ttu-id="98b08-108">用户状态的线程时由正在调试的程序对其进行检查，将线程的状态。</span><span class="sxs-lookup"><span data-stu-id="98b08-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="98b08-109">线程可能有多个状态位设置。</span><span class="sxs-lookup"><span data-stu-id="98b08-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98b08-110">要求</span><span class="sxs-lookup"><span data-stu-id="98b08-110">Requirements</span></span>  
 <span data-ttu-id="98b08-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98b08-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98b08-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98b08-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98b08-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98b08-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98b08-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98b08-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
