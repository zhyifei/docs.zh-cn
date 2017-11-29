---
title: "ICorDebugAppDomainEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomainEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10d53ebac99942ac9376041f217df53965bdbb2f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="57468-102">ICorDebugAppDomainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="57468-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="57468-103">从开始在当前光标位置处的集合获取指定的数目的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="57468-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57468-104">语法</span><span class="sxs-lookup"><span data-stu-id="57468-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57468-105">参数</span><span class="sxs-lookup"><span data-stu-id="57468-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="57468-106">[in]要检索的应用程序域的数量。</span><span class="sxs-lookup"><span data-stu-id="57468-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="57468-107">[out]一个指针数组，其中每个指向一个 ICorDebugAppDomain 对象，表示应用程序域。</span><span class="sxs-lookup"><span data-stu-id="57468-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="57468-108">[out]一个指向实际返回的应用程序域的数量。</span><span class="sxs-lookup"><span data-stu-id="57468-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="57468-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="57468-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57468-110">要求</span><span class="sxs-lookup"><span data-stu-id="57468-110">Requirements</span></span>  
 <span data-ttu-id="57468-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="57468-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57468-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57468-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57468-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57468-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57468-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57468-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
