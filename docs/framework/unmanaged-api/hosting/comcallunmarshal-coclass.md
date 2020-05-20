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
ms.openlocfilehash: 939acc0ad47021d5fdffe7b7b71ea6a4a1635a6d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616731"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="6a294-102">ComCallUnmarshal Coclass</span><span class="sxs-lookup"><span data-stu-id="6a294-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="6a294-103">提供用于管理接口指针的封送处理的接口。</span><span class="sxs-lookup"><span data-stu-id="6a294-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a294-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a294-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="6a294-105">接口</span><span class="sxs-lookup"><span data-stu-id="6a294-105">Interfaces</span></span>  
  
|<span data-ttu-id="6a294-106">接口</span><span class="sxs-lookup"><span data-stu-id="6a294-106">Interface</span></span>|<span data-ttu-id="6a294-107">说明</span><span class="sxs-lookup"><span data-stu-id="6a294-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="6a294-108">提供用于在客户端进程中创建、初始化和管理代理的方法。</span><span class="sxs-lookup"><span data-stu-id="6a294-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a294-109">要求</span><span class="sxs-lookup"><span data-stu-id="6a294-109">Requirements</span></span>  
 <span data-ttu-id="6a294-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6a294-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a294-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6a294-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="6a294-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6a294-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a294-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a294-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a294-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a294-114">See also</span></span>

- [<span data-ttu-id="6a294-115">承载 Coclass</span><span class="sxs-lookup"><span data-stu-id="6a294-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
