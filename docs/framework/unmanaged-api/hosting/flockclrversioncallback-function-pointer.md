---
title: "FLockClrVersionCallback 函数指针"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FLockClrVersionCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: FLockClrVersionCallback
helpviewer_keywords: FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90b3bd053eb2e1161d6bb107afe9b3c627b1b207
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="76cab-102">FLockClrVersionCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="76cab-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="76cab-103">指向以公共语言运行时 (CLR) 调用以指示该初始化已开始或完成的函数。</span><span class="sxs-lookup"><span data-stu-id="76cab-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="76cab-104">中已弃用此函数指针[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="76cab-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76cab-105">语法</span><span class="sxs-lookup"><span data-stu-id="76cab-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="76cab-106">备注</span><span class="sxs-lookup"><span data-stu-id="76cab-106">Remarks</span></span>  
 <span data-ttu-id="76cab-107">此函数是由宿主实现的。</span><span class="sxs-lookup"><span data-stu-id="76cab-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76cab-108">惠?</span><span class="sxs-lookup"><span data-stu-id="76cab-108">Requirements</span></span>  
 <span data-ttu-id="76cab-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76cab-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76cab-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="76cab-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76cab-111">**库：** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="76cab-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="76cab-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76cab-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76cab-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="76cab-113">See Also</span></span>  
 [<span data-ttu-id="76cab-114">LockClrVersion 函数</span><span class="sxs-lookup"><span data-stu-id="76cab-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 [<span data-ttu-id="76cab-115">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="76cab-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
