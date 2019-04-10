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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1eac0b9fe252e476f8ff781f2181a203886d3beb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160129"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="2eadc-102">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="2eadc-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="2eadc-103">提供有关进程和应用程序域的信息的发布中使用的枚举器的抽象基接口。</span><span class="sxs-lookup"><span data-stu-id="2eadc-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2eadc-104">方法</span><span class="sxs-lookup"><span data-stu-id="2eadc-104">Methods</span></span>  
  
|<span data-ttu-id="2eadc-105">方法</span><span class="sxs-lookup"><span data-stu-id="2eadc-105">Method</span></span>|<span data-ttu-id="2eadc-106">描述</span><span class="sxs-lookup"><span data-stu-id="2eadc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2eadc-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="2eadc-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="2eadc-108">创建一份`ICorPublishEnum`对象。</span><span class="sxs-lookup"><span data-stu-id="2eadc-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="2eadc-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="2eadc-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="2eadc-110">枚举中获取项的数目。</span><span class="sxs-lookup"><span data-stu-id="2eadc-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="2eadc-111">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="2eadc-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="2eadc-112">将的光标移到枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="2eadc-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="2eadc-113">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="2eadc-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="2eadc-114">将光标向前移动在枚举中指定数目的项。</span><span class="sxs-lookup"><span data-stu-id="2eadc-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2eadc-115">备注</span><span class="sxs-lookup"><span data-stu-id="2eadc-115">Remarks</span></span>  
 <span data-ttu-id="2eadc-116">派生自以下枚举器`ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="2eadc-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
-   [<span data-ttu-id="2eadc-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="2eadc-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [<span data-ttu-id="2eadc-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="2eadc-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="2eadc-119">要求</span><span class="sxs-lookup"><span data-stu-id="2eadc-119">Requirements</span></span>  
 <span data-ttu-id="2eadc-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2eadc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2eadc-121">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="2eadc-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2eadc-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2eadc-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2eadc-123">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="2eadc-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2eadc-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="2eadc-124">See also</span></span>

- [<span data-ttu-id="2eadc-125">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="2eadc-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="2eadc-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="2eadc-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
