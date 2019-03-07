---
title: ICorDebugFrame::GetCallee 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a179b68e2196eeadc712ae8f7d023b2943533335
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471064"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="d79b9-102">ICorDebugFrame::GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="d79b9-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="d79b9-103">获取一个指针指向 ICorDebugFrame 对象调用此帧当前链中。</span><span class="sxs-lookup"><span data-stu-id="d79b9-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="d79b9-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d79b9-105">参数</span><span class="sxs-lookup"><span data-stu-id="d79b9-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="d79b9-106">[out]指向的地址的指针`ICorDebugFrame`对象，表示调用的帧。</span><span class="sxs-lookup"><span data-stu-id="d79b9-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="d79b9-107">此值为 null，如果调用的帧是当前的链中的最内层帧。</span><span class="sxs-lookup"><span data-stu-id="d79b9-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d79b9-108">要求</span><span class="sxs-lookup"><span data-stu-id="d79b9-108">Requirements</span></span>  
 <span data-ttu-id="d79b9-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d79b9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d79b9-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d79b9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d79b9-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d79b9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d79b9-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d79b9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
