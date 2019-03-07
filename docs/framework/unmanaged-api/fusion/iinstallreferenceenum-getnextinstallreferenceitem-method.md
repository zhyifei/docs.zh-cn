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
ms.openlocfilehash: c23494f8c0a977624b899f01e843ba3545a22fbb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501638"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="65591-102">IInstallReferenceEnum::GetNextInstallReferenceItem 方法</span><span class="sxs-lookup"><span data-stu-id="65591-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="65591-103">获取一个指针指向下一步[IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)包含在此对象[IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="65591-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65591-104">语法</span><span class="sxs-lookup"><span data-stu-id="65591-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65591-105">参数</span><span class="sxs-lookup"><span data-stu-id="65591-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="65591-106">[out]返回`IInstallReferenceItem`指针。</span><span class="sxs-lookup"><span data-stu-id="65591-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="65591-107">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="65591-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="65591-108">`dwFlags` 必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="65591-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="65591-109">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="65591-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="65591-110">`pvReserved` 必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="65591-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65591-111">要求</span><span class="sxs-lookup"><span data-stu-id="65591-111">Requirements</span></span>  
 <span data-ttu-id="65591-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65591-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65591-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="65591-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="65591-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65591-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65591-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="65591-115">See also</span></span>
- [<span data-ttu-id="65591-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="65591-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="65591-117">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="65591-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
