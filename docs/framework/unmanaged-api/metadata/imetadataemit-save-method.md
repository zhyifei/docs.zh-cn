---
title: "IMetaDataEmit::Save 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a11241894116f57889a15a184290cd95f2f4f54f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="de3f9-102">IMetaDataEmit::Save 方法</span><span class="sxs-lookup"><span data-stu-id="de3f9-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="de3f9-103">将所有元数据保存在当前范围内指定地址处的文件。</span><span class="sxs-lookup"><span data-stu-id="de3f9-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de3f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="de3f9-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de3f9-105">参数</span><span class="sxs-lookup"><span data-stu-id="de3f9-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="de3f9-106">[in]要将保存到的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="de3f9-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="de3f9-107">如果此值为 null，则内存中的副本将保存到最后一个已使用的位置。</span><span class="sxs-lookup"><span data-stu-id="de3f9-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="de3f9-108">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="de3f9-108">[in] Reserved.</span></span> <span data-ttu-id="de3f9-109">必须为零。</span><span class="sxs-lookup"><span data-stu-id="de3f9-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de3f9-110">惠?</span><span class="sxs-lookup"><span data-stu-id="de3f9-110">Requirements</span></span>  
 <span data-ttu-id="de3f9-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de3f9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de3f9-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de3f9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de3f9-113">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="de3f9-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de3f9-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de3f9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de3f9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="de3f9-115">See Also</span></span>  
 [<span data-ttu-id="de3f9-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="de3f9-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="de3f9-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="de3f9-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
