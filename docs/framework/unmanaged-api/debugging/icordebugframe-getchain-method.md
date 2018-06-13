---
title: ICorDebugFrame::GetChain 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c020b9f6c074be11e3433939ce6898586123cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412602"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="f6bc4-102">ICorDebugFrame::GetChain 方法</span><span class="sxs-lookup"><span data-stu-id="f6bc4-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="f6bc4-103">获取一个指针指向此帧的一部分的链。</span><span class="sxs-lookup"><span data-stu-id="f6bc4-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6bc4-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6bc4-104">Syntax</span></span>  
  
```  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6bc4-105">参数</span><span class="sxs-lookup"><span data-stu-id="f6bc4-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="f6bc4-106">[out]指向一个 ICorDebugChain 对象，表示包含此帧链的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="f6bc4-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6bc4-107">要求</span><span class="sxs-lookup"><span data-stu-id="f6bc4-107">Requirements</span></span>  
 <span data-ttu-id="f6bc4-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6bc4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6bc4-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6bc4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6bc4-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6bc4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6bc4-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6bc4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
