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
ms.openlocfilehash: 1b40ed8e107d30c22b4ade25d29376b1b74583d1
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842408"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="b2564-102">IManagedObject::GetObjectIdentity 方法</span><span class="sxs-lookup"><span data-stu-id="b2564-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="b2564-103">获取此托管对象的标识。</span><span class="sxs-lookup"><span data-stu-id="b2564-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2564-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2564-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2564-105">参数</span><span class="sxs-lookup"><span data-stu-id="b2564-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="b2564-106">弄指向对象所在的进程的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="b2564-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="b2564-107">弄指向对象的应用程序域的 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="b2564-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="b2564-108">弄指向 COM 经典 v 表中对象索引的指针。</span><span class="sxs-lookup"><span data-stu-id="b2564-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2564-109">备注</span><span class="sxs-lookup"><span data-stu-id="b2564-109">Remarks</span></span>  
 <span data-ttu-id="b2564-110">托管对象的标识包括进程 GUID、应用程序域 ID 以及 COM 经典 v 表中对象的索引。</span><span class="sxs-lookup"><span data-stu-id="b2564-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2564-111">要求</span><span class="sxs-lookup"><span data-stu-id="b2564-111">Requirements</span></span>  
 <span data-ttu-id="b2564-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2564-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2564-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b2564-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2564-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b2564-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2564-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2564-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2564-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2564-116">See also</span></span>

- [<span data-ttu-id="b2564-117">IManagedObject 接口</span><span class="sxs-lookup"><span data-stu-id="b2564-117">IManagedObject Interface</span></span>](imanagedobject-interface.md)
