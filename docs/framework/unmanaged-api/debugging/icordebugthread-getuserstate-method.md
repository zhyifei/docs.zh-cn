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
ms.openlocfilehash: d1ff3427feb5dc8395bbb2fda78e3e93e1a1a8f0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378849"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="7e49d-102">ICorDebugThread::GetUserState 方法</span><span class="sxs-lookup"><span data-stu-id="7e49d-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="7e49d-103">获取此 ICorDebugThread 的当前用户状态。</span><span class="sxs-lookup"><span data-stu-id="7e49d-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e49d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7e49d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e49d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7e49d-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="7e49d-106">弄一个指针，指向用于描述此线程当前用户状态的 CorDebugUserState 枚举值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="7e49d-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e49d-107">备注</span><span class="sxs-lookup"><span data-stu-id="7e49d-107">Remarks</span></span>  
 <span data-ttu-id="7e49d-108">线程的用户状态是由正在调试的程序检查的线程的状态。</span><span class="sxs-lookup"><span data-stu-id="7e49d-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="7e49d-109">线程可能会设置多个状态位。</span><span class="sxs-lookup"><span data-stu-id="7e49d-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e49d-110">要求</span><span class="sxs-lookup"><span data-stu-id="7e49d-110">Requirements</span></span>  
 <span data-ttu-id="7e49d-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e49d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e49d-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e49d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e49d-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e49d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e49d-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e49d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
