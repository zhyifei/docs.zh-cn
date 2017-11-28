---
title: "RUNTIME_INFO_FLAGS 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: RUNTIME_INFO_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: RUNTIME_INFO_FLAGS
helpviewer_keywords: RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 697111efbb4e3f705c881ec677f781b6e3e6959d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="e054b-102">RUNTIME_INFO_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="e054b-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="e054b-103">包含值，用于指示应返回有关公共语言运行时 (CLR) 的哪些信息。</span><span class="sxs-lookup"><span data-stu-id="e054b-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e054b-104">语法</span><span class="sxs-lookup"><span data-stu-id="e054b-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="e054b-105">成员</span><span class="sxs-lookup"><span data-stu-id="e054b-105">Members</span></span>  
  
|<span data-ttu-id="e054b-106">成员</span><span class="sxs-lookup"><span data-stu-id="e054b-106">Member</span></span>|<span data-ttu-id="e054b-107">描述</span><span class="sxs-lookup"><span data-stu-id="e054b-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="e054b-108">指示不应包含目录信息。</span><span class="sxs-lookup"><span data-stu-id="e054b-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="e054b-109">指示不应包含版本信息。</span><span class="sxs-lookup"><span data-stu-id="e054b-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="e054b-110">指示应在失败时显示错误对话框。</span><span class="sxs-lookup"><span data-stu-id="e054b-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="e054b-111">指示调用的效果[SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) SEM_FAILCRITICALERRORS 标志的函数应重写。</span><span class="sxs-lookup"><span data-stu-id="e054b-111">Indicates that the effects of calling the [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="e054b-112">即一个安装对话框应显示在失败，而不是禁止显示时。</span><span class="sxs-lookup"><span data-stu-id="e054b-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="e054b-113">指示 AMD 64 兼容版本的运行时信息的请求。</span><span class="sxs-lookup"><span data-stu-id="e054b-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="e054b-114">指示运行时的 IA 64 兼容版本有关的信息的请求。</span><span class="sxs-lookup"><span data-stu-id="e054b-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="e054b-115">指示 x86 兼容版本的运行时信息的请求。</span><span class="sxs-lookup"><span data-stu-id="e054b-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="e054b-116">指示应包括版本升级的信息。</span><span class="sxs-lookup"><span data-stu-id="e054b-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e054b-117">备注</span><span class="sxs-lookup"><span data-stu-id="e054b-117">Remarks</span></span>  
 <span data-ttu-id="e054b-118">以下的平台体系结构标志可以是一次只能指定的一个，并且不能结合使用：</span><span class="sxs-lookup"><span data-stu-id="e054b-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="e054b-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="e054b-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="e054b-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="e054b-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="e054b-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="e054b-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e054b-122">要求</span><span class="sxs-lookup"><span data-stu-id="e054b-122">Requirements</span></span>  
 <span data-ttu-id="e054b-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e054b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e054b-124">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e054b-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e054b-125">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e054b-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e054b-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e054b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e054b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e054b-127">See Also</span></span>  
 [<span data-ttu-id="e054b-128">承载枚举</span><span class="sxs-lookup"><span data-stu-id="e054b-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
