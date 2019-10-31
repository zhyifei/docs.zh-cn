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
ms.openlocfilehash: 014bd4f2b12c84790065f76a67765aaf35e8b2d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131681"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="580d2-102">IInstallReferenceItem::GetReference 方法</span><span class="sxs-lookup"><span data-stu-id="580d2-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="580d2-103">获取一个指针，该指针指向此[IInstallReferenceItem](iinstallreferenceitem-interface.md)对象表示的[FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="580d2-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="580d2-104">语法</span><span class="sxs-lookup"><span data-stu-id="580d2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="580d2-105">参数</span><span class="sxs-lookup"><span data-stu-id="580d2-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="580d2-106">弄返回的 `FUSION_INSTALL_REFERENCE` 指针。</span><span class="sxs-lookup"><span data-stu-id="580d2-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="580d2-107">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="580d2-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="580d2-108">`dwFlags` 必须为0（零）。</span><span class="sxs-lookup"><span data-stu-id="580d2-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="580d2-109">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="580d2-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="580d2-110">`pvReserved` 必须为空引用。</span><span class="sxs-lookup"><span data-stu-id="580d2-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="580d2-111">要求</span><span class="sxs-lookup"><span data-stu-id="580d2-111">Requirements</span></span>  
 <span data-ttu-id="580d2-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="580d2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="580d2-113">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="580d2-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="580d2-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="580d2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="580d2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="580d2-115">See also</span></span>

- [<span data-ttu-id="580d2-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="580d2-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="580d2-117">FUSION_INSTALL_REFERENCE 结构</span><span class="sxs-lookup"><span data-stu-id="580d2-117">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
