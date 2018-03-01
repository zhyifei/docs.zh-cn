---
title: "ICorPublishProcessEnum 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a3598af7dcdfa106b50e884c0f9d3752a595da89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="02ec1-102">ICorPublishProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="02ec1-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="02ec1-103">一个子类[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)接口，提供用于遍历集合的方法[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="02ec1-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02ec1-104">方法</span><span class="sxs-lookup"><span data-stu-id="02ec1-104">Methods</span></span>  
  
|<span data-ttu-id="02ec1-105">方法</span><span class="sxs-lookup"><span data-stu-id="02ec1-105">Method</span></span>|<span data-ttu-id="02ec1-106">描述</span><span class="sxs-lookup"><span data-stu-id="02ec1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02ec1-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="02ec1-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="02ec1-108">获取指定的数目的`ICorPublishProcess`实例集合中的当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="02ec1-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02ec1-109">备注</span><span class="sxs-lookup"><span data-stu-id="02ec1-109">Remarks</span></span>  
 <span data-ttu-id="02ec1-110">`ICorPublishProcessEnum`接口实现的方法的抽象的接口， [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="02ec1-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="02ec1-111">`ICorPublishProcessEnum`实例由创建[icorpublish:: Enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="02ec1-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="02ec1-112">集合遍历`ICorPublishProcess`对象基于时给定的筛选器条件`ICorPublishProcessEnum`创建实例。</span><span class="sxs-lookup"><span data-stu-id="02ec1-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02ec1-113">惠?</span><span class="sxs-lookup"><span data-stu-id="02ec1-113">Requirements</span></span>  
 <span data-ttu-id="02ec1-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02ec1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02ec1-115">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="02ec1-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="02ec1-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02ec1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02ec1-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02ec1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ec1-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="02ec1-118">See Also</span></span>  
 [<span data-ttu-id="02ec1-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="02ec1-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="02ec1-120">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="02ec1-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
