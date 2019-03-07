---
title: ICorDebugAppDomainEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fefc933cc84fede1f3dea16d4b13e09801a96e0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497348"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="46a95-102">ICorDebugAppDomainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="46a95-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="46a95-103">从集合中，从当前光标位置开始获取指定的数目的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="46a95-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a95-104">语法</span><span class="sxs-lookup"><span data-stu-id="46a95-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46a95-105">参数</span><span class="sxs-lookup"><span data-stu-id="46a95-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="46a95-106">[in]要检索的应用程序域数。</span><span class="sxs-lookup"><span data-stu-id="46a95-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="46a95-107">[out]一个指针数组，其中每个指向一个 ICorDebugAppDomain 对象，表示应用程序域。</span><span class="sxs-lookup"><span data-stu-id="46a95-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="46a95-108">[out]指向实际返回的应用程序域数的指针。</span><span class="sxs-lookup"><span data-stu-id="46a95-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="46a95-109">此值可能为 null 如果`celt`是其中一个。</span><span class="sxs-lookup"><span data-stu-id="46a95-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46a95-110">要求</span><span class="sxs-lookup"><span data-stu-id="46a95-110">Requirements</span></span>  
 <span data-ttu-id="46a95-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="46a95-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46a95-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46a95-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46a95-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46a95-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46a95-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46a95-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
