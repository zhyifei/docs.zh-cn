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
ms.openlocfilehash: f1ad414c30788801e14a33e98a0893e2a0f58d0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136518"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="189a9-102">FLockClrVersionCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="189a9-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="189a9-103">指向一个函数，公共语言运行时（CLR）会调用该函数以指示初始化已启动或已完成。</span><span class="sxs-lookup"><span data-stu-id="189a9-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="189a9-104">此函数指针在 .NET Framework 4 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="189a9-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="189a9-105">语法</span><span class="sxs-lookup"><span data-stu-id="189a9-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="189a9-106">备注</span><span class="sxs-lookup"><span data-stu-id="189a9-106">Remarks</span></span>  
 <span data-ttu-id="189a9-107">此函数由主机实现。</span><span class="sxs-lookup"><span data-stu-id="189a9-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="189a9-108">要求</span><span class="sxs-lookup"><span data-stu-id="189a9-108">Requirements</span></span>  
 <span data-ttu-id="189a9-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="189a9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="189a9-110">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="189a9-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="189a9-111">**库：** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="189a9-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="189a9-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="189a9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="189a9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="189a9-113">See also</span></span>

- [<span data-ttu-id="189a9-114">LockClrVersion 函数</span><span class="sxs-lookup"><span data-stu-id="189a9-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="189a9-115">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="189a9-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
