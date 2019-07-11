---
title: IManagedObject::GetObjectIdentity 方法
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 291246169a5cc2c95b117bc55bc269791885b2ea
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749101"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="001d4-102">IManagedObject::GetObjectIdentity 方法</span><span class="sxs-lookup"><span data-stu-id="001d4-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="001d4-103">获取此托管对象的标识。</span><span class="sxs-lookup"><span data-stu-id="001d4-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="001d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="001d4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="001d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="001d4-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="001d4-106">[out]指向该对象所驻留的进程的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="001d4-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="001d4-107">[out]指向对象的应用程序域的 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="001d4-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="001d4-108">[out]一个指向 COM 经典 v-表中的对象的索引。</span><span class="sxs-lookup"><span data-stu-id="001d4-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="001d4-109">备注</span><span class="sxs-lookup"><span data-stu-id="001d4-109">Remarks</span></span>  
 <span data-ttu-id="001d4-110">托管对象的标识包括 COM 经典 v-表中的进程 GUID、 应用程序域 ID 和对象的索引。</span><span class="sxs-lookup"><span data-stu-id="001d4-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="001d4-111">要求</span><span class="sxs-lookup"><span data-stu-id="001d4-111">Requirements</span></span>  
 <span data-ttu-id="001d4-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="001d4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="001d4-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="001d4-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="001d4-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="001d4-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="001d4-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="001d4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="001d4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="001d4-116">See also</span></span>

- [<span data-ttu-id="001d4-117">IManagedObject 接口</span><span class="sxs-lookup"><span data-stu-id="001d4-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
