---
title: "IMetaDataImport::GetRVA 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetRVA
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f64cc5b0aa6043c5408868a5a6bf23e24278ea26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="1b82e-102">IMetaDataImport::GetRVA 方法</span><span class="sxs-lookup"><span data-stu-id="1b82e-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="1b82e-103">获取相对虚拟地址 (RVA) 和方法或指定标记所表示的字段的实现标志。</span><span class="sxs-lookup"><span data-stu-id="1b82e-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b82e-104">语法</span><span class="sxs-lookup"><span data-stu-id="1b82e-104">Syntax</span></span>  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b82e-105">参数</span><span class="sxs-lookup"><span data-stu-id="1b82e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="1b82e-106">[in]表示要返回的 RVA 的代码对象的 MethodDef 或 FieldDef 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="1b82e-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="1b82e-107">如果此令牌为 FieldDef，字段必须是全局变量。</span><span class="sxs-lookup"><span data-stu-id="1b82e-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="1b82e-108">[out]指向由标记表示的代码对象的相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="1b82e-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="1b82e-109">[out]指向方法的实现标志的指针。</span><span class="sxs-lookup"><span data-stu-id="1b82e-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="1b82e-110">此值是从一个位掩码[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="1b82e-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="1b82e-111">值`pdwImplFlags`有效才`tk`是 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="1b82e-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b82e-112">要求</span><span class="sxs-lookup"><span data-stu-id="1b82e-112">Requirements</span></span>  
 <span data-ttu-id="1b82e-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1b82e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b82e-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1b82e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b82e-115">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1b82e-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1b82e-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b82e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b82e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b82e-117">See Also</span></span>  
 [<span data-ttu-id="1b82e-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="1b82e-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="1b82e-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="1b82e-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
