---
title: IHostMemoryManager::AcquiredVirtualAddressSpace 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4675c34bfe8d1d79c184c43e5f7f5dd3a03be6a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200995"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="4a8f6-102">IHostMemoryManager::AcquiredVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="4a8f6-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="4a8f6-103">通知宿主公共语言运行时 (CLR) 已获得从操作系统指定的内存。</span><span class="sxs-lookup"><span data-stu-id="4a8f6-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a8f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a8f6-104">Syntax</span></span>  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a8f6-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a8f6-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="4a8f6-106">[in]起始内存地址。</span><span class="sxs-lookup"><span data-stu-id="4a8f6-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="4a8f6-107">[in]以字节为单位的内存的大小。</span><span class="sxs-lookup"><span data-stu-id="4a8f6-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a8f6-108">备注</span><span class="sxs-lookup"><span data-stu-id="4a8f6-108">Remarks</span></span>  
 <span data-ttu-id="4a8f6-109">`AcquiredVirtualAddressSpace`方法是回调方法，必须由主机应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="4a8f6-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="4a8f6-110">它是由 CLR 进行调用。</span><span class="sxs-lookup"><span data-stu-id="4a8f6-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a8f6-111">要求</span><span class="sxs-lookup"><span data-stu-id="4a8f6-111">Requirements</span></span>  
 <span data-ttu-id="4a8f6-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a8f6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a8f6-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4a8f6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a8f6-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4a8f6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4a8f6-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="4a8f6-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4a8f6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a8f6-116">See also</span></span>

- [<span data-ttu-id="4a8f6-117">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="4a8f6-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
