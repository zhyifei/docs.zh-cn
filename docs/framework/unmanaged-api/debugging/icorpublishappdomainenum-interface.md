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
ms.openlocfilehash: cbe2aa48a8b67b0b6e88f7b5267bc70848fe3cec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140325"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="3fb39-102">ICorPublishAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="3fb39-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="3fb39-103">[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)接口的子类，它提供了用于遍历进程中当前存在的[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)对象的集合的方法。</span><span class="sxs-lookup"><span data-stu-id="3fb39-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3fb39-104">方法</span><span class="sxs-lookup"><span data-stu-id="3fb39-104">Methods</span></span>  
  
|<span data-ttu-id="3fb39-105">方法</span><span class="sxs-lookup"><span data-stu-id="3fb39-105">Method</span></span>|<span data-ttu-id="3fb39-106">描述</span><span class="sxs-lookup"><span data-stu-id="3fb39-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3fb39-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="3fb39-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="3fb39-108">从当前位置开始，获取集合中指定数量的 `ICorPublishAppDomain` 实例。</span><span class="sxs-lookup"><span data-stu-id="3fb39-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fb39-109">备注</span><span class="sxs-lookup"><span data-stu-id="3fb39-109">Remarks</span></span>  
 <span data-ttu-id="3fb39-110">`ICorPublishAppDomainEnum` 接口实现抽象接口[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)的方法。</span><span class="sxs-lookup"><span data-stu-id="3fb39-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fb39-111">要求</span><span class="sxs-lookup"><span data-stu-id="3fb39-111">Requirements</span></span>  
 <span data-ttu-id="3fb39-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3fb39-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fb39-113">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="3fb39-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3fb39-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fb39-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fb39-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fb39-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb39-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fb39-116">See also</span></span>

- [<span data-ttu-id="3fb39-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="3fb39-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3fb39-118">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="3fb39-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
