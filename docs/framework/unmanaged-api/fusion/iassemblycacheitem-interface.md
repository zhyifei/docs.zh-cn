---
title: "IAssemblyCacheItem 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCacheItem
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCacheItem
helpviewer_keywords: IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e61b8dd90bb9311c1314a4cb4d68d75e0cd511c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="c46ca-102">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="c46ca-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="c46ca-103">表示全局程序集缓存中的单个程序集。</span><span class="sxs-lookup"><span data-stu-id="c46ca-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c46ca-104">方法</span><span class="sxs-lookup"><span data-stu-id="c46ca-104">Methods</span></span>  
  
|<span data-ttu-id="c46ca-105">方法</span><span class="sxs-lookup"><span data-stu-id="c46ca-105">Method</span></span>|<span data-ttu-id="c46ca-106">描述</span><span class="sxs-lookup"><span data-stu-id="c46ca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c46ca-107">AbortItem 方法</span><span class="sxs-lookup"><span data-stu-id="c46ca-107">AbortItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="c46ca-108">允许在全局程序集缓存中的程序集，它将被释放之前执行清理操作。</span><span class="sxs-lookup"><span data-stu-id="c46ca-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="c46ca-109">Commit 方法</span><span class="sxs-lookup"><span data-stu-id="c46ca-109">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|<span data-ttu-id="c46ca-110">提交对内存的缓存的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="c46ca-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="c46ca-111">CreateStream 方法</span><span class="sxs-lookup"><span data-stu-id="c46ca-111">CreateStream Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|<span data-ttu-id="c46ca-112">具有指定的名称和格式创建一个流。</span><span class="sxs-lookup"><span data-stu-id="c46ca-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c46ca-113">要求</span><span class="sxs-lookup"><span data-stu-id="c46ca-113">Requirements</span></span>  
 <span data-ttu-id="c46ca-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c46ca-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c46ca-115">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c46ca-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c46ca-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c46ca-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46ca-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c46ca-117">See Also</span></span>  
 [<span data-ttu-id="c46ca-118">合成接口</span><span class="sxs-lookup"><span data-stu-id="c46ca-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="c46ca-119">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="c46ca-119">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)  
 [<span data-ttu-id="c46ca-120">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="c46ca-120">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
