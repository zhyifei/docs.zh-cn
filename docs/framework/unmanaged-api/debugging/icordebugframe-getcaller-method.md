---
title: "ICorDebugFrame::GetCaller 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetCaller
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0f426823b0076a8d6bee1b39a7cdcdf618dad90
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="a34c7-102">ICorDebugFrame::GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="a34c7-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="a34c7-103">获取一个指针指向 ICorDebugFrame 对象调用此帧的当前链中。</span><span class="sxs-lookup"><span data-stu-id="a34c7-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a34c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="a34c7-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a34c7-105">参数</span><span class="sxs-lookup"><span data-stu-id="a34c7-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="a34c7-106">[out]指向的地址的指针`ICorDebugFrame`表示调用帧的对象。</span><span class="sxs-lookup"><span data-stu-id="a34c7-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="a34c7-107">此值为调用的帧是最外层的帧的当前链中的情况下为 null。</span><span class="sxs-lookup"><span data-stu-id="a34c7-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a34c7-108">要求</span><span class="sxs-lookup"><span data-stu-id="a34c7-108">Requirements</span></span>  
 <span data-ttu-id="a34c7-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a34c7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a34c7-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a34c7-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a34c7-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a34c7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a34c7-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a34c7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
