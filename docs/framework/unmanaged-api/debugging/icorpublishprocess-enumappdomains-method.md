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
ms.openlocfilehash: aa76bf511ff1e1710a7ff86ad2ac97665969f2bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140440"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="337ca-102">ICorPublishProcess::EnumAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="337ca-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="337ca-103">获取此[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)引用的进程中的应用程序域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="337ca-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="337ca-104">语法</span><span class="sxs-lookup"><span data-stu-id="337ca-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="337ca-105">参数</span><span class="sxs-lookup"><span data-stu-id="337ca-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="337ca-106">弄一个指针，指向允许在此进程中通过应用程序域集合进行迭代的[ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)实例的地址。</span><span class="sxs-lookup"><span data-stu-id="337ca-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="337ca-107">备注</span><span class="sxs-lookup"><span data-stu-id="337ca-107">Remarks</span></span>  
 <span data-ttu-id="337ca-108">应用程序域的列表基于在调用 `EnumAppDomains` 方法时存在的应用程序域的快照。</span><span class="sxs-lookup"><span data-stu-id="337ca-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="337ca-109">可以多次调用此方法来创建新的最新列表。</span><span class="sxs-lookup"><span data-stu-id="337ca-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="337ca-110">此方法的后续调用将不会影响现有列表。</span><span class="sxs-lookup"><span data-stu-id="337ca-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="337ca-111">如果进程已终止，`EnumAppDomains` 将失败，HRESULT 值为 CORDBG_E_PROCESS_TERMINATED。</span><span class="sxs-lookup"><span data-stu-id="337ca-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="337ca-112">要求</span><span class="sxs-lookup"><span data-stu-id="337ca-112">Requirements</span></span>  
 <span data-ttu-id="337ca-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="337ca-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="337ca-114">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="337ca-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="337ca-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="337ca-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="337ca-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337ca-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337ca-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="337ca-117">See also</span></span>

- [<span data-ttu-id="337ca-118">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="337ca-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
