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
ms.openlocfilehash: 8554bf2667f3542b3164b60eaed998087fe175d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="291d1-102">IcorDebugVariableHome::GetLiveRange 方法</span><span class="sxs-lookup"><span data-stu-id="291d1-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="291d1-103">获取对其此变量是实时的本机范围。</span><span class="sxs-lookup"><span data-stu-id="291d1-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="291d1-104">语法</span><span class="sxs-lookup"><span data-stu-id="291d1-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="291d1-105">参数</span><span class="sxs-lookup"><span data-stu-id="291d1-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="291d1-106">[out]从该处的变量是第一个实时逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="291d1-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="291d1-107">[out]从该处的变量是最后一个实时点后立即逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="291d1-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="291d1-108">要求</span><span class="sxs-lookup"><span data-stu-id="291d1-108">Requirements</span></span>  
 <span data-ttu-id="291d1-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="291d1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="291d1-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="291d1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="291d1-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="291d1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="291d1-112">**.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="291d1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="291d1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="291d1-113">See Also</span></span>  
 [<span data-ttu-id="291d1-114">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="291d1-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
