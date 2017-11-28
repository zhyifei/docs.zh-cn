---
title: "CLSID_RESOLUTION_FLAGS 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLSID_RESOLUTION_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: CLSID_RESOLUTION_FLAGS
helpviewer_keywords: CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17e74e8b39ff9079973063f4ea703607411ab93d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="22c51-102">CLSID_RESOLUTION_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="22c51-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="22c51-103">包含值，用于指示公共语言运行时 (CLR) 应如何解析`CLSID`。</span><span class="sxs-lookup"><span data-stu-id="22c51-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22c51-104">语法</span><span class="sxs-lookup"><span data-stu-id="22c51-104">Syntax</span></span>  
  
```  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="22c51-105">成员</span><span class="sxs-lookup"><span data-stu-id="22c51-105">Members</span></span>  
  
|<span data-ttu-id="22c51-106">成员</span><span class="sxs-lookup"><span data-stu-id="22c51-106">Member</span></span>|<span data-ttu-id="22c51-107">描述</span><span class="sxs-lookup"><span data-stu-id="22c51-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="22c51-108">指示默认行为。</span><span class="sxs-lookup"><span data-stu-id="22c51-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="22c51-109">指示运行时的注册表中搜索和应用程序策略。</span><span class="sxs-lookup"><span data-stu-id="22c51-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22c51-110">要求</span><span class="sxs-lookup"><span data-stu-id="22c51-110">Requirements</span></span>  
 <span data-ttu-id="22c51-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22c51-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22c51-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="22c51-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22c51-113">**.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22c51-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c51-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22c51-114">See Also</span></span>  
 [<span data-ttu-id="22c51-115">承载枚举</span><span class="sxs-lookup"><span data-stu-id="22c51-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
