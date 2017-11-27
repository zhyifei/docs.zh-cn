---
title: "ComCallUnmarshal 组件类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ComCallUnmarshal Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: ComCallUnmarshal
helpviewer_keywords: ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2760fc84466c85e022421bcc17dcee6444ec859a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="2c408-102">ComCallUnmarshal 组件类</span><span class="sxs-lookup"><span data-stu-id="2c408-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="2c408-103">提供用于管理的接口指针的封送处理的接口。</span><span class="sxs-lookup"><span data-stu-id="2c408-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c408-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c408-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="2c408-105">接口</span><span class="sxs-lookup"><span data-stu-id="2c408-105">Interfaces</span></span>  
  
|<span data-ttu-id="2c408-106">接口</span><span class="sxs-lookup"><span data-stu-id="2c408-106">Interface</span></span>|<span data-ttu-id="2c408-107">描述</span><span class="sxs-lookup"><span data-stu-id="2c408-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="2c408-108">提供用于创建、 初始化和管理在客户端进程中的代理方法。</span><span class="sxs-lookup"><span data-stu-id="2c408-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c408-109">要求</span><span class="sxs-lookup"><span data-stu-id="2c408-109">Requirements</span></span>  
 <span data-ttu-id="2c408-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c408-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c408-111">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="2c408-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="2c408-112">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2c408-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c408-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c408-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c408-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c408-114">See Also</span></span>  
 [<span data-ttu-id="2c408-115">承载组件类</span><span class="sxs-lookup"><span data-stu-id="2c408-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
