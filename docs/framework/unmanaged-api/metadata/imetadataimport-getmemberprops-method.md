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
ms.openlocfilehash: 40631a15bd07b5aa54488e5d3b99cee751e2e0bd
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748331"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="3c671-102">IMetaDataImport::GetMemberProps 方法</span><span class="sxs-lookup"><span data-stu-id="3c671-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="3c671-103">获取有关指定的成员定义，包括名称、 二进制签名和相对虚拟地址的元数据中存储的信息<xref:System.Type>指定的元数据标记所引用的成员。</span><span class="sxs-lookup"><span data-stu-id="3c671-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="3c671-104">这是一个简单的帮助程序方法： 如果*mb*然后是 MethodDef **GetMethodProps**调用; 如果*mb*然后是 FieldDef **GetFieldProps**调用。</span><span class="sxs-lookup"><span data-stu-id="3c671-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="3c671-105">查看这些详细信息的其他方法。</span><span class="sxs-lookup"><span data-stu-id="3c671-105">See these other methods for details.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="3c671-106">语法</span><span class="sxs-lookup"><span data-stu-id="3c671-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="3c671-107">参数</span><span class="sxs-lookup"><span data-stu-id="3c671-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="3c671-108">[in]引用的成员，若要获取有关关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="3c671-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="3c671-109">[out]指向表示类的成员的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="3c671-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="3c671-110">[out]成员的名称。</span><span class="sxs-lookup"><span data-stu-id="3c671-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="3c671-111">[in]在宽字符为单位的大小`szMember`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="3c671-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="3c671-112">[out]在宽字符返回的名称的大小。</span><span class="sxs-lookup"><span data-stu-id="3c671-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="3c671-113">[out]任何标志应用于的成员的值。</span><span class="sxs-lookup"><span data-stu-id="3c671-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="3c671-114">[out]指向成员的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="3c671-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="3c671-115">[out]以字节为单位的大小`ppvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="3c671-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="3c671-116">[out]指向成员的相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3c671-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="3c671-117">[out]与成员关联的任何方法实现标志。</span><span class="sxs-lookup"><span data-stu-id="3c671-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="3c671-118">[out]一个标志，用于将标记<xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="3c671-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="3c671-119">它是之一`ELEMENT_TYPE_*`值。</span><span class="sxs-lookup"><span data-stu-id="3c671-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="3c671-120">[out]返回此成员的常量字符串值。</span><span class="sxs-lookup"><span data-stu-id="3c671-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="3c671-121">[out]以字符为单位的大小`ppValue`，或为零`ppValue`不保存字符串。</span><span class="sxs-lookup"><span data-stu-id="3c671-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c671-122">要求</span><span class="sxs-lookup"><span data-stu-id="3c671-122">Requirements</span></span>  
 <span data-ttu-id="3c671-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c671-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c671-124">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c671-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c671-125">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3c671-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c671-126">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c671-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c671-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c671-127">See also</span></span>
- [<span data-ttu-id="3c671-128">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3c671-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3c671-129">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3c671-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
