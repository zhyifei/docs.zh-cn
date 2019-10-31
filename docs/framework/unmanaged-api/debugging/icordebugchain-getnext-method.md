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
ms.openlocfilehash: 132734dfb6ba9d70836638ab67564fc215e9bc40
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192125"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="380e1-102">ICorDebugChain::GetNext 方法</span><span class="sxs-lookup"><span data-stu-id="380e1-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="380e1-103">获取线程的下一个帧链。</span><span class="sxs-lookup"><span data-stu-id="380e1-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="380e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="380e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="380e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="380e1-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="380e1-106">弄指向 ICorDebugChain 对象的地址的指针，该对象表示线程的下一个帧链。</span><span class="sxs-lookup"><span data-stu-id="380e1-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="380e1-107">如果此链是最后一个链，则 `ppChain` 为 null。</span><span class="sxs-lookup"><span data-stu-id="380e1-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="380e1-108">要求</span><span class="sxs-lookup"><span data-stu-id="380e1-108">Requirements</span></span>  
 <span data-ttu-id="380e1-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="380e1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="380e1-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="380e1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="380e1-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="380e1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="380e1-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="380e1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
