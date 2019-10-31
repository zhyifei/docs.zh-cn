---
title: ICorPublishEnum 接口
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
ms.openlocfilehash: 7d083655326333f18ee98f8e84fff2ed182dde6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103452"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="c886b-102">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="c886b-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="c886b-103">用作枚举器的抽象基接口，这些枚举器用于发布有关进程和应用程序域的信息。</span><span class="sxs-lookup"><span data-stu-id="c886b-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c886b-104">方法</span><span class="sxs-lookup"><span data-stu-id="c886b-104">Methods</span></span>  
  
|<span data-ttu-id="c886b-105">方法</span><span class="sxs-lookup"><span data-stu-id="c886b-105">Method</span></span>|<span data-ttu-id="c886b-106">描述</span><span class="sxs-lookup"><span data-stu-id="c886b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c886b-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="c886b-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="c886b-108">创建此 `ICorPublishEnum` 对象的副本。</span><span class="sxs-lookup"><span data-stu-id="c886b-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="c886b-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="c886b-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="c886b-110">获取枚举中的项数。</span><span class="sxs-lookup"><span data-stu-id="c886b-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="c886b-111">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="c886b-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="c886b-112">将光标移到枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="c886b-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="c886b-113">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="c886b-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="c886b-114">按指定的项数在枚举中向前移动光标。</span><span class="sxs-lookup"><span data-stu-id="c886b-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c886b-115">备注</span><span class="sxs-lookup"><span data-stu-id="c886b-115">Remarks</span></span>  
 <span data-ttu-id="c886b-116">以下枚举器派生自 `ICorPublishEnum`：</span><span class="sxs-lookup"><span data-stu-id="c886b-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="c886b-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="c886b-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="c886b-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="c886b-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="c886b-119">要求</span><span class="sxs-lookup"><span data-stu-id="c886b-119">Requirements</span></span>  
 <span data-ttu-id="c886b-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c886b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c886b-121">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="c886b-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c886b-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c886b-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c886b-123">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c886b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c886b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c886b-124">See also</span></span>

- [<span data-ttu-id="c886b-125">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="c886b-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="c886b-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="c886b-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
