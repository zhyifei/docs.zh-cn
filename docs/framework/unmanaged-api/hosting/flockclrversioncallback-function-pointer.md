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
ms.openlocfilehash: ef308b624525c3a139c892e6118a24d6adb6e14a
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490460"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="15b95-102">FLockClrVersionCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="15b95-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="15b95-103">指向以公共语言运行时 (CLR) 调用以指示初始化已开始或完成的函数。</span><span class="sxs-lookup"><span data-stu-id="15b95-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="15b95-104">.NET Framework 4 中已弃用此函数指针。</span><span class="sxs-lookup"><span data-stu-id="15b95-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15b95-105">语法</span><span class="sxs-lookup"><span data-stu-id="15b95-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="15b95-106">备注</span><span class="sxs-lookup"><span data-stu-id="15b95-106">Remarks</span></span>  
 <span data-ttu-id="15b95-107">此函数是由宿主实现的。</span><span class="sxs-lookup"><span data-stu-id="15b95-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15b95-108">要求</span><span class="sxs-lookup"><span data-stu-id="15b95-108">Requirements</span></span>  
 <span data-ttu-id="15b95-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15b95-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15b95-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15b95-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15b95-111">**库：** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="15b95-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="15b95-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15b95-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15b95-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="15b95-113">See also</span></span>

- [<span data-ttu-id="15b95-114">LockClrVersion 函数</span><span class="sxs-lookup"><span data-stu-id="15b95-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="15b95-115">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="15b95-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
