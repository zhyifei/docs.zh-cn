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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213358"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="be9d7-102">IInstallReferenceItem::GetReference 方法</span><span class="sxs-lookup"><span data-stu-id="be9d7-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="be9d7-103">获取一个指向[FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)结构由此[IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="be9d7-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be9d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="be9d7-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be9d7-105">参数</span><span class="sxs-lookup"><span data-stu-id="be9d7-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="be9d7-106">[out]返回`FUSION_INSTALL_REFERENCE`指针。</span><span class="sxs-lookup"><span data-stu-id="be9d7-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="be9d7-107">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="be9d7-107">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="be9d7-108">必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="be9d7-108">must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="be9d7-109">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="be9d7-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="be9d7-110">必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="be9d7-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be9d7-111">要求</span><span class="sxs-lookup"><span data-stu-id="be9d7-111">Requirements</span></span>  
 <span data-ttu-id="be9d7-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be9d7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be9d7-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="be9d7-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="be9d7-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="be9d7-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be9d7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="be9d7-115">See also</span></span>

- [<span data-ttu-id="be9d7-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="be9d7-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="be9d7-117">FUSION_INSTALL_REFERENCE 结构</span><span class="sxs-lookup"><span data-stu-id="be9d7-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
