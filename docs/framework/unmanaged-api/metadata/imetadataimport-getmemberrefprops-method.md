---
title: IMetaDataImport::GetMemberRefProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: 1d6d66ea62cbf679f722f830b3638455001aedd6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437486"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="8817d-102">IMetaDataImport::GetMemberRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="8817d-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="8817d-103">获取与指定标记引用的成员关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="8817d-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8817d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8817d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,   
   [out] mdToken           *ptk,   
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pbSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8817d-105">参数</span><span class="sxs-lookup"><span data-stu-id="8817d-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="8817d-106">[in] The MemberRef token to return associated metadata for.</span><span class="sxs-lookup"><span data-stu-id="8817d-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="8817d-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span><span class="sxs-lookup"><span data-stu-id="8817d-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="8817d-108">[out] A string buffer for the member's name.</span><span class="sxs-lookup"><span data-stu-id="8817d-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="8817d-109">[in] The requested size in wide characters of `szMember`.</span><span class="sxs-lookup"><span data-stu-id="8817d-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="8817d-110">[out] The returned size in wide characters of `szMember`.</span><span class="sxs-lookup"><span data-stu-id="8817d-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="8817d-111">[out] A pointer to the binary metadata signature for the member.</span><span class="sxs-lookup"><span data-stu-id="8817d-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="8817d-112">[out] The size in bytes of `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="8817d-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8817d-113">要求</span><span class="sxs-lookup"><span data-stu-id="8817d-113">Requirements</span></span>  
 <span data-ttu-id="8817d-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8817d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8817d-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8817d-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8817d-116">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8817d-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8817d-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8817d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8817d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8817d-118">See also</span></span>

- [<span data-ttu-id="8817d-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="8817d-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8817d-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="8817d-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
