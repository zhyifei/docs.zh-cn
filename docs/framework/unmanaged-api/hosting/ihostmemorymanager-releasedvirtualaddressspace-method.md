---
title: IHostMemoryManager::ReleasedVirtualAddressSpace 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f6a3d425d4c2ae2146723a6acfc5ab9893f0fe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438436"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="ae3df-102">IHostMemoryManager::ReleasedVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="ae3df-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="ae3df-103">通知主机公共语言运行时 (CLR) 已完成使用指定的内存。</span><span class="sxs-lookup"><span data-stu-id="ae3df-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae3df-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae3df-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae3df-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae3df-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="ae3df-106">[in]指向要释放的内存的起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="ae3df-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae3df-107">备注</span><span class="sxs-lookup"><span data-stu-id="ae3df-107">Remarks</span></span>  
 <span data-ttu-id="ae3df-108">`ReleasedVirtualAddressSpace`方法是一个回调方法，必须在承载应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="ae3df-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="ae3df-109">它是由 CLR 调用。</span><span class="sxs-lookup"><span data-stu-id="ae3df-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae3df-110">要求</span><span class="sxs-lookup"><span data-stu-id="ae3df-110">Requirements</span></span>  
 <span data-ttu-id="ae3df-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae3df-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae3df-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ae3df-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ae3df-113">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ae3df-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae3df-114">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae3df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae3df-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae3df-115">See Also</span></span>  
 [<span data-ttu-id="ae3df-116">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="ae3df-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
