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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 900fece1dd29f73f77b85ff08e4deff1396f8aaf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484506"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="87697-102">ICorDebugThread::GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="87697-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="87697-103">获取此 ICorDebugThread 的活动部分当前句柄。</span><span class="sxs-lookup"><span data-stu-id="87697-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87697-104">语法</span><span class="sxs-lookup"><span data-stu-id="87697-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87697-105">参数</span><span class="sxs-lookup"><span data-stu-id="87697-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="87697-106">[out]此线程的活动部分的句柄 HTHREAD 指向的指针。</span><span class="sxs-lookup"><span data-stu-id="87697-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87697-107">备注</span><span class="sxs-lookup"><span data-stu-id="87697-107">Remarks</span></span>  
 <span data-ttu-id="87697-108">改变该句柄，因为该过程执行，并可能会因线程的不同部分。</span><span class="sxs-lookup"><span data-stu-id="87697-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="87697-109">调试 API 由拥有此句柄。</span><span class="sxs-lookup"><span data-stu-id="87697-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="87697-110">调试程序应使用它之前对其进行复制。</span><span class="sxs-lookup"><span data-stu-id="87697-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87697-111">要求</span><span class="sxs-lookup"><span data-stu-id="87697-111">Requirements</span></span>  
 <span data-ttu-id="87697-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87697-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87697-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87697-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87697-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87697-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87697-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87697-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
