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
ms.openlocfilehash: 462512fd2c2b33905b45bb67599b23b301fc71f7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437993"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="ed05f-102">IMetaDataImport::GetFieldProps 方法</span><span class="sxs-lookup"><span data-stu-id="ed05f-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="ed05f-103">获取与指定 FieldDef 标记引用的字段关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="ed05f-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed05f-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed05f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ed05f-105">参数</span><span class="sxs-lookup"><span data-stu-id="ed05f-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="ed05f-106">中一个 FieldDef 标记，它表示要为其获取关联元数据的字段。</span><span class="sxs-lookup"><span data-stu-id="ed05f-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="ed05f-107">弄一个指针，指向表示字段所属类的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="ed05f-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="ed05f-108">弄字段的名称。</span><span class="sxs-lookup"><span data-stu-id="ed05f-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="ed05f-109">中*SzField*缓冲区的大小（以宽字符为大小）。</span><span class="sxs-lookup"><span data-stu-id="ed05f-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="ed05f-110">弄返回的缓冲区的实际大小。</span><span class="sxs-lookup"><span data-stu-id="ed05f-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="ed05f-111">弄与字段的元数据关联的标志。</span><span class="sxs-lookup"><span data-stu-id="ed05f-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="ed05f-112">中指向描述字段的二进制元数据值的指针。</span><span class="sxs-lookup"><span data-stu-id="ed05f-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="ed05f-113">弄`ppvSigBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ed05f-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="ed05f-114">弄指定字段的值类型的标志。</span><span class="sxs-lookup"><span data-stu-id="ed05f-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ed05f-115">弄字段的常数值。</span><span class="sxs-lookup"><span data-stu-id="ed05f-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="ed05f-116">弄`ppValue`的大小，如果不存在任何字符串，则为零。</span><span class="sxs-lookup"><span data-stu-id="ed05f-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed05f-117">要求</span><span class="sxs-lookup"><span data-stu-id="ed05f-117">Requirements</span></span>  
 <span data-ttu-id="ed05f-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed05f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed05f-119">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ed05f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed05f-120">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ed05f-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed05f-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed05f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed05f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed05f-122">See also</span></span>

- [<span data-ttu-id="ed05f-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="ed05f-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ed05f-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="ed05f-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
