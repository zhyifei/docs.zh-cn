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
ms.openlocfilehash: 38f3140a181deae1a86569bfc2eb7cf3cd7d1991
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131927"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="82721-102">ComCallUnmarshal Coclass</span><span class="sxs-lookup"><span data-stu-id="82721-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="82721-103">提供用于管理接口指针的封送处理的接口。</span><span class="sxs-lookup"><span data-stu-id="82721-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82721-104">语法</span><span class="sxs-lookup"><span data-stu-id="82721-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="82721-105">接口</span><span class="sxs-lookup"><span data-stu-id="82721-105">Interfaces</span></span>  
  
|<span data-ttu-id="82721-106">接口</span><span class="sxs-lookup"><span data-stu-id="82721-106">Interface</span></span>|<span data-ttu-id="82721-107">描述</span><span class="sxs-lookup"><span data-stu-id="82721-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="82721-108">提供用于在客户端进程中创建、初始化和管理代理的方法。</span><span class="sxs-lookup"><span data-stu-id="82721-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82721-109">要求</span><span class="sxs-lookup"><span data-stu-id="82721-109">Requirements</span></span>  
 <span data-ttu-id="82721-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82721-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82721-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="82721-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="82721-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="82721-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82721-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82721-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82721-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="82721-114">See also</span></span>

- [<span data-ttu-id="82721-115">承载组件类</span><span class="sxs-lookup"><span data-stu-id="82721-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
