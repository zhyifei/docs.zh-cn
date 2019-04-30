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
ms.openlocfilehash: 6d014d2900ea790f84331ed933143513ae9e63f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61943503"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="b60a1-102">IManagedObject::GetObjectIdentity 方法</span><span class="sxs-lookup"><span data-stu-id="b60a1-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="b60a1-103">获取此托管对象的标识。</span><span class="sxs-lookup"><span data-stu-id="b60a1-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b60a1-104">语法</span><span class="sxs-lookup"><span data-stu-id="b60a1-104">Syntax</span></span>  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b60a1-105">参数</span><span class="sxs-lookup"><span data-stu-id="b60a1-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="b60a1-106">[out]指向该对象所驻留的进程的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="b60a1-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="b60a1-107">[out]指向对象的应用程序域的 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="b60a1-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="b60a1-108">[out]一个指向 COM 经典 v-表中的对象的索引。</span><span class="sxs-lookup"><span data-stu-id="b60a1-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b60a1-109">备注</span><span class="sxs-lookup"><span data-stu-id="b60a1-109">Remarks</span></span>  
 <span data-ttu-id="b60a1-110">托管对象的标识包括 COM 经典 v-表中的进程 GUID、 应用程序域 ID 和对象的索引。</span><span class="sxs-lookup"><span data-stu-id="b60a1-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b60a1-111">要求</span><span class="sxs-lookup"><span data-stu-id="b60a1-111">Requirements</span></span>  
 <span data-ttu-id="b60a1-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b60a1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b60a1-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b60a1-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b60a1-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b60a1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b60a1-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b60a1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60a1-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b60a1-116">See also</span></span>

- [<span data-ttu-id="b60a1-117">IManagedObject 接口</span><span class="sxs-lookup"><span data-stu-id="b60a1-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
