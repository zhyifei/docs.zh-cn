---
title: ICorDebugThread::GetHandle 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 16aafa439fc81c3606f98ca2ba860316ec46e0db
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379742"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="f081b-102">ICorDebugThread::GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="f081b-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="f081b-103">获取此 ICorDebugThread 的活动部分的当前句柄。</span><span class="sxs-lookup"><span data-stu-id="f081b-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f081b-104">语法</span><span class="sxs-lookup"><span data-stu-id="f081b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f081b-105">参数</span><span class="sxs-lookup"><span data-stu-id="f081b-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="f081b-106">弄指向 HTHREAD 的指针，该指针是此线程的活动部分的句柄。</span><span class="sxs-lookup"><span data-stu-id="f081b-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f081b-107">备注</span><span class="sxs-lookup"><span data-stu-id="f081b-107">Remarks</span></span>  
 <span data-ttu-id="f081b-108">该句柄可能在进程执行时发生更改，并且可能不同于线程的不同部分。</span><span class="sxs-lookup"><span data-stu-id="f081b-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="f081b-109">此句柄属于调试 API。</span><span class="sxs-lookup"><span data-stu-id="f081b-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="f081b-110">调试器应在使用之前进行复制。</span><span class="sxs-lookup"><span data-stu-id="f081b-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f081b-111">要求</span><span class="sxs-lookup"><span data-stu-id="f081b-111">Requirements</span></span>  
 <span data-ttu-id="f081b-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f081b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f081b-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f081b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f081b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f081b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f081b-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f081b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
