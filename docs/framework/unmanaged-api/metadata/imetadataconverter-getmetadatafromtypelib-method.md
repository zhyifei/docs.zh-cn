---
title: "IMetaDataConverter::GetMetaDataFromTypeLib 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter.GetMetaDataFromTypeLib
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f2438c2d5402f6cff695ecc9832329ff826ded01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="9d8ed-102">IMetaDataConverter::GetMetaDataFromTypeLib 方法</span><span class="sxs-lookup"><span data-stu-id="9d8ed-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="9d8ed-103">获取到的接口指针[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)实例，它表示由指定的类型库的元数据签名`ITypeLib`实例。</span><span class="sxs-lookup"><span data-stu-id="9d8ed-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d8ed-104">语法</span><span class="sxs-lookup"><span data-stu-id="9d8ed-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d8ed-105">参数</span><span class="sxs-lookup"><span data-stu-id="9d8ed-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="9d8ed-106">[in]指向`ITypeLib`表示的类型库的对象。</span><span class="sxs-lookup"><span data-stu-id="9d8ed-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="9d8ed-107">[out]接收的地址的位置指针`IMetaDataImport`表示的元数据签名的实例。</span><span class="sxs-lookup"><span data-stu-id="9d8ed-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d8ed-108">要求</span><span class="sxs-lookup"><span data-stu-id="9d8ed-108">Requirements</span></span>  
 <span data-ttu-id="9d8ed-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d8ed-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d8ed-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d8ed-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d8ed-111">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9d8ed-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d8ed-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d8ed-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d8ed-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d8ed-113">See Also</span></span>  
 [<span data-ttu-id="9d8ed-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="9d8ed-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9d8ed-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="9d8ed-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
