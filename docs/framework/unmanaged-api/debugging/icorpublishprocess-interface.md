---
title: ICorPublishProcess 接口
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08dfa3ddbfd9cffdb0cb88d0325e5703a854668a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182957"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="04a8b-102">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="04a8b-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="04a8b-103">提供用于访问要显示有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="04a8b-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04a8b-104">方法</span><span class="sxs-lookup"><span data-stu-id="04a8b-104">Methods</span></span>  
  
|<span data-ttu-id="04a8b-105">方法</span><span class="sxs-lookup"><span data-stu-id="04a8b-105">Method</span></span>|<span data-ttu-id="04a8b-106">描述</span><span class="sxs-lookup"><span data-stu-id="04a8b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04a8b-107">EnumAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="04a8b-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="04a8b-108">获取[ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)实例，它包含此引用的进程中的应用程序域`ICorPublishProcess`。</span><span class="sxs-lookup"><span data-stu-id="04a8b-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="04a8b-109">GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="04a8b-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="04a8b-110">获取引用此进程可执行文件的完整路径`ICorPublishProcess`。</span><span class="sxs-lookup"><span data-stu-id="04a8b-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="04a8b-111">GetProcessID 方法</span><span class="sxs-lookup"><span data-stu-id="04a8b-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="04a8b-112">获取引用此进程的操作系统识别符`ICorPublishProcess`。</span><span class="sxs-lookup"><span data-stu-id="04a8b-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="04a8b-113">IsManaged 方法</span><span class="sxs-lookup"><span data-stu-id="04a8b-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="04a8b-114">获取一个值，该值指示是否引用的进程这`ICorPublishProcess`已知的正在运行托管的代码。</span><span class="sxs-lookup"><span data-stu-id="04a8b-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04a8b-115">要求</span><span class="sxs-lookup"><span data-stu-id="04a8b-115">Requirements</span></span>  
 <span data-ttu-id="04a8b-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="04a8b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04a8b-117">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="04a8b-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="04a8b-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04a8b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04a8b-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04a8b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a8b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="04a8b-120">See also</span></span>

- [<span data-ttu-id="04a8b-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="04a8b-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="04a8b-122">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="04a8b-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
