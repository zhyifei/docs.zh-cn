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
ms.openlocfilehash: 19f76a163fae4a1390a2e0fcb85299f8ce78180c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435885"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="0c1f3-102">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="0c1f3-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="0c1f3-103">提供访问要显示有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="0c1f3-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c1f3-104">方法</span><span class="sxs-lookup"><span data-stu-id="0c1f3-104">Methods</span></span>  
  
|<span data-ttu-id="0c1f3-105">方法</span><span class="sxs-lookup"><span data-stu-id="0c1f3-105">Method</span></span>|<span data-ttu-id="0c1f3-106">描述</span><span class="sxs-lookup"><span data-stu-id="0c1f3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c1f3-107">EnumAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="0c1f3-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="0c1f3-108">获取[ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)实例，其中包含在引用此过程中的应用程序域`ICorPublishProcess`。</span><span class="sxs-lookup"><span data-stu-id="0c1f3-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="0c1f3-109">GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="0c1f3-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="0c1f3-110">获取引用此进程可执行文件的完整路径`ICorPublishProcess`。</span><span class="sxs-lookup"><span data-stu-id="0c1f3-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="0c1f3-111">GetProcessID 方法</span><span class="sxs-lookup"><span data-stu-id="0c1f3-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="0c1f3-112">获取引用此进程的操作系统识别符`ICorPublishProcess`。</span><span class="sxs-lookup"><span data-stu-id="0c1f3-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="0c1f3-113">IsManaged 方法</span><span class="sxs-lookup"><span data-stu-id="0c1f3-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="0c1f3-114">获取一个值，该值指示由此是否引用的进程`ICorPublishProcess`已知运行托管的代码。</span><span class="sxs-lookup"><span data-stu-id="0c1f3-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c1f3-115">要求</span><span class="sxs-lookup"><span data-stu-id="0c1f3-115">Requirements</span></span>  
 <span data-ttu-id="0c1f3-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c1f3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c1f3-117">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="0c1f3-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0c1f3-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c1f3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c1f3-119">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c1f3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c1f3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c1f3-120">See Also</span></span>  
 [<span data-ttu-id="0c1f3-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="0c1f3-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0c1f3-122">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="0c1f3-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
