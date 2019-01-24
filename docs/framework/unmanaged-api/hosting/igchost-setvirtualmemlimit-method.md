---
title: IGCHost::SetVirtualMemLimit 方法
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d38b174a7e959647a9c1f5287b8acbbcdaf5ca7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564274"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="dde0b-102">IGCHost::SetVirtualMemLimit 方法</span><span class="sxs-lookup"><span data-stu-id="dde0b-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="dde0b-103">设置运行时的虚拟内存的最大大小。</span><span class="sxs-lookup"><span data-stu-id="dde0b-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde0b-104">语法</span><span class="sxs-lookup"><span data-stu-id="dde0b-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dde0b-105">参数</span><span class="sxs-lookup"><span data-stu-id="dde0b-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="dde0b-106">[in]最大大小，以兆字节为单位的运行时的虚拟内存。</span><span class="sxs-lookup"><span data-stu-id="dde0b-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dde0b-107">备注</span><span class="sxs-lookup"><span data-stu-id="dde0b-107">Remarks</span></span>  
 <span data-ttu-id="dde0b-108">可以动态更改运行时的虚拟内存的最大大小。</span><span class="sxs-lookup"><span data-stu-id="dde0b-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dde0b-109">要求</span><span class="sxs-lookup"><span data-stu-id="dde0b-109">Requirements</span></span>  
 <span data-ttu-id="dde0b-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dde0b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dde0b-111">**标头：** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="dde0b-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="dde0b-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dde0b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dde0b-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dde0b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde0b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="dde0b-114">See also</span></span>
- [<span data-ttu-id="dde0b-115">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="dde0b-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
