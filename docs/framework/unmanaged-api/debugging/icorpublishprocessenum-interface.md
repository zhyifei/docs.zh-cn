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
ms.openlocfilehash: 3a7267548a957d403cfe02aa3d800a410c14b82a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103417"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="caefc-102">ICorPublishProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="caefc-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="caefc-103">[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)接口的子类，提供遍历[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)对象集合的方法。</span><span class="sxs-lookup"><span data-stu-id="caefc-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="caefc-104">方法</span><span class="sxs-lookup"><span data-stu-id="caefc-104">Methods</span></span>  
  
|<span data-ttu-id="caefc-105">方法</span><span class="sxs-lookup"><span data-stu-id="caefc-105">Method</span></span>|<span data-ttu-id="caefc-106">描述</span><span class="sxs-lookup"><span data-stu-id="caefc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="caefc-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="caefc-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="caefc-108">从当前位置开始，获取集合中指定数量的 `ICorPublishProcess` 实例。</span><span class="sxs-lookup"><span data-stu-id="caefc-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caefc-109">备注</span><span class="sxs-lookup"><span data-stu-id="caefc-109">Remarks</span></span>  
 <span data-ttu-id="caefc-110">`ICorPublishProcessEnum` 接口实现抽象接口[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)的方法。</span><span class="sxs-lookup"><span data-stu-id="caefc-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="caefc-111">`ICorPublishProcessEnum` 实例是通过[ICorPublish：： EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)方法创建的。</span><span class="sxs-lookup"><span data-stu-id="caefc-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="caefc-112">`ICorPublishProcess` 对象集合的遍历基于创建 `ICorPublishProcessEnum` 实例时给定的筛选条件。</span><span class="sxs-lookup"><span data-stu-id="caefc-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caefc-113">要求</span><span class="sxs-lookup"><span data-stu-id="caefc-113">Requirements</span></span>  
 <span data-ttu-id="caefc-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="caefc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caefc-115">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="caefc-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="caefc-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caefc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caefc-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caefc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caefc-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="caefc-118">See also</span></span>

- [<span data-ttu-id="caefc-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="caefc-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="caefc-120">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="caefc-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
