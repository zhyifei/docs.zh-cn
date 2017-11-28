---
title: "ICorDebugThread::CreateEval 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.CreateEval
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aebabf12e6dcf12f0e1e1f24ec2ad69ea55ec86c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="1eada-102">ICorDebugThread::CreateEval 方法</span><span class="sxs-lookup"><span data-stu-id="1eada-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="1eada-103">创建一个收集和公开此 ICorDebugThread 的功能的 ICorDebugEval 对象。</span><span class="sxs-lookup"><span data-stu-id="1eada-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eada-104">语法</span><span class="sxs-lookup"><span data-stu-id="1eada-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1eada-105">参数</span><span class="sxs-lookup"><span data-stu-id="1eada-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="1eada-106">[out]指向的地址的指针`ICorDebugEval`收集和公开此线程的功能的对象。</span><span class="sxs-lookup"><span data-stu-id="1eada-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1eada-107">备注</span><span class="sxs-lookup"><span data-stu-id="1eada-107">Remarks</span></span>  
 <span data-ttu-id="1eada-108">评估对象会在进行其计算之前将新链推送线程上。</span><span class="sxs-lookup"><span data-stu-id="1eada-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="1eada-109">则会中断当前正在执行的线程上评估完成之前计算。</span><span class="sxs-lookup"><span data-stu-id="1eada-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eada-110">要求</span><span class="sxs-lookup"><span data-stu-id="1eada-110">Requirements</span></span>  
 <span data-ttu-id="1eada-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1eada-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eada-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1eada-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1eada-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1eada-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1eada-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eada-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
