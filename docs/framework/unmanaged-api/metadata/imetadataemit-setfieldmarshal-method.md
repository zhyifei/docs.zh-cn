---
title: "IMetaDataEmit::SetFieldMarshal 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetFieldMarshal
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3ef1d50d0d74a92a5bcaf23981226e5a6c852edd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="c2b38-102">IMetaDataEmit::SetFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="c2b38-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="c2b38-103">设置 PInvoke 封送处理指定的标记所引用的字段、 方法返回或方法参数的信息。</span><span class="sxs-lookup"><span data-stu-id="c2b38-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2b38-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2b38-104">Syntax</span></span>  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2b38-105">参数</span><span class="sxs-lookup"><span data-stu-id="c2b38-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c2b38-106">[in]目标数据项的标记。</span><span class="sxs-lookup"><span data-stu-id="c2b38-106">[in] The token for target data item.</span></span> <span data-ttu-id="c2b38-107">这可以是`mdFieldDef`或`mdParamDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="c2b38-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="c2b38-108">[in]非托管类型的签名。</span><span class="sxs-lookup"><span data-stu-id="c2b38-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="c2b38-109">[in]中的字节计数`pvNativeType`。</span><span class="sxs-lookup"><span data-stu-id="c2b38-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2b38-110">要求</span><span class="sxs-lookup"><span data-stu-id="c2b38-110">Requirements</span></span>  
 <span data-ttu-id="c2b38-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2b38-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2b38-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c2b38-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2b38-113">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c2b38-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2b38-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2b38-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b38-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2b38-115">See Also</span></span>  
 [<span data-ttu-id="c2b38-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="c2b38-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c2b38-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="c2b38-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
