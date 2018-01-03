---
title: CorpubPublish Coclass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorpubPublish Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorpubPublish
helpviewer_keywords: CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3dec1175715bdbddc3c975924e91e238fa6d5f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="58a34-102">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="58a34-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="58a34-103">提供用于发布应用程序域和进程相关信息的接口。</span><span class="sxs-lookup"><span data-stu-id="58a34-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58a34-104">语法</span><span class="sxs-lookup"><span data-stu-id="58a34-104">Syntax</span></span>  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="58a34-105">接口</span><span class="sxs-lookup"><span data-stu-id="58a34-105">Interfaces</span></span>  
  
|<span data-ttu-id="58a34-106">接口</span><span class="sxs-lookup"><span data-stu-id="58a34-106">Interface</span></span>|<span data-ttu-id="58a34-107">描述</span><span class="sxs-lookup"><span data-stu-id="58a34-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="58a34-108">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="58a34-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="58a34-109">提供有关进程和应用程序域的信息发布到这些进程的方法。</span><span class="sxs-lookup"><span data-stu-id="58a34-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="58a34-110">ICorPublishAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="58a34-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="58a34-111">表示，并提供关于，应用程序域的过程中的信息。</span><span class="sxs-lookup"><span data-stu-id="58a34-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="58a34-112">ICorPublishAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="58a34-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="58a34-113">提供遍历进程中当前存在的应用程序域的集合的方法。</span><span class="sxs-lookup"><span data-stu-id="58a34-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="58a34-114">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="58a34-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="58a34-115">表示在计算机运行的进程。</span><span class="sxs-lookup"><span data-stu-id="58a34-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="58a34-116">ICorPublishProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="58a34-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="58a34-117">提供遍历集合的计算机运行的进程的方法。</span><span class="sxs-lookup"><span data-stu-id="58a34-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58a34-118">备注</span><span class="sxs-lookup"><span data-stu-id="58a34-118">Remarks</span></span>  
 <span data-ttu-id="58a34-119">典型的发布方案涉及的开发人员想要调试应用程序域内的计算机运行的托管的代码。</span><span class="sxs-lookup"><span data-stu-id="58a34-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="58a34-120">宿主环境可能运行的进程中的多个应用程序域。</span><span class="sxs-lookup"><span data-stu-id="58a34-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="58a34-121">开发人员想要使用图形用户界面或某种其他方式来列出所有的计算机，运行的进程并选取一个特定的进程。</span><span class="sxs-lookup"><span data-stu-id="58a34-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="58a34-122">该列表应包括所有正在运行托管的代码的进程内的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="58a34-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="58a34-123">然后，开发人员可以标识特定的应用程序域，并将调试器附加到该域。</span><span class="sxs-lookup"><span data-stu-id="58a34-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58a34-124">惠?</span><span class="sxs-lookup"><span data-stu-id="58a34-124">Requirements</span></span>  
 <span data-ttu-id="58a34-125">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58a34-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58a34-126">**标头：** CorPub.idl</span><span class="sxs-lookup"><span data-stu-id="58a34-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="58a34-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58a34-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58a34-128">**.NET framework 版本：**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58a34-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a34-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="58a34-129">See Also</span></span>  
 [<span data-ttu-id="58a34-130">调试</span><span class="sxs-lookup"><span data-stu-id="58a34-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
