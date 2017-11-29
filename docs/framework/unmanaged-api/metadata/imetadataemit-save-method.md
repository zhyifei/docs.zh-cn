---
title: "IMetaDataEmit::Save 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.Save
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8a2e77ad9ce66a04ef0530dc41f9795c501eed9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="5ff4a-102">IMetaDataEmit::Save 方法</span><span class="sxs-lookup"><span data-stu-id="5ff4a-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="5ff4a-103">将所有元数据保存在当前范围内指定地址处的文件。</span><span class="sxs-lookup"><span data-stu-id="5ff4a-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff4a-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ff4a-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ff4a-105">参数</span><span class="sxs-lookup"><span data-stu-id="5ff4a-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="5ff4a-106">[in]要将保存到的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="5ff4a-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="5ff4a-107">如果此值为 null，则内存中的副本将保存到最后一个已使用的位置。</span><span class="sxs-lookup"><span data-stu-id="5ff4a-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="5ff4a-108">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="5ff4a-108">[in] Reserved.</span></span> <span data-ttu-id="5ff4a-109">必须为零。</span><span class="sxs-lookup"><span data-stu-id="5ff4a-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff4a-110">要求</span><span class="sxs-lookup"><span data-stu-id="5ff4a-110">Requirements</span></span>  
 <span data-ttu-id="5ff4a-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5ff4a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ff4a-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ff4a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ff4a-113">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5ff4a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ff4a-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ff4a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff4a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ff4a-115">See Also</span></span>  
 [<span data-ttu-id="5ff4a-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="5ff4a-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="5ff4a-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="5ff4a-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
