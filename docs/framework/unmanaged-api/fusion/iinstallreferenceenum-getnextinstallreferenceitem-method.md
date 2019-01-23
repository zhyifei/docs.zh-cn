---
title: IInstallReferenceEnum::GetNextInstallReferenceItem 方法
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba2abaccfc4a9ae2d1f07677a49a72c980acda24
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607496"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="854f3-102">IInstallReferenceEnum::GetNextInstallReferenceItem 方法</span><span class="sxs-lookup"><span data-stu-id="854f3-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="854f3-103">获取一个指针指向下一步[IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)包含在此对象[IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="854f3-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="854f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="854f3-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="854f3-105">参数</span><span class="sxs-lookup"><span data-stu-id="854f3-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="854f3-106">[out]返回`IInstallReferenceItem`指针。</span><span class="sxs-lookup"><span data-stu-id="854f3-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="854f3-107">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="854f3-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="854f3-108">`dwFlags` 必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="854f3-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="854f3-109">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="854f3-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="854f3-110">`pvReserved` 必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="854f3-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="854f3-111">要求</span><span class="sxs-lookup"><span data-stu-id="854f3-111">Requirements</span></span>  
 <span data-ttu-id="854f3-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="854f3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="854f3-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="854f3-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="854f3-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="854f3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="854f3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="854f3-115">See also</span></span>
- [<span data-ttu-id="854f3-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="854f3-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="854f3-117">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="854f3-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
