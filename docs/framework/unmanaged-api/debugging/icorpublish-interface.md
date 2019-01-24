---
title: ICorPublish 接口
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1dea8cc54c68db333c409e3bd7b3e4211bd52ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713962"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="57576-102">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="57576-102">ICorPublish Interface</span></span>
<span data-ttu-id="57576-103">用作发布进程的信息和有关应用程序域的信息，这些进程中的常规接口。</span><span class="sxs-lookup"><span data-stu-id="57576-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57576-104">方法</span><span class="sxs-lookup"><span data-stu-id="57576-104">Methods</span></span>  
  
|<span data-ttu-id="57576-105">方法</span><span class="sxs-lookup"><span data-stu-id="57576-105">Method</span></span>|<span data-ttu-id="57576-106">描述</span><span class="sxs-lookup"><span data-stu-id="57576-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57576-107">EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="57576-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="57576-108">获取[ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)实例，它包含在此计算机上运行的托管的进程。</span><span class="sxs-lookup"><span data-stu-id="57576-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="57576-109">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="57576-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="57576-110">获取[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)实例，它表示具有指定标识符的进程。</span><span class="sxs-lookup"><span data-stu-id="57576-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57576-111">要求</span><span class="sxs-lookup"><span data-stu-id="57576-111">Requirements</span></span>  
 <span data-ttu-id="57576-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="57576-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57576-113">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="57576-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="57576-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57576-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57576-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57576-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57576-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="57576-116">See also</span></span>
- [<span data-ttu-id="57576-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="57576-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="57576-118">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="57576-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
