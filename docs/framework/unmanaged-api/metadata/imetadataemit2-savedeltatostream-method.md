---
title: "IMetaDataEmit2::SaveDeltaToStream 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SaveDeltaToStream
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4bab7bd9035c0746b7f789925e23b74e2caade6a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="f1379-102">IMetaDataEmit2::SaveDeltaToStream 方法</span><span class="sxs-lookup"><span data-stu-id="f1379-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="f1379-103">将更改从当前的编辑并继续会话保存到指定的流。</span><span class="sxs-lookup"><span data-stu-id="f1379-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1379-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1379-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1379-105">参数</span><span class="sxs-lookup"><span data-stu-id="f1379-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="f1379-106">[in]指向要将更改保存到的可写流的接口指针。</span><span class="sxs-lookup"><span data-stu-id="f1379-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="f1379-107">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="f1379-107">[in] Reserved.</span></span> <span data-ttu-id="f1379-108">此值必须为零。</span><span class="sxs-lookup"><span data-stu-id="f1379-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1379-109">要求</span><span class="sxs-lookup"><span data-stu-id="f1379-109">Requirements</span></span>  
 <span data-ttu-id="f1379-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1379-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1379-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1379-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1379-112">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f1379-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1379-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1379-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1379-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1379-114">See Also</span></span>  
 [<span data-ttu-id="f1379-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="f1379-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="f1379-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="f1379-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
