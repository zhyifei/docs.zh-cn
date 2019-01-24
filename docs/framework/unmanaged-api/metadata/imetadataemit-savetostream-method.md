---
title: IMetaDataEmit::SaveToStream 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 515e925c9b086823450b73cfbb558d0409b4948a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575994"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="c5397-102">IMetaDataEmit::SaveToStream 方法</span><span class="sxs-lookup"><span data-stu-id="c5397-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="c5397-103">将所有元数据保存在当前作用域为指定`IStream`。</span><span class="sxs-lookup"><span data-stu-id="c5397-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5397-104">语法</span><span class="sxs-lookup"><span data-stu-id="c5397-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5397-105">参数</span><span class="sxs-lookup"><span data-stu-id="c5397-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="c5397-106">[in]要将保存到的可写流。</span><span class="sxs-lookup"><span data-stu-id="c5397-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="c5397-107">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="c5397-107">[in] Reserved.</span></span> <span data-ttu-id="c5397-108">必须为零。</span><span class="sxs-lookup"><span data-stu-id="c5397-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5397-109">要求</span><span class="sxs-lookup"><span data-stu-id="c5397-109">Requirements</span></span>  
 <span data-ttu-id="c5397-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c5397-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5397-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c5397-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5397-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c5397-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5397-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5397-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5397-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5397-114">See also</span></span>
- [<span data-ttu-id="c5397-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="c5397-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c5397-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="c5397-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
