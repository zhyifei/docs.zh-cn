---
title: ICorPublishAppDomainEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: 6f7f400c51ded0b98c0c2286cb6f90bbd77e47d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178401"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="0d0d0-102">ICorPublishAppDomainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="0d0d0-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="0d0d0-103">从当前位置开始获取进程中当前存在的指定数量的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d0d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d0d0-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d0d0-105">parameters</span><span class="sxs-lookup"><span data-stu-id="0d0d0-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0d0d0-106">[在]要检索的元素数。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="0d0d0-107">[出]指向检索到[的 ICorPublishAppDomain](icorpublishappdomain-interface.md)对象的数组的指针，每个对象都表示一个应用程序域。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0d0d0-108">[出]指向实际返回的应用程序域数的指针。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="0d0d0-109">此值可以是 null（如果是`celt`1）。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d0d0-110">要求</span><span class="sxs-lookup"><span data-stu-id="0d0d0-110">Requirements</span></span>  
 <span data-ttu-id="0d0d0-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0d0d0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d0d0-112">**标题：** 科尔普布.idl， 科尔普布.h</span><span class="sxs-lookup"><span data-stu-id="0d0d0-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0d0d0-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d0d0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d0d0-114">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d0d0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d0d0-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d0d0-115">See also</span></span>

- [<span data-ttu-id="0d0d0-116">ICorPublishAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="0d0d0-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)
