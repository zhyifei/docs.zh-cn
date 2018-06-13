---
title: IAssemblyCacheItem 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c6da86ce2d86a6842d2d7d8de860e9a8621bdaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429590"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="10111-102">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="10111-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="10111-103">表示全局程序集缓存中的单个程序集。</span><span class="sxs-lookup"><span data-stu-id="10111-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10111-104">方法</span><span class="sxs-lookup"><span data-stu-id="10111-104">Methods</span></span>  
  
|<span data-ttu-id="10111-105">方法</span><span class="sxs-lookup"><span data-stu-id="10111-105">Method</span></span>|<span data-ttu-id="10111-106">描述</span><span class="sxs-lookup"><span data-stu-id="10111-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10111-107">AbortItem 方法</span><span class="sxs-lookup"><span data-stu-id="10111-107">AbortItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="10111-108">允许在全局程序集缓存中的程序集，它将被释放之前执行清理操作。</span><span class="sxs-lookup"><span data-stu-id="10111-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="10111-109">Commit 方法</span><span class="sxs-lookup"><span data-stu-id="10111-109">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|<span data-ttu-id="10111-110">提交对内存的缓存的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="10111-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="10111-111">CreateStream 方法</span><span class="sxs-lookup"><span data-stu-id="10111-111">CreateStream Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|<span data-ttu-id="10111-112">具有指定的名称和格式创建一个流。</span><span class="sxs-lookup"><span data-stu-id="10111-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10111-113">要求</span><span class="sxs-lookup"><span data-stu-id="10111-113">Requirements</span></span>  
 <span data-ttu-id="10111-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="10111-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10111-115">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="10111-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="10111-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10111-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10111-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="10111-117">See Also</span></span>  
 [<span data-ttu-id="10111-118">合成接口</span><span class="sxs-lookup"><span data-stu-id="10111-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="10111-119">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="10111-119">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)  
 [<span data-ttu-id="10111-120">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="10111-120">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
