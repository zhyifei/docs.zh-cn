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
ms.openlocfilehash: a5509dd07bbb6c812a7ea2797c46002aaa161c46
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619963"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="de737-102">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="de737-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="de737-103">提供有关进程和应用程序域的信息的发布中使用的枚举器的抽象基接口。</span><span class="sxs-lookup"><span data-stu-id="de737-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de737-104">方法</span><span class="sxs-lookup"><span data-stu-id="de737-104">Methods</span></span>  
  
|<span data-ttu-id="de737-105">方法</span><span class="sxs-lookup"><span data-stu-id="de737-105">Method</span></span>|<span data-ttu-id="de737-106">描述</span><span class="sxs-lookup"><span data-stu-id="de737-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de737-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="de737-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="de737-108">创建一份`ICorPublishEnum`对象。</span><span class="sxs-lookup"><span data-stu-id="de737-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="de737-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="de737-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="de737-110">枚举中获取项的数目。</span><span class="sxs-lookup"><span data-stu-id="de737-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="de737-111">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="de737-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="de737-112">将的光标移到枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="de737-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="de737-113">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="de737-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="de737-114">将光标向前移动在枚举中指定数目的项。</span><span class="sxs-lookup"><span data-stu-id="de737-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de737-115">备注</span><span class="sxs-lookup"><span data-stu-id="de737-115">Remarks</span></span>  
 <span data-ttu-id="de737-116">派生自以下枚举器`ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="de737-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="de737-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="de737-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="de737-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="de737-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="de737-119">要求</span><span class="sxs-lookup"><span data-stu-id="de737-119">Requirements</span></span>  
 <span data-ttu-id="de737-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de737-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de737-121">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="de737-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="de737-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de737-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de737-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de737-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de737-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="de737-124">See also</span></span>

- [<span data-ttu-id="de737-125">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="de737-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="de737-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="de737-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
