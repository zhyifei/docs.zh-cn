---
title: ComCallUnmarshal Coclass
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fde42e3ecfac81a168920bc152833be7ba72b995
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779079"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="e957a-102">ComCallUnmarshal Coclass</span><span class="sxs-lookup"><span data-stu-id="e957a-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="e957a-103">提供用于管理的接口指针的封送的接口。</span><span class="sxs-lookup"><span data-stu-id="e957a-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e957a-104">语法</span><span class="sxs-lookup"><span data-stu-id="e957a-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="e957a-105">接口</span><span class="sxs-lookup"><span data-stu-id="e957a-105">Interfaces</span></span>  
  
|<span data-ttu-id="e957a-106">接口</span><span class="sxs-lookup"><span data-stu-id="e957a-106">Interface</span></span>|<span data-ttu-id="e957a-107">描述</span><span class="sxs-lookup"><span data-stu-id="e957a-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="e957a-108">提供用于创建、 初始化和管理客户端进程中的代理方法。</span><span class="sxs-lookup"><span data-stu-id="e957a-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e957a-109">要求</span><span class="sxs-lookup"><span data-stu-id="e957a-109">Requirements</span></span>  
 <span data-ttu-id="e957a-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e957a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e957a-111">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="e957a-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="e957a-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e957a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e957a-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e957a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e957a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e957a-114">See also</span></span>

- [<span data-ttu-id="e957a-115">承载组件类</span><span class="sxs-lookup"><span data-stu-id="e957a-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
