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
ms.openlocfilehash: cc0cea10b4a209583fb7afb551a6b80d52ad7f62
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127030"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="cfb14-102">HOST_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="cfb14-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="cfb14-103">包含的值用于指定启动应用程序的主机的类型。</span><span class="sxs-lookup"><span data-stu-id="cfb14-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb14-104">语法</span><span class="sxs-lookup"><span data-stu-id="cfb14-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="cfb14-105">Members</span><span class="sxs-lookup"><span data-stu-id="cfb14-105">Members</span></span>  
  
|<span data-ttu-id="cfb14-106">成员</span><span class="sxs-lookup"><span data-stu-id="cfb14-106">Member</span></span>|<span data-ttu-id="cfb14-107">描述</span><span class="sxs-lookup"><span data-stu-id="cfb14-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="cfb14-108">从 AppLaunch 启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="cfb14-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="cfb14-109">将此值用于部分受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cfb14-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="cfb14-110">直接启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cfb14-110">Launch the application directly.</span></span> <span data-ttu-id="cfb14-111">也就是说，从它自己的 .exe 文件启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cfb14-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="cfb14-112">将此值用于完全受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cfb14-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="cfb14-113">与 HOST_TYPE_APPLAUNCH 相同。</span><span class="sxs-lookup"><span data-stu-id="cfb14-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cfb14-114">要求</span><span class="sxs-lookup"><span data-stu-id="cfb14-114">Requirements</span></span>  
 <span data-ttu-id="cfb14-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cfb14-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfb14-116">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cfb14-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cfb14-117">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cfb14-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cfb14-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfb14-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb14-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="cfb14-119">See also</span></span>

- [<span data-ttu-id="cfb14-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="cfb14-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
