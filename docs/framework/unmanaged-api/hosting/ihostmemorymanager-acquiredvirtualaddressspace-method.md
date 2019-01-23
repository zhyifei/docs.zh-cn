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
ms.openlocfilehash: b6133b558e62d66cfaac201317f66d784aac264c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513706"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="01611-102">IHostMemoryManager::AcquiredVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="01611-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="01611-103">通知宿主公共语言运行时 (CLR) 已获得从操作系统指定的内存。</span><span class="sxs-lookup"><span data-stu-id="01611-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01611-104">语法</span><span class="sxs-lookup"><span data-stu-id="01611-104">Syntax</span></span>  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01611-105">参数</span><span class="sxs-lookup"><span data-stu-id="01611-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="01611-106">[in]起始内存地址。</span><span class="sxs-lookup"><span data-stu-id="01611-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="01611-107">[in]以字节为单位的内存的大小。</span><span class="sxs-lookup"><span data-stu-id="01611-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01611-108">备注</span><span class="sxs-lookup"><span data-stu-id="01611-108">Remarks</span></span>  
 <span data-ttu-id="01611-109">`AcquiredVirtualAddressSpace`方法是回调方法，必须由主机应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="01611-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="01611-110">它是由 CLR 进行调用。</span><span class="sxs-lookup"><span data-stu-id="01611-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01611-111">要求</span><span class="sxs-lookup"><span data-stu-id="01611-111">Requirements</span></span>  
 <span data-ttu-id="01611-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01611-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01611-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01611-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01611-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="01611-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01611-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01611-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01611-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="01611-116">See also</span></span>
- [<span data-ttu-id="01611-117">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="01611-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
