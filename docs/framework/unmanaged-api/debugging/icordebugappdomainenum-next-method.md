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
ms.openlocfilehash: 17bf4c92b1e1347a8fe790c8df5937de0f95df4d
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895088"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="1272d-102">ICorDebugAppDomainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="1272d-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="1272d-103">从当前游标位置开始，获取集合中指定数量的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="1272d-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1272d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1272d-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1272d-105">参数</span><span class="sxs-lookup"><span data-stu-id="1272d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1272d-106">中要检索的应用程序域的数量。</span><span class="sxs-lookup"><span data-stu-id="1272d-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="1272d-107">弄指针的数组，其中每个都指向表示应用程序域的 ICorDebugAppDomain 对象。</span><span class="sxs-lookup"><span data-stu-id="1272d-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1272d-108">弄一个指针，指向实际返回的应用程序域的数量。</span><span class="sxs-lookup"><span data-stu-id="1272d-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="1272d-109">如果`celt`为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="1272d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1272d-110">要求</span><span class="sxs-lookup"><span data-stu-id="1272d-110">Requirements</span></span>  
 <span data-ttu-id="1272d-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1272d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1272d-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1272d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1272d-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1272d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1272d-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1272d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
