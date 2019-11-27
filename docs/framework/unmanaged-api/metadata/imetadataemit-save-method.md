---
title: IMetaDataEmit::Save 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: afd60cdf566bea459816ee890d44cc09258de516
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435945"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="16b93-102">IMetaDataEmit::Save 方法</span><span class="sxs-lookup"><span data-stu-id="16b93-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="16b93-103">将当前范围中的所有元数据保存到指定地址处的文件。</span><span class="sxs-lookup"><span data-stu-id="16b93-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16b93-104">语法</span><span class="sxs-lookup"><span data-stu-id="16b93-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16b93-105">参数</span><span class="sxs-lookup"><span data-stu-id="16b93-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="16b93-106">中要保存到的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="16b93-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="16b93-107">如果此值为 null，则内存中的副本将保存到上次使用的位置。</span><span class="sxs-lookup"><span data-stu-id="16b93-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="16b93-108">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="16b93-108">[in] Reserved.</span></span> <span data-ttu-id="16b93-109">必须为零。</span><span class="sxs-lookup"><span data-stu-id="16b93-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16b93-110">要求</span><span class="sxs-lookup"><span data-stu-id="16b93-110">Requirements</span></span>  
 <span data-ttu-id="16b93-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="16b93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16b93-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="16b93-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="16b93-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="16b93-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16b93-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16b93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b93-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16b93-115">See also</span></span>

- [<span data-ttu-id="16b93-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="16b93-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="16b93-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="16b93-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
