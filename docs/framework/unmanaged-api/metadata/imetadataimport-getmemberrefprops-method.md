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
ms.openlocfilehash: a61254ba751e47b0089a3f7528aca337a32e2db3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175364"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="b6b16-102">IMetaDataImport::GetMemberRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="b6b16-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="b6b16-103">获取与指定标记引用的成员关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="b6b16-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6b16-104">语法</span><span class="sxs-lookup"><span data-stu-id="b6b16-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b6b16-105">parameters</span><span class="sxs-lookup"><span data-stu-id="b6b16-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="b6b16-106">[在]要为其返回关联的元数据的会员Ref 令牌。</span><span class="sxs-lookup"><span data-stu-id="b6b16-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="b6b16-107">[出]表示成员声明的类的 TypeDef 或 TypeRef 或 TypeSpec 令牌，或表示声明成员的模块类的 ModuleRef 令牌，或表示成员的 MethodDef。</span><span class="sxs-lookup"><span data-stu-id="b6b16-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="b6b16-108">[出]成员名称的字符串缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b6b16-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="b6b16-109">[在]请求的大小以宽字符表示`szMember`。</span><span class="sxs-lookup"><span data-stu-id="b6b16-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="b6b16-110">[出]返回的大小以宽字符。 `szMember`</span><span class="sxs-lookup"><span data-stu-id="b6b16-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="b6b16-111">[出]指向成员的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="b6b16-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="b6b16-112">[出]的大小（以字节为单位）。 `ppvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="b6b16-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6b16-113">要求</span><span class="sxs-lookup"><span data-stu-id="b6b16-113">Requirements</span></span>  
 <span data-ttu-id="b6b16-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b6b16-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6b16-115">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="b6b16-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6b16-116">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="b6b16-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6b16-117">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6b16-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b16-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6b16-118">See also</span></span>

- [<span data-ttu-id="b6b16-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="b6b16-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b6b16-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="b6b16-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
