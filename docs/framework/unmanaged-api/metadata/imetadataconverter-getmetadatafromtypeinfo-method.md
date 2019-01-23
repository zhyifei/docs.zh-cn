---
title: IMetaDataConverter::GetMetaDataFromTypeInfo 方法
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ae7007c4588724da7b3a67f924c981121d2c82bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622216"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="f1c5d-102">IMetaDataConverter::GetMetaDataFromTypeInfo 方法</span><span class="sxs-lookup"><span data-stu-id="f1c5d-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="f1c5d-103">获取一个指向[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)实例，它表示由指定引用的类型库的元数据签名`ITypeInfo`实例。</span><span class="sxs-lookup"><span data-stu-id="f1c5d-103">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1c5d-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1c5d-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1c5d-105">参数</span><span class="sxs-lookup"><span data-stu-id="f1c5d-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="f1c5d-106">[in]一个指向`ITypeInfo`对象，表示类型库。</span><span class="sxs-lookup"><span data-stu-id="f1c5d-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="f1c5d-107">[out]指向接收的地址的位置的指针`IMetaDataImport`实例，它表示元数据签名。</span><span class="sxs-lookup"><span data-stu-id="f1c5d-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1c5d-108">要求</span><span class="sxs-lookup"><span data-stu-id="f1c5d-108">Requirements</span></span>  
 <span data-ttu-id="f1c5d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1c5d-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1c5d-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1c5d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1c5d-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f1c5d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1c5d-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1c5d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c5d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1c5d-113">See also</span></span>
- [<span data-ttu-id="f1c5d-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="f1c5d-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f1c5d-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="f1c5d-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
