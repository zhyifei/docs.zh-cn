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
ms.openlocfilehash: bc5bbba2fa4a95955e52a2e083a2097178b5d96a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437515"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="5e19d-102">IMetaDataImport::GetMemberProps 方法</span><span class="sxs-lookup"><span data-stu-id="5e19d-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="5e19d-103">获取存储在指定的成员定义的元数据中的信息，这些信息包括指定的元数据标记所引用的 <xref:System.Type> 成员的名称、二进制签名和相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="5e19d-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="5e19d-104">这是一个简单的帮助器方法：如果*mb*是 MethodDef，则调用**GetMethodProps** ;如果*mb*是 FieldDef，则调用**GetFieldProps** 。</span><span class="sxs-lookup"><span data-stu-id="5e19d-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="5e19d-105">有关详细信息，请参阅其他方法。</span><span class="sxs-lookup"><span data-stu-id="5e19d-105">See these other methods for details.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="5e19d-106">语法</span><span class="sxs-lookup"><span data-stu-id="5e19d-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5e19d-107">参数</span><span class="sxs-lookup"><span data-stu-id="5e19d-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="5e19d-108">中引用要为其获取关联元数据的成员的标记。</span><span class="sxs-lookup"><span data-stu-id="5e19d-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="5e19d-109">弄指向表示成员的类的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="5e19d-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="5e19d-110">弄成员的名称。</span><span class="sxs-lookup"><span data-stu-id="5e19d-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="5e19d-111">中`szMember` 缓冲区的大小（以宽字符为大小）。</span><span class="sxs-lookup"><span data-stu-id="5e19d-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="5e19d-112">弄返回名称的大小（以宽字符为大小）。</span><span class="sxs-lookup"><span data-stu-id="5e19d-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="5e19d-113">弄应用于成员的任何标志值。</span><span class="sxs-lookup"><span data-stu-id="5e19d-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="5e19d-114">弄指向成员的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="5e19d-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="5e19d-115">弄`ppvSigBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5e19d-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="5e19d-116">弄指向成员的相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="5e19d-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="5e19d-117">弄与成员关联的任何方法实现标志。</span><span class="sxs-lookup"><span data-stu-id="5e19d-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="5e19d-118">弄标记 <xref:System.ValueType>的标志。</span><span class="sxs-lookup"><span data-stu-id="5e19d-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="5e19d-119">这是 `ELEMENT_TYPE_*` 值之一。</span><span class="sxs-lookup"><span data-stu-id="5e19d-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="5e19d-120">弄此成员返回的常量字符串值。</span><span class="sxs-lookup"><span data-stu-id="5e19d-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="5e19d-121">弄`ppValue`的大小（以字符为大小）; 如果 `ppValue` 不包含字符串，则为零。</span><span class="sxs-lookup"><span data-stu-id="5e19d-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e19d-122">要求</span><span class="sxs-lookup"><span data-stu-id="5e19d-122">Requirements</span></span>  
 <span data-ttu-id="5e19d-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5e19d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e19d-124">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="5e19d-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5e19d-125">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="5e19d-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5e19d-126">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e19d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e19d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e19d-127">See also</span></span>

- [<span data-ttu-id="5e19d-128">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="5e19d-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5e19d-129">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="5e19d-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
