---
title: "ICorDebugThread::GetHandle 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7a932d04fef438e19176af565c92e0673339e02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="0d98a-102">ICorDebugThread::GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="0d98a-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="0d98a-103">获取此 ICorDebugThread 的活动部分当前句柄。</span><span class="sxs-lookup"><span data-stu-id="0d98a-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d98a-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d98a-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d98a-105">参数</span><span class="sxs-lookup"><span data-stu-id="0d98a-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="0d98a-106">[out]为此线程的活动部分的句柄 HTHREAD 指向的指针。</span><span class="sxs-lookup"><span data-stu-id="0d98a-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d98a-107">备注</span><span class="sxs-lookup"><span data-stu-id="0d98a-107">Remarks</span></span>  
 <span data-ttu-id="0d98a-108">在过程执行，并可能在不同线程的不同部分时可能会变化句柄。</span><span class="sxs-lookup"><span data-stu-id="0d98a-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="0d98a-109">调试 API 将拥有此句柄。</span><span class="sxs-lookup"><span data-stu-id="0d98a-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="0d98a-110">调试器应使用它之前对它进行复制。</span><span class="sxs-lookup"><span data-stu-id="0d98a-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d98a-111">惠?</span><span class="sxs-lookup"><span data-stu-id="0d98a-111">Requirements</span></span>  
 <span data-ttu-id="0d98a-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0d98a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d98a-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d98a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d98a-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d98a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d98a-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d98a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
