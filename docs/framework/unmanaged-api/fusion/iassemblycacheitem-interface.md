---
title: "IAssemblyCacheItem 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 323b501efbdf309d5e0d595137407dd8289de17a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="1e3ba-102">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="1e3ba-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="1e3ba-103">表示全局程序集缓存中的单个程序集。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e3ba-104">方法</span><span class="sxs-lookup"><span data-stu-id="1e3ba-104">Methods</span></span>  
  
|<span data-ttu-id="1e3ba-105">方法</span><span class="sxs-lookup"><span data-stu-id="1e3ba-105">Method</span></span>|<span data-ttu-id="1e3ba-106">描述</span><span class="sxs-lookup"><span data-stu-id="1e3ba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e3ba-107">AbortItem 方法</span><span class="sxs-lookup"><span data-stu-id="1e3ba-107">AbortItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="1e3ba-108">允许在全局程序集缓存中的程序集，它将被释放之前执行清理操作。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="1e3ba-109">Commit 方法</span><span class="sxs-lookup"><span data-stu-id="1e3ba-109">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|<span data-ttu-id="1e3ba-110">提交对内存的缓存的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="1e3ba-111">CreateStream 方法</span><span class="sxs-lookup"><span data-stu-id="1e3ba-111">CreateStream Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|<span data-ttu-id="1e3ba-112">具有指定的名称和格式创建一个流。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e3ba-113">惠?</span><span class="sxs-lookup"><span data-stu-id="1e3ba-113">Requirements</span></span>  
 <span data-ttu-id="1e3ba-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e3ba-115">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1e3ba-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1e3ba-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e3ba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e3ba-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e3ba-117">See Also</span></span>  
 [<span data-ttu-id="1e3ba-118">合成接口</span><span class="sxs-lookup"><span data-stu-id="1e3ba-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="1e3ba-119">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="1e3ba-119">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)  
 [<span data-ttu-id="1e3ba-120">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="1e3ba-120">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
