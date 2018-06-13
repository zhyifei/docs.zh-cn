---
title: IHostMemoryManager::NeedsVirtualAddressSpace 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87c97a678fce4c25a113670a4668515a898e5251
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438413"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="e9388-102">IHostMemoryManager::NeedsVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="e9388-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="e9388-103">通知宿主，公共语言运行时 (CLR) 将尝试使用指定的内存。</span><span class="sxs-lookup"><span data-stu-id="e9388-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9388-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9388-104">Syntax</span></span>  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9388-105">参数</span><span class="sxs-lookup"><span data-stu-id="e9388-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="e9388-106">[in]内存起始地址。</span><span class="sxs-lookup"><span data-stu-id="e9388-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="e9388-107">[in]以字节为单位，内存的大小。</span><span class="sxs-lookup"><span data-stu-id="e9388-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9388-108">备注</span><span class="sxs-lookup"><span data-stu-id="e9388-108">Remarks</span></span>  
 <span data-ttu-id="e9388-109">`NeedsVirtualAddressSpace`方法是一个回调方法，必须在承载应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="e9388-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="e9388-110">它是由 CLR 调用。</span><span class="sxs-lookup"><span data-stu-id="e9388-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="e9388-111">如果主机不希望 CLR 使用指定的内存，它可能返回 E_OUTOFMEMORY HRESULT。</span><span class="sxs-lookup"><span data-stu-id="e9388-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9388-112">要求</span><span class="sxs-lookup"><span data-stu-id="e9388-112">Requirements</span></span>  
 <span data-ttu-id="e9388-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9388-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9388-114">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9388-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9388-115">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e9388-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9388-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9388-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9388-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9388-117">See Also</span></span>  
 [<span data-ttu-id="e9388-118">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="e9388-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
