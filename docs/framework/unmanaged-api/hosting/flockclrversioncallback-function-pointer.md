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
ms.openlocfilehash: 46e3356df6578f2adf2ceee00b1363b65fd014ea
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760239"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="543c0-102">FLockClrVersionCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="543c0-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="543c0-103">指向以公共语言运行时 (CLR) 调用以指示初始化已开始或完成的函数。</span><span class="sxs-lookup"><span data-stu-id="543c0-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="543c0-104">.NET Framework 4 中已弃用此函数指针。</span><span class="sxs-lookup"><span data-stu-id="543c0-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="543c0-105">语法</span><span class="sxs-lookup"><span data-stu-id="543c0-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="543c0-106">备注</span><span class="sxs-lookup"><span data-stu-id="543c0-106">Remarks</span></span>  
 <span data-ttu-id="543c0-107">此函数是由宿主实现的。</span><span class="sxs-lookup"><span data-stu-id="543c0-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="543c0-108">要求</span><span class="sxs-lookup"><span data-stu-id="543c0-108">Requirements</span></span>  
 <span data-ttu-id="543c0-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="543c0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="543c0-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="543c0-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="543c0-111">**库：** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="543c0-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="543c0-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="543c0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="543c0-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="543c0-113">See also</span></span>

- [<span data-ttu-id="543c0-114">LockClrVersion 函数</span><span class="sxs-lookup"><span data-stu-id="543c0-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="543c0-115">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="543c0-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
