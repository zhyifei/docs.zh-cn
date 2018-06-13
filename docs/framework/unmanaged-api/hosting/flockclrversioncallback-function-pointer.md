---
title: FLockClrVersionCallback 函数指针
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c884d07fa35c053b1a3b65c04426ac0e3712621
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429668"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="80fad-102">FLockClrVersionCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="80fad-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="80fad-103">指向以公共语言运行时 (CLR) 调用以指示该初始化已开始或完成的函数。</span><span class="sxs-lookup"><span data-stu-id="80fad-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="80fad-104">中已弃用此函数指针[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80fad-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80fad-105">语法</span><span class="sxs-lookup"><span data-stu-id="80fad-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="80fad-106">备注</span><span class="sxs-lookup"><span data-stu-id="80fad-106">Remarks</span></span>  
 <span data-ttu-id="80fad-107">此函数是由宿主实现的。</span><span class="sxs-lookup"><span data-stu-id="80fad-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80fad-108">要求</span><span class="sxs-lookup"><span data-stu-id="80fad-108">Requirements</span></span>  
 <span data-ttu-id="80fad-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="80fad-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80fad-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80fad-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80fad-111">**库：** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="80fad-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="80fad-112">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80fad-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80fad-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="80fad-113">See Also</span></span>  
 [<span data-ttu-id="80fad-114">LockClrVersion 函数</span><span class="sxs-lookup"><span data-stu-id="80fad-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 [<span data-ttu-id="80fad-115">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="80fad-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
