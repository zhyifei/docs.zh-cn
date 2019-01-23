---
title: IMetaDataEmit2::GetDeltaSaveSize 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb59fdb2249d798c70b1990a6bca41c5c14b80c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610560"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="d762b-102">IMetaDataEmit2::GetDeltaSaveSize 方法</span><span class="sxs-lookup"><span data-stu-id="d762b-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="d762b-103">获取一个值，该值指示元数据大小而导致编辑并继续在当前会话中的任何更改。</span><span class="sxs-lookup"><span data-stu-id="d762b-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d762b-104">语法</span><span class="sxs-lookup"><span data-stu-id="d762b-104">Syntax</span></span>  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d762b-105">参数</span><span class="sxs-lookup"><span data-stu-id="d762b-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="d762b-106">[in]之一[CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md)值，指示所需的精度级别。</span><span class="sxs-lookup"><span data-stu-id="d762b-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="d762b-107">对于.NET Framework 2.0 版中，将忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="d762b-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="d762b-108">[out]元数据的大小变化。</span><span class="sxs-lookup"><span data-stu-id="d762b-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d762b-109">要求</span><span class="sxs-lookup"><span data-stu-id="d762b-109">Requirements</span></span>  
 <span data-ttu-id="d762b-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d762b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d762b-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d762b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d762b-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d762b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d762b-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d762b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d762b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d762b-114">See also</span></span>
- [<span data-ttu-id="d762b-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="d762b-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="d762b-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="d762b-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
