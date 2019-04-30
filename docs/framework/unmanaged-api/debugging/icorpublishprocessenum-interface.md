---
title: ICorPublishProcessEnum 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5186df61eb82b29fcfa9776408498b748068e122
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993470"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="780e8-102">ICorPublishProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="780e8-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="780e8-103">子类[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)接口所提供的方法来遍历一系列[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="780e8-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="780e8-104">方法</span><span class="sxs-lookup"><span data-stu-id="780e8-104">Methods</span></span>  
  
|<span data-ttu-id="780e8-105">方法</span><span class="sxs-lookup"><span data-stu-id="780e8-105">Method</span></span>|<span data-ttu-id="780e8-106">描述</span><span class="sxs-lookup"><span data-stu-id="780e8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="780e8-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="780e8-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="780e8-108">获取指定的数目的`ICorPublishProcess`实例从集合中，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="780e8-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="780e8-109">备注</span><span class="sxs-lookup"><span data-stu-id="780e8-109">Remarks</span></span>  
 <span data-ttu-id="780e8-110">`ICorPublishProcessEnum`接口实现的抽象接口，方法[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="780e8-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="780e8-111">`ICorPublishProcessEnum`实例创建的[icorpublish:: Enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="780e8-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="780e8-112">集合的遍历`ICorPublishProcess`对象基于在时提供的筛选器条件`ICorPublishProcessEnum`创建实例。</span><span class="sxs-lookup"><span data-stu-id="780e8-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="780e8-113">要求</span><span class="sxs-lookup"><span data-stu-id="780e8-113">Requirements</span></span>  
 <span data-ttu-id="780e8-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="780e8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="780e8-115">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="780e8-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="780e8-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="780e8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="780e8-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="780e8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="780e8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="780e8-118">See also</span></span>

- [<span data-ttu-id="780e8-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="780e8-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="780e8-120">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="780e8-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
