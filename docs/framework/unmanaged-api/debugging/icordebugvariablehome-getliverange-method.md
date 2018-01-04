---
title: "IcorDebugVariableHome::GetLiveRange 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetLiveRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bb86921be3398e6e9653838c1aec6b40ca86469
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="e7799-102">IcorDebugVariableHome::GetLiveRange 方法</span><span class="sxs-lookup"><span data-stu-id="e7799-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="e7799-103">获取对其此变量是实时的本机范围。</span><span class="sxs-lookup"><span data-stu-id="e7799-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7799-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7799-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7799-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7799-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="e7799-106">[out]从该处的变量是第一个实时逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="e7799-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="e7799-107">[out]从该处的变量是最后一个实时点后立即逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="e7799-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7799-108">惠?</span><span class="sxs-lookup"><span data-stu-id="e7799-108">Requirements</span></span>  
 <span data-ttu-id="e7799-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7799-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7799-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7799-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7799-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7799-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7799-112">**.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7799-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7799-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7799-113">See Also</span></span>  
 [<span data-ttu-id="e7799-114">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="e7799-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
