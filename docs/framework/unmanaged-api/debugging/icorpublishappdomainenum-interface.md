---
title: "ICorPublishAppDomainEnum 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomainEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomainEnum
helpviewer_keywords: ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8359eda5432a9b3818fd58f6adc18570e4c5f154
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="88816-102">ICorPublishAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="88816-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="88816-103">一个子类[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)接口，提供用于遍历集合的方法[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)进程中当前存在的对象。</span><span class="sxs-lookup"><span data-stu-id="88816-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="88816-104">方法</span><span class="sxs-lookup"><span data-stu-id="88816-104">Methods</span></span>  
  
|<span data-ttu-id="88816-105">方法</span><span class="sxs-lookup"><span data-stu-id="88816-105">Method</span></span>|<span data-ttu-id="88816-106">描述</span><span class="sxs-lookup"><span data-stu-id="88816-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="88816-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="88816-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="88816-108">获取指定的数目的`ICorPublishAppDomain`实例集合中的当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="88816-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88816-109">备注</span><span class="sxs-lookup"><span data-stu-id="88816-109">Remarks</span></span>  
 <span data-ttu-id="88816-110">`ICorPublishAppDomainEnum`接口实现的方法的抽象的接口， [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="88816-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88816-111">要求</span><span class="sxs-lookup"><span data-stu-id="88816-111">Requirements</span></span>  
 <span data-ttu-id="88816-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88816-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88816-113">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="88816-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="88816-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88816-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88816-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88816-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88816-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88816-116">See Also</span></span>  
 [<span data-ttu-id="88816-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="88816-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="88816-118">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="88816-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
