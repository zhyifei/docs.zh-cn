---
title: IMetaDataImport::GetMethodSemantics 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f4908f5d03687fb415c91325941aaab148832dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447731"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="cd08e-102">IMetaDataImport::GetMethodSemantics 方法</span><span class="sxs-lookup"><span data-stu-id="cd08e-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="cd08e-103">获取令牌的标志，指示由指定的 MethodDef 标记和与成对的属性引用的方法和事件由指定的 EventProp 引用之间的关系。</span><span class="sxs-lookup"><span data-stu-id="cd08e-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd08e-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd08e-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd08e-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd08e-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="cd08e-106">[in]表示要获取的语义角色信息的方法的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="cd08e-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="cd08e-107">[in]表示成对的属性和要为其获取方法的角色的事件的标记。</span><span class="sxs-lookup"><span data-stu-id="cd08e-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="cd08e-108">[out]指向关联的语义标记的指针。</span><span class="sxs-lookup"><span data-stu-id="cd08e-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="cd08e-109">此值是从一个位掩码[CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="cd08e-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd08e-110">备注</span><span class="sxs-lookup"><span data-stu-id="cd08e-110">Remarks</span></span>  
 <span data-ttu-id="cd08e-111">[Imetadataemit:: Defineproperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)方法设置方法的语义标志。</span><span class="sxs-lookup"><span data-stu-id="cd08e-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd08e-112">要求</span><span class="sxs-lookup"><span data-stu-id="cd08e-112">Requirements</span></span>  
 <span data-ttu-id="cd08e-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd08e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd08e-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cd08e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd08e-115">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cd08e-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cd08e-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd08e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd08e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd08e-117">See Also</span></span>  
 [<span data-ttu-id="cd08e-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="cd08e-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="cd08e-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="cd08e-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
