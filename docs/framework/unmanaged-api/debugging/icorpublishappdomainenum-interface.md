---
title: ICorPublishAppDomainEnum 接口
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2be3406cd4330fb477e8a1c89945be1e9f777bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706597"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="05c6d-102">ICorPublishAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="05c6d-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="05c6d-103">子类[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)接口所提供的方法来遍历一系列[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)在进程中当前存在的对象。</span><span class="sxs-lookup"><span data-stu-id="05c6d-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05c6d-104">方法</span><span class="sxs-lookup"><span data-stu-id="05c6d-104">Methods</span></span>  
  
|<span data-ttu-id="05c6d-105">方法</span><span class="sxs-lookup"><span data-stu-id="05c6d-105">Method</span></span>|<span data-ttu-id="05c6d-106">描述</span><span class="sxs-lookup"><span data-stu-id="05c6d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05c6d-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="05c6d-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="05c6d-108">获取指定的数目的`ICorPublishAppDomain`实例从集合中，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="05c6d-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05c6d-109">备注</span><span class="sxs-lookup"><span data-stu-id="05c6d-109">Remarks</span></span>  
 <span data-ttu-id="05c6d-110">`ICorPublishAppDomainEnum`接口实现的抽象接口，方法[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="05c6d-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05c6d-111">要求</span><span class="sxs-lookup"><span data-stu-id="05c6d-111">Requirements</span></span>  
 <span data-ttu-id="05c6d-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05c6d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05c6d-113">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="05c6d-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="05c6d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05c6d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05c6d-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05c6d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c6d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="05c6d-116">See also</span></span>
- [<span data-ttu-id="05c6d-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="05c6d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="05c6d-118">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="05c6d-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
