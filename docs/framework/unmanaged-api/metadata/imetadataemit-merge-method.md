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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 179cfc5c0725934e21d7b89a2f8d4c934b049f78
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106049"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="5c696-102">IMetaDataEmit::Merge 方法</span><span class="sxs-lookup"><span data-stu-id="5c696-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="5c696-103">将指定的导入的范围添加到要合并的范围列表。</span><span class="sxs-lookup"><span data-stu-id="5c696-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c696-104">语法</span><span class="sxs-lookup"><span data-stu-id="5c696-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c696-105">参数</span><span class="sxs-lookup"><span data-stu-id="5c696-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="5c696-106">[in]一个指向[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)对象，用于标识要合并的导入的作用域。</span><span class="sxs-lookup"><span data-stu-id="5c696-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="5c696-107">[in]一个指向[IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)对象，它指定标记重新映射。</span><span class="sxs-lookup"><span data-stu-id="5c696-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandleer`  
 <span data-ttu-id="5c696-108">[in]一个指向[IUnknown](/cpp/atl/iunknown)对象，它指定了错误。</span><span class="sxs-lookup"><span data-stu-id="5c696-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c696-109">备注</span><span class="sxs-lookup"><span data-stu-id="5c696-109">Remarks</span></span>  
 <span data-ttu-id="5c696-110">调用[imetadataemit:: Mergeend](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)触发的元数据合并到单个作用域。</span><span class="sxs-lookup"><span data-stu-id="5c696-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c696-111">要求</span><span class="sxs-lookup"><span data-stu-id="5c696-111">Requirements</span></span>  
 <span data-ttu-id="5c696-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c696-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c696-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5c696-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c696-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5c696-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5c696-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5c696-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c696-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c696-116">See also</span></span>

- [<span data-ttu-id="5c696-117">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="5c696-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5c696-118">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="5c696-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
