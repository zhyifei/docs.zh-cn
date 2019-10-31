---
title: ICorDebugThread::CreateEval 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
ms.openlocfilehash: 0c622e0eba27f501446d2b7d9d264ee0834e869c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133621"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="044a4-102">ICorDebugThread::CreateEval 方法</span><span class="sxs-lookup"><span data-stu-id="044a4-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="044a4-103">创建一个 ICorDebugEval 对象，该对象收集并公开此 ICorDebugThread 的功能。</span><span class="sxs-lookup"><span data-stu-id="044a4-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="044a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="044a4-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="044a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="044a4-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="044a4-106">弄指向收集并公开此线程功能的 `ICorDebugEval` 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="044a4-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="044a4-107">备注</span><span class="sxs-lookup"><span data-stu-id="044a4-107">Remarks</span></span>  
 <span data-ttu-id="044a4-108">计算对象在计算之前会在线程上推送新的链。</span><span class="sxs-lookup"><span data-stu-id="044a4-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="044a4-109">这会中断当前正在线程上执行的计算，直到完成计算。</span><span class="sxs-lookup"><span data-stu-id="044a4-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="044a4-110">要求</span><span class="sxs-lookup"><span data-stu-id="044a4-110">Requirements</span></span>  
 <span data-ttu-id="044a4-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="044a4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="044a4-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="044a4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="044a4-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="044a4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="044a4-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="044a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
