---
title: "ICorDebugChain::IsManaged 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.IsManaged
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e9937222c215d22ef4ef572873385f279e7ba86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="d56cf-102">ICorDebugChain::IsManaged 方法</span><span class="sxs-lookup"><span data-stu-id="d56cf-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="d56cf-103">获取一个值，该值指示此链是否正在运行托管的代码。</span><span class="sxs-lookup"><span data-stu-id="d56cf-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d56cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="d56cf-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d56cf-105">参数</span><span class="sxs-lookup"><span data-stu-id="d56cf-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="d56cf-106">[out]`true`如果此证书链正在运行托管的代码; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="d56cf-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d56cf-107">惠?</span><span class="sxs-lookup"><span data-stu-id="d56cf-107">Requirements</span></span>  
 <span data-ttu-id="d56cf-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d56cf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d56cf-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d56cf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d56cf-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d56cf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d56cf-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d56cf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
