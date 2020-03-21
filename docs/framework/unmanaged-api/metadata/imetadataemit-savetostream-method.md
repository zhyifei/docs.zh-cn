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
ms.openlocfilehash: 7db27670b72a5018a03d4614b69486f67bcef155
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175676"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="49cbb-102">IMetaDataEmit::SaveToStream 方法</span><span class="sxs-lookup"><span data-stu-id="49cbb-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="49cbb-103">将当前作用域中的所有元数据保存到指定的`IStream`。</span><span class="sxs-lookup"><span data-stu-id="49cbb-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49cbb-104">语法</span><span class="sxs-lookup"><span data-stu-id="49cbb-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49cbb-105">parameters</span><span class="sxs-lookup"><span data-stu-id="49cbb-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="49cbb-106">[在]要保存到的可写流。</span><span class="sxs-lookup"><span data-stu-id="49cbb-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="49cbb-107">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="49cbb-107">[in] Reserved.</span></span> <span data-ttu-id="49cbb-108">必须为零。</span><span class="sxs-lookup"><span data-stu-id="49cbb-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49cbb-109">要求</span><span class="sxs-lookup"><span data-stu-id="49cbb-109">Requirements</span></span>  
 <span data-ttu-id="49cbb-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49cbb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49cbb-111">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="49cbb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49cbb-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="49cbb-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49cbb-113">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49cbb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49cbb-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49cbb-114">See also</span></span>

- [<span data-ttu-id="49cbb-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="49cbb-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="49cbb-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="49cbb-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
