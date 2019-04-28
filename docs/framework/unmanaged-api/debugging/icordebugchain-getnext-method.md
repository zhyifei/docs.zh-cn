---
title: ICorDebugChain::GetNext 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetNext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ecb4f8a5519fb819161ed917ad03d2537bd9551
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645235"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="767e2-102">ICorDebugChain::GetNext 方法</span><span class="sxs-lookup"><span data-stu-id="767e2-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="767e2-103">获取线程的下一帧链。</span><span class="sxs-lookup"><span data-stu-id="767e2-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="767e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="767e2-104">Syntax</span></span>  
  
```  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="767e2-105">参数</span><span class="sxs-lookup"><span data-stu-id="767e2-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="767e2-106">[out]指向一个 ICorDebugChain 对象，表示下一个线程的帧链的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="767e2-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="767e2-107">如果此证书链的最后一个链`ppChain`为 null。</span><span class="sxs-lookup"><span data-stu-id="767e2-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="767e2-108">要求</span><span class="sxs-lookup"><span data-stu-id="767e2-108">Requirements</span></span>  
 <span data-ttu-id="767e2-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="767e2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="767e2-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="767e2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="767e2-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="767e2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="767e2-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="767e2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
