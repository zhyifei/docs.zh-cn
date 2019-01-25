---
title: IMetaDataImport::GetMemberProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98d7be5adc81cff09b121265e7d5b5f712122607
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611405"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="fe863-102">IMetaDataImport::GetMemberProps 方法</span><span class="sxs-lookup"><span data-stu-id="fe863-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="fe863-103">获取元数据信息，包括名称、 二进制签名和相对虚拟地址的<xref:System.Type>指定的元数据标记所引用的成员。</span><span class="sxs-lookup"><span data-stu-id="fe863-103">Gets metadata information, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe863-104">语法</span><span class="sxs-lookup"><span data-stu-id="fe863-104">Syntax</span></span>  
  
```  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] ULONG             *pulCodeRVA,   
   [out] DWORD             *pdwImplFlags,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe863-105">参数</span><span class="sxs-lookup"><span data-stu-id="fe863-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="fe863-106">[in]引用的成员，若要获取有关关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="fe863-106">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="fe863-107">[out]指向表示类的成员的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="fe863-107">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="fe863-108">[out]成员的名称。</span><span class="sxs-lookup"><span data-stu-id="fe863-108">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="fe863-109">[in]在宽字符为单位的大小`szMember`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="fe863-109">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="fe863-110">[out]在宽字符返回的名称的大小。</span><span class="sxs-lookup"><span data-stu-id="fe863-110">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="fe863-111">[out]任何标志应用于的成员的值。</span><span class="sxs-lookup"><span data-stu-id="fe863-111">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="fe863-112">[out]指向成员的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="fe863-112">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="fe863-113">[out]以字节为单位的大小`ppvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="fe863-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="fe863-114">[out]指向成员的相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="fe863-114">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="fe863-115">[out]与成员关联的任何方法实现标志。</span><span class="sxs-lookup"><span data-stu-id="fe863-115">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="fe863-116">[out]一个标志，用于将标记<xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="fe863-116">[out] A flag that marks a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="fe863-117">[out]返回此成员的常量字符串值。</span><span class="sxs-lookup"><span data-stu-id="fe863-117">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="fe863-118">[out]以字符为单位的大小`ppValue`，或为零`ppValue`不保存字符串。</span><span class="sxs-lookup"><span data-stu-id="fe863-118">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe863-119">要求</span><span class="sxs-lookup"><span data-stu-id="fe863-119">Requirements</span></span>  
 <span data-ttu-id="fe863-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe863-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe863-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fe863-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe863-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fe863-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe863-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe863-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe863-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe863-124">See also</span></span>
- [<span data-ttu-id="fe863-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="fe863-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fe863-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="fe863-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
