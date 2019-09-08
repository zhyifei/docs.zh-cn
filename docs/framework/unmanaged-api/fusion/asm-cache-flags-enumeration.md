---
title: ASM_CACHE_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e3e9da3db71d3e24b2a60ff032a631680055b88
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795285"
---
# <a name="asm_cache_flags-enumeration"></a><span data-ttu-id="93f9c-102">ASM_CACHE_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="93f9c-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="93f9c-103">指示由全局程序集缓存中的[IAssemblyCacheItem](iassemblycacheitem-interface.md)表示的程序集的源。</span><span class="sxs-lookup"><span data-stu-id="93f9c-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93f9c-104">语法</span><span class="sxs-lookup"><span data-stu-id="93f9c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="93f9c-105">成员</span><span class="sxs-lookup"><span data-stu-id="93f9c-105">Members</span></span>  
  
|<span data-ttu-id="93f9c-106">成员</span><span class="sxs-lookup"><span data-stu-id="93f9c-106">Member</span></span>|<span data-ttu-id="93f9c-107">描述</span><span class="sxs-lookup"><span data-stu-id="93f9c-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="93f9c-108">使用 Ngen.exe 枚举预编译程序集的缓存。</span><span class="sxs-lookup"><span data-stu-id="93f9c-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="93f9c-109">枚举全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="93f9c-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="93f9c-110">枚举已按需下载或已进行卷影复制的程序集。</span><span class="sxs-lookup"><span data-stu-id="93f9c-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="93f9c-111">指示[GetCachePath](getcachepath-function.md)函数应返回公共语言运行时（CLR）版本2.0 的全局程序集缓存的路径。</span><span class="sxs-lookup"><span data-stu-id="93f9c-111">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="93f9c-112">仅在对[GetCachePath](getcachepath-function.md)的调用上下文中有意义。</span><span class="sxs-lookup"><span data-stu-id="93f9c-112">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="93f9c-113">指示[GetCachePath](getcachepath-function.md)函数应返回 CLR 版本4的全局程序集缓存的路径。</span><span class="sxs-lookup"><span data-stu-id="93f9c-113">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="93f9c-114">仅在对[GetCachePath](getcachepath-function.md)的调用上下文中有意义。</span><span class="sxs-lookup"><span data-stu-id="93f9c-114">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93f9c-115">要求</span><span class="sxs-lookup"><span data-stu-id="93f9c-115">Requirements</span></span>  
 <span data-ttu-id="93f9c-116">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="93f9c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93f9c-117">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="93f9c-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="93f9c-118">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="93f9c-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="93f9c-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93f9c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f9c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="93f9c-120">See also</span></span>

- [<span data-ttu-id="93f9c-121">GetCachePath 函数</span><span class="sxs-lookup"><span data-stu-id="93f9c-121">GetCachePath Function</span></span>](getcachepath-function.md)
- [<span data-ttu-id="93f9c-122">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="93f9c-122">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
- [<span data-ttu-id="93f9c-123">合成枚举</span><span class="sxs-lookup"><span data-stu-id="93f9c-123">Fusion Enumerations</span></span>](fusion-enumerations.md)
