---
title: IMetaDataEmit::SetFieldMarshal 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b65f3476da69249f449090e1f2d67c58ed5a427a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737291"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="b4c68-102">IMetaDataEmit::SetFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="b4c68-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="b4c68-103">设置 PInvoke 封送处理指定的标记所引用的字段、 方法将返回或方法参数的信息。</span><span class="sxs-lookup"><span data-stu-id="b4c68-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c68-104">语法</span><span class="sxs-lookup"><span data-stu-id="b4c68-104">Syntax</span></span>  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4c68-105">参数</span><span class="sxs-lookup"><span data-stu-id="b4c68-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b4c68-106">[in]目标数据的项的标记。</span><span class="sxs-lookup"><span data-stu-id="b4c68-106">[in] The token for target data item.</span></span> <span data-ttu-id="b4c68-107">这可以是`mdFieldDef`或`mdParamDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="b4c68-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="b4c68-108">[in]非托管类型的签名。</span><span class="sxs-lookup"><span data-stu-id="b4c68-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="b4c68-109">[in]中的字节计数`pvNativeType`。</span><span class="sxs-lookup"><span data-stu-id="b4c68-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4c68-110">要求</span><span class="sxs-lookup"><span data-stu-id="b4c68-110">Requirements</span></span>  
 <span data-ttu-id="b4c68-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b4c68-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4c68-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b4c68-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4c68-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b4c68-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4c68-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4c68-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c68-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4c68-115">See also</span></span>
- [<span data-ttu-id="b4c68-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="b4c68-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b4c68-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="b4c68-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
