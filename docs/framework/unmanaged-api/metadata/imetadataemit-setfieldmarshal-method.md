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
ms.openlocfilehash: 1037cd4210605192870d43d88979b89af6536380
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175650"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="f5214-102">IMetaDataEmit::SetFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="f5214-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="f5214-103">为指定令牌引用的字段、方法返回或方法参数设置 PInvoke 封送信息。</span><span class="sxs-lookup"><span data-stu-id="f5214-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5214-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5214-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5214-105">parameters</span><span class="sxs-lookup"><span data-stu-id="f5214-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f5214-106">[在]目标数据项的令牌。</span><span class="sxs-lookup"><span data-stu-id="f5214-106">[in] The token for target data item.</span></span> <span data-ttu-id="f5214-107">这是 或`mdFieldDef``mdParamDef`标记。</span><span class="sxs-lookup"><span data-stu-id="f5214-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="f5214-108">[在]非托管类型的签名。</span><span class="sxs-lookup"><span data-stu-id="f5214-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="f5214-109">[在]中的`pvNativeType`字节计数。</span><span class="sxs-lookup"><span data-stu-id="f5214-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5214-110">要求</span><span class="sxs-lookup"><span data-stu-id="f5214-110">Requirements</span></span>  
 <span data-ttu-id="f5214-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5214-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5214-112">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="f5214-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5214-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f5214-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5214-114">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5214-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5214-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5214-115">See also</span></span>

- [<span data-ttu-id="f5214-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="f5214-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f5214-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="f5214-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
