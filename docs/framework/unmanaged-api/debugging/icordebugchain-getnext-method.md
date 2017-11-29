---
title: "ICorDebugChain::GetNext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetNext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1955d503b612ce4b3a6c4eaaae2003b652f38fd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="67996-102">ICorDebugChain::GetNext 方法</span><span class="sxs-lookup"><span data-stu-id="67996-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="67996-103">获取线程的下一步帧链。</span><span class="sxs-lookup"><span data-stu-id="67996-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67996-104">语法</span><span class="sxs-lookup"><span data-stu-id="67996-104">Syntax</span></span>  
  
```  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67996-105">参数</span><span class="sxs-lookup"><span data-stu-id="67996-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="67996-106">[out]指向一个表示下一个线程的帧链 ICorDebugChain 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="67996-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="67996-107">如果此链是最后一个链，`ppChain`为 null。</span><span class="sxs-lookup"><span data-stu-id="67996-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67996-108">要求</span><span class="sxs-lookup"><span data-stu-id="67996-108">Requirements</span></span>  
 <span data-ttu-id="67996-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67996-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67996-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67996-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67996-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67996-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67996-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67996-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
