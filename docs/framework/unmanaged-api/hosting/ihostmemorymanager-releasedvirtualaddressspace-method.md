---
title: "IHostMemoryManager::ReleasedVirtualAddressSpace 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.ReleasedVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c0f2588c34429366794fcfb30c6d6e7038814506
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="74343-102">IHostMemoryManager::ReleasedVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="74343-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="74343-103">通知主机公共语言运行时 (CLR) 已完成使用指定的内存。</span><span class="sxs-lookup"><span data-stu-id="74343-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74343-104">语法</span><span class="sxs-lookup"><span data-stu-id="74343-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74343-105">参数</span><span class="sxs-lookup"><span data-stu-id="74343-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="74343-106">[in]指向要释放的内存的起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="74343-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74343-107">备注</span><span class="sxs-lookup"><span data-stu-id="74343-107">Remarks</span></span>  
 <span data-ttu-id="74343-108">`ReleasedVirtualAddressSpace`方法是一个回调方法，必须在承载应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="74343-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="74343-109">它是由 CLR 调用。</span><span class="sxs-lookup"><span data-stu-id="74343-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74343-110">要求</span><span class="sxs-lookup"><span data-stu-id="74343-110">Requirements</span></span>  
 <span data-ttu-id="74343-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="74343-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74343-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74343-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74343-113">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="74343-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74343-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74343-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74343-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74343-115">See Also</span></span>  
 [<span data-ttu-id="74343-116">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="74343-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
