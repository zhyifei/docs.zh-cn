---
title: IMetaDataImport::GetFieldProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
ms.openlocfilehash: 8c3f98a124dbbcae3b0500932a2357ed1757951f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177237"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="6bfb4-102">IMetaDataImport::GetFieldProps 方法</span><span class="sxs-lookup"><span data-stu-id="6bfb4-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="6bfb4-103">获取与指定 FieldDef 标记引用的字段关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bfb4-104">语法</span><span class="sxs-lookup"><span data-stu-id="6bfb4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bfb4-105">parameters</span><span class="sxs-lookup"><span data-stu-id="6bfb4-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="6bfb4-106">[在]表示要为其获取关联的元数据的字段的 FieldDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="6bfb4-107">[出]指向 TypeDef 令牌的指针，表示字段所属的类的类型。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="6bfb4-108">[出]字段的名称。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="6bfb4-109">[在]*szField*缓冲区的大小以宽字符表示。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="6bfb4-110">[出]返回的缓冲区的实际大小。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="6bfb4-111">[出]与字段的元数据关联的标志。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="6bfb4-112">[在]指向描述字段的二进制元数据值的指针。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="6bfb4-113">[出]的大小（以字节为单位）。 `ppvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="6bfb4-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="6bfb4-114">[出]指定字段的值类型的标志。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="6bfb4-115">[出]字段的常量值。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="6bfb4-116">[出]如果不存在字符串，则大小`ppValue`以 的 字符表示或零。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bfb4-117">要求</span><span class="sxs-lookup"><span data-stu-id="6bfb4-117">Requirements</span></span>  
 <span data-ttu-id="6bfb4-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6bfb4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bfb4-119">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="6bfb4-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6bfb4-120">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="6bfb4-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6bfb4-121">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bfb4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bfb4-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6bfb4-122">See also</span></span>

- [<span data-ttu-id="6bfb4-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="6bfb4-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6bfb4-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="6bfb4-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
