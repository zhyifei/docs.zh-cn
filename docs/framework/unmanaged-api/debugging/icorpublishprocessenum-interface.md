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
ms.openlocfilehash: 657d2d638a419ba88d4cf7152f4505de1bd23706
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421067"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="4629a-102">ICorPublishProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4629a-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="4629a-103">[ICorPublishEnum](icorpublishenum-interface.md)接口的子类，提供遍历[ICorPublishProcess](icorpublishprocess-interface.md)对象集合的方法。</span><span class="sxs-lookup"><span data-stu-id="4629a-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4629a-104">方法</span><span class="sxs-lookup"><span data-stu-id="4629a-104">Methods</span></span>  
  
|<span data-ttu-id="4629a-105">方法</span><span class="sxs-lookup"><span data-stu-id="4629a-105">Method</span></span>|<span data-ttu-id="4629a-106">说明</span><span class="sxs-lookup"><span data-stu-id="4629a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4629a-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="4629a-107">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="4629a-108">`ICorPublishProcess`从当前位置开始，获取集合中指定数量的实例。</span><span class="sxs-lookup"><span data-stu-id="4629a-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4629a-109">备注</span><span class="sxs-lookup"><span data-stu-id="4629a-109">Remarks</span></span>  
 <span data-ttu-id="4629a-110">`ICorPublishProcessEnum`接口实现抽象接口的方法[ICorPublishEnum](icorpublishenum-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="4629a-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="4629a-111">`ICorPublishProcessEnum`实例由[ICorPublish：： EnumProcesses](icorpublish-enumprocesses-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="4629a-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="4629a-112">对象集合的遍历 `ICorPublishProcess` 基于创建实例时给定的筛选条件 `ICorPublishProcessEnum` 。</span><span class="sxs-lookup"><span data-stu-id="4629a-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4629a-113">要求</span><span class="sxs-lookup"><span data-stu-id="4629a-113">Requirements</span></span>  
 <span data-ttu-id="4629a-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4629a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4629a-115">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="4629a-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="4629a-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4629a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4629a-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4629a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4629a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4629a-118">See also</span></span>

- [<span data-ttu-id="4629a-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="4629a-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4629a-120">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="4629a-120">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
