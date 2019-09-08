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
ms.openlocfilehash: 193604068e379d62107b25f2bc348cd7c8bc6e98
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796705"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="24e2b-102">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="24e2b-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="24e2b-103">表示全局程序集缓存中的单个程序集。</span><span class="sxs-lookup"><span data-stu-id="24e2b-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24e2b-104">方法</span><span class="sxs-lookup"><span data-stu-id="24e2b-104">Methods</span></span>  
  
|<span data-ttu-id="24e2b-105">方法</span><span class="sxs-lookup"><span data-stu-id="24e2b-105">Method</span></span>|<span data-ttu-id="24e2b-106">描述</span><span class="sxs-lookup"><span data-stu-id="24e2b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24e2b-107">AbortItem 方法</span><span class="sxs-lookup"><span data-stu-id="24e2b-107">AbortItem Method</span></span>](iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="24e2b-108">允许全局程序集缓存中的程序集在发布前执行清除操作。</span><span class="sxs-lookup"><span data-stu-id="24e2b-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="24e2b-109">Commit 方法</span><span class="sxs-lookup"><span data-stu-id="24e2b-109">Commit Method</span></span>](iassemblycacheitem-commit-method.md)|<span data-ttu-id="24e2b-110">将缓存的程序集引用提交到内存。</span><span class="sxs-lookup"><span data-stu-id="24e2b-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="24e2b-111">CreateStream 方法</span><span class="sxs-lookup"><span data-stu-id="24e2b-111">CreateStream Method</span></span>](iassemblycacheitem-createstream-method.md)|<span data-ttu-id="24e2b-112">创建具有指定名称和格式的流。</span><span class="sxs-lookup"><span data-stu-id="24e2b-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24e2b-113">要求</span><span class="sxs-lookup"><span data-stu-id="24e2b-113">Requirements</span></span>  
 <span data-ttu-id="24e2b-114">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24e2b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24e2b-115">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="24e2b-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="24e2b-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24e2b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e2b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="24e2b-117">See also</span></span>

- [<span data-ttu-id="24e2b-118">合成接口</span><span class="sxs-lookup"><span data-stu-id="24e2b-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="24e2b-119">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="24e2b-119">Global Assembly Cache</span></span>](../../app-domains/gac.md)
- [<span data-ttu-id="24e2b-120">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="24e2b-120">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
