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
ms.openlocfilehash: 4a246fb95ab5b4a7f187aa660f20e590c63ddff2
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804457"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="3d0ca-102">IHostMemoryManager::ReleasedVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="3d0ca-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="3d0ca-103">向宿主通知公共语言运行时（CLR）已使用指定的内存完成。</span><span class="sxs-lookup"><span data-stu-id="3d0ca-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d0ca-104">语法</span><span class="sxs-lookup"><span data-stu-id="3d0ca-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d0ca-105">参数</span><span class="sxs-lookup"><span data-stu-id="3d0ca-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="3d0ca-106">中指向要释放的内存的起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3d0ca-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d0ca-107">备注</span><span class="sxs-lookup"><span data-stu-id="3d0ca-107">Remarks</span></span>  
 <span data-ttu-id="3d0ca-108">`ReleasedVirtualAddressSpace`方法是一个回调方法，必须由宿主应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="3d0ca-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="3d0ca-109">它由 CLR 调用。</span><span class="sxs-lookup"><span data-stu-id="3d0ca-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d0ca-110">要求</span><span class="sxs-lookup"><span data-stu-id="3d0ca-110">Requirements</span></span>  
 <span data-ttu-id="3d0ca-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3d0ca-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d0ca-112">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3d0ca-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d0ca-113">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="3d0ca-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d0ca-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d0ca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d0ca-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d0ca-115">See also</span></span>

- [<span data-ttu-id="3d0ca-116">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="3d0ca-116">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
