---
title: RUNTIME_INFO_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09bd32172bcad298eebc2921461fdc953e9c6d6e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084492"
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="e2498-102">RUNTIME_INFO_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="e2498-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="e2498-103">包含指示应返回有关公共语言运行时 (CLR) 的哪些信息的值。</span><span class="sxs-lookup"><span data-stu-id="e2498-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2498-104">语法</span><span class="sxs-lookup"><span data-stu-id="e2498-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e2498-105">成员</span><span class="sxs-lookup"><span data-stu-id="e2498-105">Members</span></span>  
  
|<span data-ttu-id="e2498-106">成员</span><span class="sxs-lookup"><span data-stu-id="e2498-106">Member</span></span>|<span data-ttu-id="e2498-107">描述</span><span class="sxs-lookup"><span data-stu-id="e2498-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="e2498-108">指示不应包含目录信息。</span><span class="sxs-lookup"><span data-stu-id="e2498-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="e2498-109">指示不应包含版本信息。</span><span class="sxs-lookup"><span data-stu-id="e2498-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="e2498-110">指示在失败时应不显示错误对话框。</span><span class="sxs-lookup"><span data-stu-id="e2498-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="e2498-111">指示调用的效果[SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) SEM_FAILCRITICALERRORS 标志的函数应重写。</span><span class="sxs-lookup"><span data-stu-id="e2498-111">Indicates that the effects of calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="e2498-112">也就是说，安装对话框中应显示失败，而不是所抑制。</span><span class="sxs-lookup"><span data-stu-id="e2498-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="e2498-113">指示有关 AMD 64 兼容版本的运行时信息的请求。</span><span class="sxs-lookup"><span data-stu-id="e2498-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="e2498-114">指示有关 IA 64 兼容版本的运行时信息的请求。</span><span class="sxs-lookup"><span data-stu-id="e2498-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="e2498-115">指示有关 x86 可兼容版本的运行时信息的请求。</span><span class="sxs-lookup"><span data-stu-id="e2498-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="e2498-116">指示应包含版本升级的信息。</span><span class="sxs-lookup"><span data-stu-id="e2498-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2498-117">备注</span><span class="sxs-lookup"><span data-stu-id="e2498-117">Remarks</span></span>  
 <span data-ttu-id="e2498-118">以下平台体系结构标志可以是一次只能指定的一个，并且不能结合使用：</span><span class="sxs-lookup"><span data-stu-id="e2498-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="e2498-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="e2498-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="e2498-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="e2498-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="e2498-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="e2498-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2498-122">要求</span><span class="sxs-lookup"><span data-stu-id="e2498-122">Requirements</span></span>  
 <span data-ttu-id="e2498-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2498-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2498-124">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e2498-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2498-125">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2498-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2498-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2498-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2498-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2498-127">See Also</span></span>  
 [<span data-ttu-id="e2498-128">承载枚举</span><span class="sxs-lookup"><span data-stu-id="e2498-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
