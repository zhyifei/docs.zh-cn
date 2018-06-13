---
title: ICorDebugFrame::GetCaller 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2452f4be0acde300676bf56011416e0a9ef16464
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411711"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="74fbd-102">ICorDebugFrame::GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="74fbd-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="74fbd-103">获取一个指针指向 ICorDebugFrame 对象调用此帧的当前链中。</span><span class="sxs-lookup"><span data-stu-id="74fbd-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74fbd-104">语法</span><span class="sxs-lookup"><span data-stu-id="74fbd-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74fbd-105">参数</span><span class="sxs-lookup"><span data-stu-id="74fbd-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="74fbd-106">[out]指向的地址的指针`ICorDebugFrame`表示调用帧的对象。</span><span class="sxs-lookup"><span data-stu-id="74fbd-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="74fbd-107">此值为调用的帧是最外层的帧的当前链中的情况下为 null。</span><span class="sxs-lookup"><span data-stu-id="74fbd-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74fbd-108">要求</span><span class="sxs-lookup"><span data-stu-id="74fbd-108">Requirements</span></span>  
 <span data-ttu-id="74fbd-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="74fbd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74fbd-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74fbd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74fbd-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74fbd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74fbd-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74fbd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
