---
title: "IHostMemoryManager::NeedsVirtualAddressSpace 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.NeedsVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62ceb9e5b4d5843b8e2adad344b3ffb662ab3aff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="96f2a-102">IHostMemoryManager::NeedsVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="96f2a-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="96f2a-103">通知宿主，公共语言运行时 (CLR) 将尝试使用指定的内存。</span><span class="sxs-lookup"><span data-stu-id="96f2a-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96f2a-104">语法</span><span class="sxs-lookup"><span data-stu-id="96f2a-104">Syntax</span></span>  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96f2a-105">参数</span><span class="sxs-lookup"><span data-stu-id="96f2a-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="96f2a-106">[in]内存起始地址。</span><span class="sxs-lookup"><span data-stu-id="96f2a-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="96f2a-107">[in]以字节为单位，内存的大小。</span><span class="sxs-lookup"><span data-stu-id="96f2a-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96f2a-108">备注</span><span class="sxs-lookup"><span data-stu-id="96f2a-108">Remarks</span></span>  
 <span data-ttu-id="96f2a-109">`NeedsVirtualAddressSpace`方法是一个回调方法，必须在承载应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="96f2a-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="96f2a-110">它是由 CLR 调用。</span><span class="sxs-lookup"><span data-stu-id="96f2a-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="96f2a-111">如果主机不希望 CLR 使用指定的内存，它可能返回 E_OUTOFMEMORY HRESULT。</span><span class="sxs-lookup"><span data-stu-id="96f2a-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96f2a-112">要求</span><span class="sxs-lookup"><span data-stu-id="96f2a-112">Requirements</span></span>  
 <span data-ttu-id="96f2a-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="96f2a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96f2a-114">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="96f2a-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96f2a-115">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="96f2a-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96f2a-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96f2a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96f2a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96f2a-117">See Also</span></span>  
 [<span data-ttu-id="96f2a-118">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="96f2a-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
