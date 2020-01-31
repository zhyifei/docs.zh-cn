---
title: CorpubPublish Coclass
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
ms.openlocfilehash: 24d245bbb0f9ac86e321491e0af3b66b1e011baa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789222"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="90e8f-102">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="90e8f-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="90e8f-103">提供用于发布应用程序域和进程相关信息的接口。</span><span class="sxs-lookup"><span data-stu-id="90e8f-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e8f-104">语法</span><span class="sxs-lookup"><span data-stu-id="90e8f-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="90e8f-105">接口</span><span class="sxs-lookup"><span data-stu-id="90e8f-105">Interfaces</span></span>  
  
|<span data-ttu-id="90e8f-106">界面</span><span class="sxs-lookup"><span data-stu-id="90e8f-106">Interface</span></span>|<span data-ttu-id="90e8f-107">描述</span><span class="sxs-lookup"><span data-stu-id="90e8f-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="90e8f-108">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="90e8f-108">ICorPublish Interface</span></span>](icorpublish-interface.md)|<span data-ttu-id="90e8f-109">提供用于在这些进程中发布有关进程和应用程序域的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="90e8f-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="90e8f-110">ICorPublishAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="90e8f-110">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)|<span data-ttu-id="90e8f-111">表示并提供有关进程中的应用程序域的信息。</span><span class="sxs-lookup"><span data-stu-id="90e8f-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="90e8f-112">ICorPublishAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="90e8f-112">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)|<span data-ttu-id="90e8f-113">提供遍历进程中当前存在的应用程序域集合的方法。</span><span class="sxs-lookup"><span data-stu-id="90e8f-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="90e8f-114">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="90e8f-114">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)|<span data-ttu-id="90e8f-115">表示在计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="90e8f-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="90e8f-116">ICorPublishProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="90e8f-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)|<span data-ttu-id="90e8f-117">提供遍历计算机上运行的进程集合的方法。</span><span class="sxs-lookup"><span data-stu-id="90e8f-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90e8f-118">备注</span><span class="sxs-lookup"><span data-stu-id="90e8f-118">Remarks</span></span>  
 <span data-ttu-id="90e8f-119">典型的发布方案涉及到需要调试在应用程序域中的计算机上运行的托管代码的开发人员。</span><span class="sxs-lookup"><span data-stu-id="90e8f-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="90e8f-120">宿主环境可能会在一个进程内运行多个应用程序域。</span><span class="sxs-lookup"><span data-stu-id="90e8f-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="90e8f-121">开发人员希望使用图形用户界面或其他一些方法列出计算机上运行的所有进程，并选择特定的进程。</span><span class="sxs-lookup"><span data-stu-id="90e8f-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="90e8f-122">此列表应包括正在运行托管代码的进程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="90e8f-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="90e8f-123">然后，开发人员可以确定特定的应用程序域，并将调试器附加到该域。</span><span class="sxs-lookup"><span data-stu-id="90e8f-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90e8f-124">需求</span><span class="sxs-lookup"><span data-stu-id="90e8f-124">Requirements</span></span>  
 <span data-ttu-id="90e8f-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90e8f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90e8f-126">**标头：** CorPub .idl</span><span class="sxs-lookup"><span data-stu-id="90e8f-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="90e8f-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90e8f-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90e8f-128">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90e8f-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e8f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90e8f-129">See also</span></span>

- [<span data-ttu-id="90e8f-130">调试</span><span class="sxs-lookup"><span data-stu-id="90e8f-130">Debugging</span></span>](index.md)
