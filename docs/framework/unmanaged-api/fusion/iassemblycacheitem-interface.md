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
ms.openlocfilehash: fba17a2ffad9220acdbc79726efe0d3d4184978a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188547"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="15e6e-102">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="15e6e-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="15e6e-103">表示全局程序集缓存中的单个程序集。</span><span class="sxs-lookup"><span data-stu-id="15e6e-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15e6e-104">方法</span><span class="sxs-lookup"><span data-stu-id="15e6e-104">Methods</span></span>  
  
|<span data-ttu-id="15e6e-105">方法</span><span class="sxs-lookup"><span data-stu-id="15e6e-105">Method</span></span>|<span data-ttu-id="15e6e-106">描述</span><span class="sxs-lookup"><span data-stu-id="15e6e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15e6e-107">AbortItem 方法</span><span class="sxs-lookup"><span data-stu-id="15e6e-107">AbortItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="15e6e-108">允许在全局程序集缓存中的程序集以进行发布之前执行清理操作。</span><span class="sxs-lookup"><span data-stu-id="15e6e-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="15e6e-109">Commit 方法</span><span class="sxs-lookup"><span data-stu-id="15e6e-109">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|<span data-ttu-id="15e6e-110">提交对内存的缓存程序集引用。</span><span class="sxs-lookup"><span data-stu-id="15e6e-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="15e6e-111">CreateStream 方法</span><span class="sxs-lookup"><span data-stu-id="15e6e-111">CreateStream Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|<span data-ttu-id="15e6e-112">创建具有指定的名称和格式的流。</span><span class="sxs-lookup"><span data-stu-id="15e6e-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15e6e-113">要求</span><span class="sxs-lookup"><span data-stu-id="15e6e-113">Requirements</span></span>  
 <span data-ttu-id="15e6e-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15e6e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15e6e-115">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="15e6e-115">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="15e6e-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="15e6e-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="15e6e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="15e6e-117">See also</span></span>

- [<span data-ttu-id="15e6e-118">合成接口</span><span class="sxs-lookup"><span data-stu-id="15e6e-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="15e6e-119">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="15e6e-119">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
- [<span data-ttu-id="15e6e-120">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="15e6e-120">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
