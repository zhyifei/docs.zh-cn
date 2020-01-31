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
ms.openlocfilehash: 084af87acd73ef65739ba69ef2bd66d10d7c27c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790514"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="bef00-102">ICorPublishProcessEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="bef00-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="bef00-103">从当前游标位置开始，获取集合中指定数量的进程。</span><span class="sxs-lookup"><span data-stu-id="bef00-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bef00-104">语法</span><span class="sxs-lookup"><span data-stu-id="bef00-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bef00-105">参数</span><span class="sxs-lookup"><span data-stu-id="bef00-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="bef00-106">中要检索的进程数。</span><span class="sxs-lookup"><span data-stu-id="bef00-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="bef00-107">弄一个指针，指向检索到的[ICorPublishProcess](icorpublishprocess-interface.md)对象的数组，其中每个对象都表示一个进程。</span><span class="sxs-lookup"><span data-stu-id="bef00-107">[out] A pointer to the array of retrieved [ICorPublishProcess](icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="bef00-108">弄一个指针，指向实际返回的进程数。</span><span class="sxs-lookup"><span data-stu-id="bef00-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="bef00-109">如果 `celt` 为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="bef00-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bef00-110">需求</span><span class="sxs-lookup"><span data-stu-id="bef00-110">Requirements</span></span>  
 <span data-ttu-id="bef00-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bef00-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bef00-112">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="bef00-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="bef00-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bef00-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bef00-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bef00-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bef00-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bef00-115">See also</span></span>

- [<span data-ttu-id="bef00-116">ICorPublishProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="bef00-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)
