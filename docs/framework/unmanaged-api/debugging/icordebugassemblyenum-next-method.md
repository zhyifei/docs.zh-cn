---
title: "ICorDebugAssemblyEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssemblyEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69f43a24caff7e67f307bbf4521094e8ebfd98cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="27038-102">ICorDebugAssemblyEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="27038-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="27038-103">从开始在当前光标位置处的集合获取指定的数目的程序集。</span><span class="sxs-lookup"><span data-stu-id="27038-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27038-104">语法</span><span class="sxs-lookup"><span data-stu-id="27038-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27038-105">参数</span><span class="sxs-lookup"><span data-stu-id="27038-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="27038-106">[in]要检索的程序集的数量。</span><span class="sxs-lookup"><span data-stu-id="27038-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="27038-107">[out]一个指针数组，其中每个指向表示程序集的 icor 调试程序集对象。</span><span class="sxs-lookup"><span data-stu-id="27038-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="27038-108">[out]一个指向实际返回的程序集的数量。</span><span class="sxs-lookup"><span data-stu-id="27038-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="27038-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="27038-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27038-110">惠?</span><span class="sxs-lookup"><span data-stu-id="27038-110">Requirements</span></span>  
 <span data-ttu-id="27038-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27038-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27038-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27038-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27038-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27038-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27038-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27038-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
