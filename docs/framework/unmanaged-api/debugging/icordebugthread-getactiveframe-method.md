---
title: "ICorDebugThread::GetActiveFrame 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 441f97ebbaf95a8b6b6e14c8372893a83f6299a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="06af8-102">ICorDebugThread::GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="06af8-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="06af8-103">获取此 ICorDebugThread 对象上活动的 （最新） 帧的接口指针。</span><span class="sxs-lookup"><span data-stu-id="06af8-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06af8-104">语法</span><span class="sxs-lookup"><span data-stu-id="06af8-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06af8-105">参数</span><span class="sxs-lookup"><span data-stu-id="06af8-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="06af8-106">[out]指向表示的帧 ICorDebugFrame 接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="06af8-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06af8-107">备注</span><span class="sxs-lookup"><span data-stu-id="06af8-107">Remarks</span></span>  
 <span data-ttu-id="06af8-108">`ppFrame`参数为 null，如果没有帧为当前处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="06af8-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06af8-109">惠?</span><span class="sxs-lookup"><span data-stu-id="06af8-109">Requirements</span></span>  
 <span data-ttu-id="06af8-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06af8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06af8-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06af8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06af8-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06af8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06af8-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06af8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
