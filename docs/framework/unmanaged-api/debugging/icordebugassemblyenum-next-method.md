---
title: ICorDebugAssemblyEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b94ae83f2fb5f71abb8cb3a5c96aac9e268fc5db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405283"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="cbea6-102">ICorDebugAssemblyEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="cbea6-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="cbea6-103">从开始在当前光标位置处的集合获取指定的数目的程序集。</span><span class="sxs-lookup"><span data-stu-id="cbea6-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbea6-104">语法</span><span class="sxs-lookup"><span data-stu-id="cbea6-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbea6-105">参数</span><span class="sxs-lookup"><span data-stu-id="cbea6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cbea6-106">[in]要检索的程序集的数量。</span><span class="sxs-lookup"><span data-stu-id="cbea6-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="cbea6-107">[out]一个指针数组，其中每个指向表示程序集的 icor 调试程序集对象。</span><span class="sxs-lookup"><span data-stu-id="cbea6-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="cbea6-108">[out]一个指向实际返回的程序集的数量。</span><span class="sxs-lookup"><span data-stu-id="cbea6-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="cbea6-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="cbea6-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbea6-110">要求</span><span class="sxs-lookup"><span data-stu-id="cbea6-110">Requirements</span></span>  
 <span data-ttu-id="cbea6-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cbea6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbea6-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbea6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbea6-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbea6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbea6-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbea6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
