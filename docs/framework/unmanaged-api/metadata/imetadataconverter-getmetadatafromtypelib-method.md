---
title: IMetaDataConverter::GetMetaDataFromTypeLib 方法
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdd2aeb54e9d3c78c58b1a8b497839e876038dfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443634"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="ed602-102">IMetaDataConverter::GetMetaDataFromTypeLib 方法</span><span class="sxs-lookup"><span data-stu-id="ed602-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="ed602-103">获取到的接口指针[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)实例，它表示由指定的类型库的元数据签名`ITypeLib`实例。</span><span class="sxs-lookup"><span data-stu-id="ed602-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed602-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed602-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed602-105">参数</span><span class="sxs-lookup"><span data-stu-id="ed602-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="ed602-106">[in]指向`ITypeLib`表示的类型库的对象。</span><span class="sxs-lookup"><span data-stu-id="ed602-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="ed602-107">[out]接收的地址的位置指针`IMetaDataImport`表示的元数据签名的实例。</span><span class="sxs-lookup"><span data-stu-id="ed602-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed602-108">要求</span><span class="sxs-lookup"><span data-stu-id="ed602-108">Requirements</span></span>  
 <span data-ttu-id="ed602-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed602-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed602-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ed602-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed602-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ed602-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed602-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed602-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed602-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed602-113">See Also</span></span>  
 [<span data-ttu-id="ed602-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="ed602-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="ed602-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="ed602-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
