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
ms.openlocfilehash: 09a1605deda5b51be604c3b8f0c69fa5adcf9dc0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175949"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="8d03d-102">IMetaDataConverter::GetMetaDataFromTypeLib 方法</span><span class="sxs-lookup"><span data-stu-id="8d03d-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="8d03d-103">获取指向[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)实例的接口指针，该实例表示指定`ITypeLib`实例表示的类型库的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="8d03d-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d03d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d03d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d03d-105">parameters</span><span class="sxs-lookup"><span data-stu-id="8d03d-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="8d03d-106">[在]指向表示类型`ITypeLib`库的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="8d03d-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="8d03d-107">[出]指向接收表示元数据签名的`IMetaDataImport`实例地址的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="8d03d-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d03d-108">要求</span><span class="sxs-lookup"><span data-stu-id="8d03d-108">Requirements</span></span>  
 <span data-ttu-id="8d03d-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d03d-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d03d-110">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="8d03d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d03d-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8d03d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8d03d-112">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d03d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d03d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d03d-113">See also</span></span>

- [<span data-ttu-id="8d03d-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="8d03d-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8d03d-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="8d03d-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
