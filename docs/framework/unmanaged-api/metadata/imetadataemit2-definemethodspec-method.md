---
title: "IMetaDataEmit2::DefineMethodSpec 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.DefineMethodSpec
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 036654c733dc73d40c526bf5cad4dd3750e2e9d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="5171e-102">IMetaDataEmit2::DefineMethodSpec 方法</span><span class="sxs-lookup"><span data-stu-id="5171e-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="5171e-103">创建的泛型实例方法，并获取指向定义的标记。</span><span class="sxs-lookup"><span data-stu-id="5171e-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5171e-104">语法</span><span class="sxs-lookup"><span data-stu-id="5171e-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5171e-105">参数</span><span class="sxs-lookup"><span data-stu-id="5171e-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="5171e-106">[in]要创建泛型实例方法标记。</span><span class="sxs-lookup"><span data-stu-id="5171e-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="5171e-107">令牌的类型必须为`mdMethodDef`或`mdMemberRef`。</span><span class="sxs-lookup"><span data-stu-id="5171e-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="5171e-108">[in]指向二进制 COM + 方法的签名的指针。</span><span class="sxs-lookup"><span data-stu-id="5171e-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="5171e-109">[in]大小，以字节为单位的`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="5171e-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="5171e-110">[out]指向方法的元数据签名定义的标记。</span><span class="sxs-lookup"><span data-stu-id="5171e-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5171e-111">要求</span><span class="sxs-lookup"><span data-stu-id="5171e-111">Requirements</span></span>  
 <span data-ttu-id="5171e-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5171e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5171e-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5171e-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5171e-114">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5171e-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5171e-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5171e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5171e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5171e-116">See Also</span></span>  
 [<span data-ttu-id="5171e-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="5171e-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="5171e-118">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="5171e-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
