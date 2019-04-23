---
title: HOST_TYPE 枚举
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfb1cff3e95c5ff86d22913745b7d14982766b48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175222"
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="b5069-102">HOST_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="b5069-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="b5069-103">包含指定的启动应用程序的宿主类型的值。</span><span class="sxs-lookup"><span data-stu-id="b5069-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5069-104">语法</span><span class="sxs-lookup"><span data-stu-id="b5069-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="b5069-105">成员</span><span class="sxs-lookup"><span data-stu-id="b5069-105">Members</span></span>  
  
|<span data-ttu-id="b5069-106">成员</span><span class="sxs-lookup"><span data-stu-id="b5069-106">Member</span></span>|<span data-ttu-id="b5069-107">描述</span><span class="sxs-lookup"><span data-stu-id="b5069-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="b5069-108">启动从 AppLaunch.exe 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5069-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="b5069-109">对于部分受信任的应用程序中使用此值。</span><span class="sxs-lookup"><span data-stu-id="b5069-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="b5069-110">直接启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5069-110">Launch the application directly.</span></span> <span data-ttu-id="b5069-111">也就是说，启动应用程序从其自己的.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="b5069-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="b5069-112">此值用于完全受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5069-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="b5069-113">HOST_TYPE_APPLAUNCH 相同。</span><span class="sxs-lookup"><span data-stu-id="b5069-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5069-114">要求</span><span class="sxs-lookup"><span data-stu-id="b5069-114">Requirements</span></span>  
 <span data-ttu-id="b5069-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5069-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5069-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b5069-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5069-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5069-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5069-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5069-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5069-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5069-119">See also</span></span>

- [<span data-ttu-id="b5069-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="b5069-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
