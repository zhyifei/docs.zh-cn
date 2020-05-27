---
title: IMetaDataEmit::Merge 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: e7fe5cbe27c0771a71e4c03d14ab68ada7d0741a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004148"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="9b5e5-102">IMetaDataEmit::Merge 方法</span><span class="sxs-lookup"><span data-stu-id="9b5e5-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="9b5e5-103">将指定的导入范围添加到要合并的范围列表。</span><span class="sxs-lookup"><span data-stu-id="9b5e5-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b5e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="9b5e5-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b5e5-105">参数</span><span class="sxs-lookup"><span data-stu-id="9b5e5-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="9b5e5-106">中指向用于标识要合并的导入范围的[IMetaDataImport](imetadataimport-interface.md)对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9b5e5-106">[in] A pointer to an [IMetaDataImport](imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="9b5e5-107">中指向[IMapToken](imaptoken-interface.md)对象的指针，该对象指定标记重新映射。</span><span class="sxs-lookup"><span data-stu-id="9b5e5-107">[in] A pointer to an [IMapToken](imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="9b5e5-108">中指向指定错误的[IUnknown](/cpp/atl/iunknown)对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9b5e5-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b5e5-109">备注</span><span class="sxs-lookup"><span data-stu-id="9b5e5-109">Remarks</span></span>  
 <span data-ttu-id="9b5e5-110">调用[IMetaDataEmit：： MergeEnd](imetadataemit-mergeend-method.md)以触发将元数据合并到单个范围中。</span><span class="sxs-lookup"><span data-stu-id="9b5e5-110">Call [IMetaDataEmit::MergeEnd](imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b5e5-111">要求</span><span class="sxs-lookup"><span data-stu-id="9b5e5-111">Requirements</span></span>  
 <span data-ttu-id="9b5e5-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b5e5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b5e5-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="9b5e5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b5e5-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9b5e5-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b5e5-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b5e5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b5e5-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b5e5-116">See also</span></span>

- [<span data-ttu-id="9b5e5-117">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="9b5e5-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9b5e5-118">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="9b5e5-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
