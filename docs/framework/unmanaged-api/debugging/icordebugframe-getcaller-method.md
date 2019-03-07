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
ms.openlocfilehash: 82902e6a395fe62464065ccea4cca5b52c960f0d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492213"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="5b4e3-102">ICorDebugFrame::GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="5b4e3-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="5b4e3-103">获取一个指针指向 ICorDebugFrame 对象中调用此帧的当前链。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b4e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b4e3-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b4e3-105">参数</span><span class="sxs-lookup"><span data-stu-id="5b4e3-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="5b4e3-106">[out]指向的地址的指针`ICorDebugFrame`对象，表示调用的帧。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="5b4e3-107">此值为 null，如果调用的帧是当前的链中的最外层帧。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b4e3-108">要求</span><span class="sxs-lookup"><span data-stu-id="5b4e3-108">Requirements</span></span>  
 <span data-ttu-id="5b4e3-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b4e3-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b4e3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b4e3-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b4e3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b4e3-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b4e3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
