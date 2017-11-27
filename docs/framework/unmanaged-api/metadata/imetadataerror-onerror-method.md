---
title: "IMetaDataError::OnError 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataError.OnError
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7b8947f0bac8b51e704fbbb9085cf48740b3197d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="c2dbb-102">IMetaDataError::OnError 方法</span><span class="sxs-lookup"><span data-stu-id="c2dbb-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="c2dbb-103">提供在元数据合并过程中发生的错误的通知。</span><span class="sxs-lookup"><span data-stu-id="c2dbb-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2dbb-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2dbb-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2dbb-105">参数</span><span class="sxs-lookup"><span data-stu-id="c2dbb-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="c2dbb-106">[in]返回到调用方法的 HRESULT 错误值。</span><span class="sxs-lookup"><span data-stu-id="c2dbb-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="c2dbb-107">[in]出现错误时合并的代码对象的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="c2dbb-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2dbb-108">要求</span><span class="sxs-lookup"><span data-stu-id="c2dbb-108">Requirements</span></span>  
 <span data-ttu-id="c2dbb-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2dbb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2dbb-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c2dbb-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2dbb-111">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c2dbb-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2dbb-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2dbb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2dbb-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2dbb-113">See Also</span></span>  
 [<span data-ttu-id="c2dbb-114">IMetaDataError 接口</span><span class="sxs-lookup"><span data-stu-id="c2dbb-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
