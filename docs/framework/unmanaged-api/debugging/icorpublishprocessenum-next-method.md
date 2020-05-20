---
title: ICorPublishProcessEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
ms.openlocfilehash: b3bb1857075f857f62ec92ac6a2876a49655c70e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421054"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="298c3-102">ICorPublishProcessEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="298c3-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="298c3-103">从当前游标位置开始，获取集合中指定数量的进程。</span><span class="sxs-lookup"><span data-stu-id="298c3-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="298c3-104">语法</span><span class="sxs-lookup"><span data-stu-id="298c3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="298c3-105">参数</span><span class="sxs-lookup"><span data-stu-id="298c3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="298c3-106">中要检索的进程数。</span><span class="sxs-lookup"><span data-stu-id="298c3-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="298c3-107">弄一个指针，指向检索到的[ICorPublishProcess](icorpublishprocess-interface.md)对象的数组，其中每个对象都表示一个进程。</span><span class="sxs-lookup"><span data-stu-id="298c3-107">[out] A pointer to the array of retrieved [ICorPublishProcess](icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="298c3-108">弄一个指针，指向实际返回的进程数。</span><span class="sxs-lookup"><span data-stu-id="298c3-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="298c3-109">如果为1，则此值可以为 null `celt` 。</span><span class="sxs-lookup"><span data-stu-id="298c3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="298c3-110">要求</span><span class="sxs-lookup"><span data-stu-id="298c3-110">Requirements</span></span>  
 <span data-ttu-id="298c3-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="298c3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="298c3-112">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="298c3-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="298c3-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="298c3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="298c3-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="298c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="298c3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="298c3-115">See also</span></span>

- [<span data-ttu-id="298c3-116">ICorPublishProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="298c3-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)
