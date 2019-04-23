---
title: IInstallReferenceItem::GetReference 方法
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd0a554535122b81f5812102c7951f56b294796a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213358"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="645de-102">IInstallReferenceItem::GetReference 方法</span><span class="sxs-lookup"><span data-stu-id="645de-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="645de-103">获取一个指向[FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)结构由此[IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="645de-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="645de-104">语法</span><span class="sxs-lookup"><span data-stu-id="645de-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="645de-105">参数</span><span class="sxs-lookup"><span data-stu-id="645de-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="645de-106">[out]返回`FUSION_INSTALL_REFERENCE`指针。</span><span class="sxs-lookup"><span data-stu-id="645de-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="645de-107">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="645de-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="645de-108">`dwFlags` 必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="645de-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="645de-109">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="645de-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="645de-110">`pvReserved` 必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="645de-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="645de-111">要求</span><span class="sxs-lookup"><span data-stu-id="645de-111">Requirements</span></span>  
 <span data-ttu-id="645de-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="645de-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="645de-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="645de-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="645de-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="645de-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645de-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="645de-115">See also</span></span>

- [<span data-ttu-id="645de-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="645de-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="645de-117">FUSION_INSTALL_REFERENCE 结构</span><span class="sxs-lookup"><span data-stu-id="645de-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
