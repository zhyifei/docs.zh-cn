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
ms.openlocfilehash: 990786fbb3cc853f7f399d60fa686bb5d60018af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745695"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="f5785-102">ICorDebugChain::GetNext 方法</span><span class="sxs-lookup"><span data-stu-id="f5785-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="f5785-103">获取线程的下一帧链。</span><span class="sxs-lookup"><span data-stu-id="f5785-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5785-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5785-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5785-105">参数</span><span class="sxs-lookup"><span data-stu-id="f5785-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="f5785-106">[out]指向一个 ICorDebugChain 对象，表示下一个线程的帧链的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="f5785-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="f5785-107">如果此证书链的最后一个链`ppChain`为 null。</span><span class="sxs-lookup"><span data-stu-id="f5785-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5785-108">要求</span><span class="sxs-lookup"><span data-stu-id="f5785-108">Requirements</span></span>  
 <span data-ttu-id="f5785-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5785-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5785-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5785-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5785-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5785-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5785-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5785-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
