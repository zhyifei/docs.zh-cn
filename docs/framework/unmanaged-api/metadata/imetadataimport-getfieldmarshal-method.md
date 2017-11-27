---
title: "IMetaDataImport::GetFieldMarshal 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetFieldMarshal
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce29990bf9e6b5b670a9a277442adac4ceef2947
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="24913-102">IMetaDataImport::GetFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="24913-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="24913-103">获取一个指向指定的字段的元数据标记所表示的字段的本机非托管类型。</span><span class="sxs-lookup"><span data-stu-id="24913-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24913-104">语法</span><span class="sxs-lookup"><span data-stu-id="24913-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24913-105">参数</span><span class="sxs-lookup"><span data-stu-id="24913-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="24913-106">[in]表示要获取有关互操作封送处理信息的字段元数据标记。</span><span class="sxs-lookup"><span data-stu-id="24913-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="24913-107">[out]指向字段的本机类型的元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="24913-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="24913-108">[out]以字节为单位的大小`ppvNativeType`。</span><span class="sxs-lookup"><span data-stu-id="24913-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24913-109">要求</span><span class="sxs-lookup"><span data-stu-id="24913-109">Requirements</span></span>  
 <span data-ttu-id="24913-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24913-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24913-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="24913-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24913-112">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="24913-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24913-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24913-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24913-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24913-114">See Also</span></span>  
 [<span data-ttu-id="24913-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="24913-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="24913-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="24913-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
