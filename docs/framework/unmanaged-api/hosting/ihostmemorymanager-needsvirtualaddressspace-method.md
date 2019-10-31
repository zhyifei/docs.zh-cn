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
ms.openlocfilehash: a3ae474a73f4c8e4b98c4b2bc5d04e55bcae6874
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128666"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="a56c9-102">IHostMemoryManager::NeedsVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="a56c9-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="a56c9-103">向宿主通知公共语言运行时（CLR）将要尝试使用指定的内存。</span><span class="sxs-lookup"><span data-stu-id="a56c9-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a56c9-104">语法</span><span class="sxs-lookup"><span data-stu-id="a56c9-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a56c9-105">参数</span><span class="sxs-lookup"><span data-stu-id="a56c9-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="a56c9-106">中内存的起始地址。</span><span class="sxs-lookup"><span data-stu-id="a56c9-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="a56c9-107">中内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a56c9-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a56c9-108">备注</span><span class="sxs-lookup"><span data-stu-id="a56c9-108">Remarks</span></span>  
 <span data-ttu-id="a56c9-109">`NeedsVirtualAddressSpace` 方法是回调方法，必须由宿主应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="a56c9-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="a56c9-110">它由 CLR 调用。</span><span class="sxs-lookup"><span data-stu-id="a56c9-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="a56c9-111">如果主机不希望 CLR 使用指定的内存，则它可能会返回 E_OUTOFMEMORY HRESULT。</span><span class="sxs-lookup"><span data-stu-id="a56c9-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a56c9-112">要求</span><span class="sxs-lookup"><span data-stu-id="a56c9-112">Requirements</span></span>  
 <span data-ttu-id="a56c9-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a56c9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a56c9-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a56c9-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a56c9-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a56c9-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a56c9-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a56c9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a56c9-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a56c9-117">See also</span></span>

- [<span data-ttu-id="a56c9-118">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="a56c9-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
