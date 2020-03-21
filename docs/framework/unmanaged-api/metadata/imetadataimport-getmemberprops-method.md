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
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177234"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="5d3e6-102">IMetaDataImport::GetMemberProps 方法</span><span class="sxs-lookup"><span data-stu-id="5d3e6-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="5d3e6-103">获取存储在指定成员定义的元数据中的信息，包括指定元数据令牌引用<xref:System.Type>的成员的名称、二进制签名和相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="5d3e6-104">这是一个简单的帮助方法：如果*mb*是一个方法Def，则调用**GetMethodProps;** 如果*mb*是 FieldDef，则调用**GetFieldProps。**</span><span class="sxs-lookup"><span data-stu-id="5d3e6-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="5d3e6-105">有关详细信息，请参阅这些其他方法。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-105">See these other methods for details.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5d3e6-106">语法</span><span class="sxs-lookup"><span data-stu-id="5d3e6-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="5d3e6-107">parameters</span><span class="sxs-lookup"><span data-stu-id="5d3e6-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="5d3e6-108">[在]引用成员获取关联的元数据的令牌。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="5d3e6-109">[出]指向表示成员类的元数据令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="5d3e6-110">[出]成员的名称。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="5d3e6-111">[在]`szMember`缓冲区的大小以宽字符表示。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="5d3e6-112">[出]返回名称的宽字符大小。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="5d3e6-113">[出]应用于成员的任何标志值。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="5d3e6-114">[出]指向成员的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="5d3e6-115">[出]的大小（以字节为单位）。 `ppvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="5d3e6-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="5d3e6-116">[出]指向成员的相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="5d3e6-117">[出]与成员关联的任何方法实现标志。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="5d3e6-118">[出]标记 的标志<xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="5d3e6-119">它是`ELEMENT_TYPE_*`值之一。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="5d3e6-120">[出]此成员返回的常量字符串值。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="5d3e6-121">[出]如果`ppValue`不保存字符串，`ppValue`则以 字符或零表示的大小。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d3e6-122">要求</span><span class="sxs-lookup"><span data-stu-id="5d3e6-122">Requirements</span></span>  
 <span data-ttu-id="5d3e6-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d3e6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d3e6-124">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="5d3e6-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d3e6-125">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="5d3e6-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d3e6-126">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d3e6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d3e6-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d3e6-127">See also</span></span>

- [<span data-ttu-id="5d3e6-128">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="5d3e6-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5d3e6-129">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="5d3e6-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
