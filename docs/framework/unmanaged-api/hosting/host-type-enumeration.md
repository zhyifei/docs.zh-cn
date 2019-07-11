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
ms.openlocfilehash: caf76fa7962de9392b06591777ac862aa548d20d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779555"
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="bfaab-102">HOST_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="bfaab-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="bfaab-103">包含指定的启动应用程序的宿主类型的值。</span><span class="sxs-lookup"><span data-stu-id="bfaab-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfaab-104">语法</span><span class="sxs-lookup"><span data-stu-id="bfaab-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="bfaab-105">成员</span><span class="sxs-lookup"><span data-stu-id="bfaab-105">Members</span></span>  
  
|<span data-ttu-id="bfaab-106">成员</span><span class="sxs-lookup"><span data-stu-id="bfaab-106">Member</span></span>|<span data-ttu-id="bfaab-107">描述</span><span class="sxs-lookup"><span data-stu-id="bfaab-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="bfaab-108">启动从 AppLaunch.exe 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bfaab-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="bfaab-109">对于部分受信任的应用程序中使用此值。</span><span class="sxs-lookup"><span data-stu-id="bfaab-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="bfaab-110">直接启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="bfaab-110">Launch the application directly.</span></span> <span data-ttu-id="bfaab-111">也就是说，启动应用程序从其自己的.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="bfaab-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="bfaab-112">此值用于完全受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bfaab-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="bfaab-113">HOST_TYPE_APPLAUNCH 相同。</span><span class="sxs-lookup"><span data-stu-id="bfaab-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfaab-114">要求</span><span class="sxs-lookup"><span data-stu-id="bfaab-114">Requirements</span></span>  
 <span data-ttu-id="bfaab-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bfaab-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfaab-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bfaab-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bfaab-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bfaab-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfaab-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfaab-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfaab-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfaab-119">See also</span></span>

- [<span data-ttu-id="bfaab-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="bfaab-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
