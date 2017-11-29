---
title: "ICorDebugThread::CreateStepper 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.CreateStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b66c3e536104a46b65c92fe038fb5a92d79db299
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="e622c-102">ICorDebugThread::CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="e622c-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="e622c-103">创建允许逐句通过此 ICorDebugThread 活动帧的 ICorDebugStepper 对象。</span><span class="sxs-lookup"><span data-stu-id="e622c-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e622c-104">语法</span><span class="sxs-lookup"><span data-stu-id="e622c-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e622c-105">参数</span><span class="sxs-lookup"><span data-stu-id="e622c-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="e622c-106">[out]指向的地址的指针`ICorDebugStepper`允许逐句通过此线程的活动帧的对象。</span><span class="sxs-lookup"><span data-stu-id="e622c-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e622c-107">备注</span><span class="sxs-lookup"><span data-stu-id="e622c-107">Remarks</span></span>  
 <span data-ttu-id="e622c-108">活动帧可能非托管的代码。</span><span class="sxs-lookup"><span data-stu-id="e622c-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="e622c-109">`ICorDebugStepper`必须使用接口来执行实际单步执行。</span><span class="sxs-lookup"><span data-stu-id="e622c-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e622c-110">要求</span><span class="sxs-lookup"><span data-stu-id="e622c-110">Requirements</span></span>  
 <span data-ttu-id="e622c-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e622c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e622c-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e622c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e622c-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e622c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e622c-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e622c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
