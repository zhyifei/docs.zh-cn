---
title: "ICorPublishEnum 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishEnum
helpviewer_keywords: ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7034945824e439b42134f8ea3c13bfaf73dbb649
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="957a4-102">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="957a4-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="957a4-103">在发布有关进程和应用程序域的信息中使用的枚举数作为抽象的基接口。</span><span class="sxs-lookup"><span data-stu-id="957a4-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="957a4-104">方法</span><span class="sxs-lookup"><span data-stu-id="957a4-104">Methods</span></span>  
  
|<span data-ttu-id="957a4-105">方法</span><span class="sxs-lookup"><span data-stu-id="957a4-105">Method</span></span>|<span data-ttu-id="957a4-106">描述</span><span class="sxs-lookup"><span data-stu-id="957a4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="957a4-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="957a4-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="957a4-108">创建一份`ICorPublishEnum`对象。</span><span class="sxs-lookup"><span data-stu-id="957a4-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="957a4-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="957a4-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="957a4-110">枚举中获取项的数目。</span><span class="sxs-lookup"><span data-stu-id="957a4-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="957a4-111">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="957a4-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="957a4-112">将光标移到枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="957a4-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="957a4-113">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="957a4-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="957a4-114">将光标向前移动在枚举中指定数目的项。</span><span class="sxs-lookup"><span data-stu-id="957a4-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="957a4-115">备注</span><span class="sxs-lookup"><span data-stu-id="957a4-115">Remarks</span></span>  
 <span data-ttu-id="957a4-116">以下枚举器派生自`ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="957a4-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
-   [<span data-ttu-id="957a4-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="957a4-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [<span data-ttu-id="957a4-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="957a4-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="957a4-119">要求</span><span class="sxs-lookup"><span data-stu-id="957a4-119">Requirements</span></span>  
 <span data-ttu-id="957a4-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="957a4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="957a4-121">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="957a4-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="957a4-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="957a4-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="957a4-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="957a4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957a4-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="957a4-124">See Also</span></span>  
 [<span data-ttu-id="957a4-125">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="957a4-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)  
 [<span data-ttu-id="957a4-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="957a4-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
