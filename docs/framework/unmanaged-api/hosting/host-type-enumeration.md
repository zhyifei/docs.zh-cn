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
ms.openlocfilehash: 6a2db1aea04ae060623bc39a52ed6990f6137f82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606436"
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="95ce4-102">HOST_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="95ce4-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="95ce4-103">包含指定的启动应用程序的宿主类型的值。</span><span class="sxs-lookup"><span data-stu-id="95ce4-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95ce4-104">语法</span><span class="sxs-lookup"><span data-stu-id="95ce4-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="95ce4-105">成员</span><span class="sxs-lookup"><span data-stu-id="95ce4-105">Members</span></span>  
  
|<span data-ttu-id="95ce4-106">成员</span><span class="sxs-lookup"><span data-stu-id="95ce4-106">Member</span></span>|<span data-ttu-id="95ce4-107">描述</span><span class="sxs-lookup"><span data-stu-id="95ce4-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="95ce4-108">启动从 AppLaunch.exe 应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ce4-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="95ce4-109">对于部分受信任的应用程序中使用此值。</span><span class="sxs-lookup"><span data-stu-id="95ce4-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="95ce4-110">直接启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ce4-110">Launch the application directly.</span></span> <span data-ttu-id="95ce4-111">也就是说，启动应用程序从其自己的.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="95ce4-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="95ce4-112">此值用于完全受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="95ce4-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="95ce4-113">HOST_TYPE_APPLAUNCH 相同。</span><span class="sxs-lookup"><span data-stu-id="95ce4-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95ce4-114">要求</span><span class="sxs-lookup"><span data-stu-id="95ce4-114">Requirements</span></span>  
 <span data-ttu-id="95ce4-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95ce4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95ce4-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95ce4-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95ce4-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95ce4-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95ce4-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95ce4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ce4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="95ce4-119">See also</span></span>
- [<span data-ttu-id="95ce4-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="95ce4-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
