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
ms.openlocfilehash: e33029e8244fdfa180a79aa4a5b05b07f594d928
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860905"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="462d5-102">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="462d5-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="462d5-103">提供用于发布应用程序域和进程相关信息的接口。</span><span class="sxs-lookup"><span data-stu-id="462d5-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="462d5-104">语法</span><span class="sxs-lookup"><span data-stu-id="462d5-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="462d5-105">界面</span><span class="sxs-lookup"><span data-stu-id="462d5-105">Interfaces</span></span>  
  
|<span data-ttu-id="462d5-106">接口</span><span class="sxs-lookup"><span data-stu-id="462d5-106">Interface</span></span>|<span data-ttu-id="462d5-107">说明</span><span class="sxs-lookup"><span data-stu-id="462d5-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="462d5-108">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="462d5-108">ICorPublish Interface</span></span>](icorpublish-interface.md)|<span data-ttu-id="462d5-109">提供用于在这些进程中发布有关进程和应用程序域的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="462d5-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="462d5-110">ICorPublishAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="462d5-110">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)|<span data-ttu-id="462d5-111">表示并提供有关进程中的应用程序域的信息。</span><span class="sxs-lookup"><span data-stu-id="462d5-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="462d5-112">ICorPublishAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="462d5-112">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)|<span data-ttu-id="462d5-113">提供遍历进程中当前存在的应用程序域集合的方法。</span><span class="sxs-lookup"><span data-stu-id="462d5-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="462d5-114">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="462d5-114">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)|<span data-ttu-id="462d5-115">表示在计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="462d5-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="462d5-116">ICorPublishProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="462d5-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)|<span data-ttu-id="462d5-117">提供遍历计算机上运行的进程集合的方法。</span><span class="sxs-lookup"><span data-stu-id="462d5-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="462d5-118">备注</span><span class="sxs-lookup"><span data-stu-id="462d5-118">Remarks</span></span>  
 <span data-ttu-id="462d5-119">典型的发布方案涉及到需要调试在应用程序域中的计算机上运行的托管代码的开发人员。</span><span class="sxs-lookup"><span data-stu-id="462d5-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="462d5-120">宿主环境可能会在一个进程内运行多个应用程序域。</span><span class="sxs-lookup"><span data-stu-id="462d5-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="462d5-121">开发人员希望使用图形用户界面或其他一些方法列出计算机上运行的所有进程，并选择特定的进程。</span><span class="sxs-lookup"><span data-stu-id="462d5-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="462d5-122">此列表应包括正在运行托管代码的进程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="462d5-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="462d5-123">然后，开发人员可以确定特定的应用程序域，并将调试器附加到该域。</span><span class="sxs-lookup"><span data-stu-id="462d5-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="462d5-124">要求</span><span class="sxs-lookup"><span data-stu-id="462d5-124">Requirements</span></span>  
 <span data-ttu-id="462d5-125">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="462d5-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="462d5-126">**标头：** CorPub .idl</span><span class="sxs-lookup"><span data-stu-id="462d5-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="462d5-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="462d5-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="462d5-128">**.NET Framework 版本：**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="462d5-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="462d5-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="462d5-129">See also</span></span>

- [<span data-ttu-id="462d5-130">调试</span><span class="sxs-lookup"><span data-stu-id="462d5-130">Debugging</span></span>](index.md)
