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
ms.openlocfilehash: a7430a420769a2d7952caf93af3b1412094483f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="a16ff-102">ICorDebugAssemblyEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="a16ff-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="a16ff-103">从开始在当前光标位置处的集合获取指定的数目的程序集。</span><span class="sxs-lookup"><span data-stu-id="a16ff-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a16ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="a16ff-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a16ff-105">参数</span><span class="sxs-lookup"><span data-stu-id="a16ff-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a16ff-106">[in]要检索的程序集的数量。</span><span class="sxs-lookup"><span data-stu-id="a16ff-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="a16ff-107">[out]一个指针数组，其中每个指向表示程序集的 icor 调试程序集对象。</span><span class="sxs-lookup"><span data-stu-id="a16ff-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a16ff-108">[out]一个指向实际返回的程序集的数量。</span><span class="sxs-lookup"><span data-stu-id="a16ff-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="a16ff-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="a16ff-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a16ff-110">要求</span><span class="sxs-lookup"><span data-stu-id="a16ff-110">Requirements</span></span>  
 <span data-ttu-id="a16ff-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a16ff-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a16ff-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a16ff-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a16ff-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a16ff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a16ff-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a16ff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
