---
title: ICorPublishProcess::EnumAppDomains 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 173a7d6793bec9262efb661d56e3a371d0bf9b47
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164601"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="22804-102">ICorPublishProcess::EnumAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="22804-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="22804-103">获取可枚举的应用程序域中引用此进程[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="22804-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22804-104">语法</span><span class="sxs-lookup"><span data-stu-id="22804-104">Syntax</span></span>  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22804-105">参数</span><span class="sxs-lookup"><span data-stu-id="22804-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="22804-106">[out]指向的地址的指针[ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)允许遍历此过程中的应用程序域的集合的实例。</span><span class="sxs-lookup"><span data-stu-id="22804-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22804-107">备注</span><span class="sxs-lookup"><span data-stu-id="22804-107">Remarks</span></span>  
 <span data-ttu-id="22804-108">应用程序域的列表取决于存在的应用程序域的快照时`EnumAppDomains`调用方法。</span><span class="sxs-lookup"><span data-stu-id="22804-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="22804-109">若要创建新的最新列表，可能会超过一次调用此方法。</span><span class="sxs-lookup"><span data-stu-id="22804-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="22804-110">此方法的后续调用不会影响现有列表。</span><span class="sxs-lookup"><span data-stu-id="22804-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="22804-111">如果进程已终止，`EnumAppDomains`将因 CORDBG_E_PROCESS_TERMINATED 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="22804-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22804-112">要求</span><span class="sxs-lookup"><span data-stu-id="22804-112">Requirements</span></span>  
 <span data-ttu-id="22804-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22804-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22804-114">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="22804-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="22804-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22804-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22804-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22804-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22804-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="22804-117">See also</span></span>

- [<span data-ttu-id="22804-118">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="22804-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
