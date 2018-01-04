---
title: "ICorDebugModule::IsInMemory 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.IsInMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 448458874c4de96503261bc0fe34fae160395c49
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="6a88a-102">ICorDebugModule::IsInMemory 方法</span><span class="sxs-lookup"><span data-stu-id="6a88a-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="6a88a-103">获取一个值，该值指示仅在内存中是否存在此模块。</span><span class="sxs-lookup"><span data-stu-id="6a88a-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a88a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a88a-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a88a-105">参数</span><span class="sxs-lookup"><span data-stu-id="6a88a-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="6a88a-106">[out]`true`如果此模块只存在于内存; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="6a88a-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a88a-107">备注</span><span class="sxs-lookup"><span data-stu-id="6a88a-107">Remarks</span></span>  
 <span data-ttu-id="6a88a-108">公共语言运行时 (CLR) 支持原始字节流中的模块加载。</span><span class="sxs-lookup"><span data-stu-id="6a88a-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="6a88a-109">进行此类模块称为*内存中模块*和磁盘上不存在。</span><span class="sxs-lookup"><span data-stu-id="6a88a-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a88a-110">惠?</span><span class="sxs-lookup"><span data-stu-id="6a88a-110">Requirements</span></span>  
 <span data-ttu-id="6a88a-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6a88a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a88a-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a88a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a88a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a88a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a88a-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a88a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a88a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a88a-115">See Also</span></span>  
    
 
