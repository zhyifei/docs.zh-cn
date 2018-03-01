---
title: "IMetaDataImport::GetMemberRefProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6cd229d9286dfe9c12a4c6f7e171f8bb634fcc0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="8d102-102">IMetaDataImport::GetMemberRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="8d102-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="8d102-103">获取与指定标记引用的成员关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="8d102-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d102-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d102-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="8d102-105">参数</span><span class="sxs-lookup"><span data-stu-id="8d102-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="8d102-106">[in]要返回关联的元数据的 MemberRef 标记。</span><span class="sxs-lookup"><span data-stu-id="8d102-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="8d102-107">[out]表示声明该成员或表示声明该成员或表示成员 MethodDef module 类的 ModuleRef 标记的类的 TypeDef 或 TypeRef 或 TypeSpec 标记。</span><span class="sxs-lookup"><span data-stu-id="8d102-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="8d102-108">[out]一个成员的名称的字符串缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8d102-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="8d102-109">[in]请求的大小以宽字符为单位`szMember`。</span><span class="sxs-lookup"><span data-stu-id="8d102-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="8d102-110">[out]在宽字符为单位返回的大小`szMember`。</span><span class="sxs-lookup"><span data-stu-id="8d102-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="8d102-111">[out]指向成员的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="8d102-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="8d102-112">[out]以字节为单位的大小`ppvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="8d102-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d102-113">惠?</span><span class="sxs-lookup"><span data-stu-id="8d102-113">Requirements</span></span>  
 <span data-ttu-id="8d102-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d102-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d102-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8d102-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d102-116">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8d102-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8d102-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d102-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d102-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d102-118">See Also</span></span>  
 [<span data-ttu-id="8d102-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="8d102-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="8d102-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="8d102-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
