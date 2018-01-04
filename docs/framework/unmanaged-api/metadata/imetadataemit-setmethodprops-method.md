---
title: "IMetaDataEmit::SetMethodProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetMethodProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28ec0ba45a83ccf51cc84ee9deb2c658b9b106bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="1333d-102">IMetaDataEmit::SetMethodProps 方法</span><span class="sxs-lookup"><span data-stu-id="1333d-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="1333d-103">设置或更新的功能，存储在指定的相对虚拟地址，通过调用定义的方法的[imetadataemit:: Definemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="1333d-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1333d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1333d-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1333d-105">参数</span><span class="sxs-lookup"><span data-stu-id="1333d-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="1333d-106">[in]要更改方法的标记。</span><span class="sxs-lookup"><span data-stu-id="1333d-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="1333d-107">[in]成员属性。</span><span class="sxs-lookup"><span data-stu-id="1333d-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="1333d-108">[in]代码的地址。</span><span class="sxs-lookup"><span data-stu-id="1333d-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="1333d-109">[in]此方法实现标志。</span><span class="sxs-lookup"><span data-stu-id="1333d-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1333d-110">惠?</span><span class="sxs-lookup"><span data-stu-id="1333d-110">Requirements</span></span>  
 <span data-ttu-id="1333d-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1333d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1333d-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1333d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1333d-113">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1333d-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1333d-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1333d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1333d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1333d-115">See Also</span></span>  
 [<span data-ttu-id="1333d-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="1333d-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="1333d-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="1333d-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
