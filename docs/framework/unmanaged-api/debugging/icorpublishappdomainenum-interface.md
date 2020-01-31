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
ms.openlocfilehash: 61cac0922423acabef3d47618d98ddf082d071da
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790666"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="b115f-102">ICorPublishAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b115f-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="b115f-103">[ICorPublishEnum](icorpublishenum-interface.md)接口的子类，它提供了用于遍历进程中当前存在的[ICorPublishAppDomain](icorpublishappdomain-interface.md)对象的集合的方法。</span><span class="sxs-lookup"><span data-stu-id="b115f-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b115f-104">方法</span><span class="sxs-lookup"><span data-stu-id="b115f-104">Methods</span></span>  
  
|<span data-ttu-id="b115f-105">方法</span><span class="sxs-lookup"><span data-stu-id="b115f-105">Method</span></span>|<span data-ttu-id="b115f-106">描述</span><span class="sxs-lookup"><span data-stu-id="b115f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b115f-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="b115f-107">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="b115f-108">从当前位置开始，获取集合中指定数量的 `ICorPublishAppDomain` 实例。</span><span class="sxs-lookup"><span data-stu-id="b115f-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b115f-109">备注</span><span class="sxs-lookup"><span data-stu-id="b115f-109">Remarks</span></span>  
 <span data-ttu-id="b115f-110">`ICorPublishAppDomainEnum` 接口实现抽象接口[ICorPublishEnum](icorpublishenum-interface.md)的方法。</span><span class="sxs-lookup"><span data-stu-id="b115f-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b115f-111">需求</span><span class="sxs-lookup"><span data-stu-id="b115f-111">Requirements</span></span>  
 <span data-ttu-id="b115f-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b115f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b115f-113">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="b115f-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b115f-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b115f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b115f-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b115f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b115f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b115f-116">See also</span></span>

- [<span data-ttu-id="b115f-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="b115f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b115f-118">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="b115f-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
