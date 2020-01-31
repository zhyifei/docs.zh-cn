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
ms.openlocfilehash: 3ae48df9e66890161c1aef944d37b0a279939d56
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790543"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="641c7-102">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="641c7-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="641c7-103">提供用于访问要显示的有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="641c7-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="641c7-104">方法</span><span class="sxs-lookup"><span data-stu-id="641c7-104">Methods</span></span>  
  
|<span data-ttu-id="641c7-105">方法</span><span class="sxs-lookup"><span data-stu-id="641c7-105">Method</span></span>|<span data-ttu-id="641c7-106">描述</span><span class="sxs-lookup"><span data-stu-id="641c7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="641c7-107">EnumAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="641c7-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="641c7-108">获取一个[ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)实例，它包含此 `ICorPublishProcess`所引用的进程中的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="641c7-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="641c7-109">GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="641c7-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="641c7-110">获取此 `ICorPublishProcess`所引用的进程的可执行文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="641c7-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="641c7-111">GetProcessID 方法</span><span class="sxs-lookup"><span data-stu-id="641c7-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="641c7-112">获取此 `ICorPublishProcess`所引用的进程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="641c7-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="641c7-113">IsManaged 方法</span><span class="sxs-lookup"><span data-stu-id="641c7-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="641c7-114">获取一个值，该值指示此 `ICorPublishProcess` 引用的进程是否已知正在运行托管代码。</span><span class="sxs-lookup"><span data-stu-id="641c7-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="641c7-115">需求</span><span class="sxs-lookup"><span data-stu-id="641c7-115">Requirements</span></span>  
 <span data-ttu-id="641c7-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="641c7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="641c7-117">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="641c7-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="641c7-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="641c7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="641c7-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="641c7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="641c7-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="641c7-120">See also</span></span>

- [<span data-ttu-id="641c7-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="641c7-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="641c7-122">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="641c7-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
