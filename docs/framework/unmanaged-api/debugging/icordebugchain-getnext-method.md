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
ms.openlocfilehash: 839052b72d908e48a4b6f88dab05ec3c3d575d65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405406"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="8b74d-102">ICorDebugChain::GetNext 方法</span><span class="sxs-lookup"><span data-stu-id="8b74d-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="8b74d-103">获取线程的下一步帧链。</span><span class="sxs-lookup"><span data-stu-id="8b74d-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b74d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b74d-104">Syntax</span></span>  
  
```  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b74d-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b74d-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="8b74d-106">[out]指向一个表示下一个线程的帧链 ICorDebugChain 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="8b74d-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="8b74d-107">如果此链是最后一个链，`ppChain`为 null。</span><span class="sxs-lookup"><span data-stu-id="8b74d-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b74d-108">要求</span><span class="sxs-lookup"><span data-stu-id="8b74d-108">Requirements</span></span>  
 <span data-ttu-id="8b74d-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b74d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b74d-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b74d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b74d-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b74d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b74d-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b74d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
