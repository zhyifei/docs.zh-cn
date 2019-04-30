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
ms.openlocfilehash: cdc1b0de9795a000ee680df880c73acc4f711db2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044364"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="26341-102">IMetaDataConverter::GetMetaDataFromTypeLib 方法</span><span class="sxs-lookup"><span data-stu-id="26341-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="26341-103">获取到的接口指针[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)实例，它表示由指定的类型库的元数据签名`ITypeLib`实例。</span><span class="sxs-lookup"><span data-stu-id="26341-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26341-104">语法</span><span class="sxs-lookup"><span data-stu-id="26341-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26341-105">参数</span><span class="sxs-lookup"><span data-stu-id="26341-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="26341-106">[in]指向`ITypeLib`对象，表示类型库。</span><span class="sxs-lookup"><span data-stu-id="26341-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="26341-107">[out]位置收到的地址指针`IMetaDataImport`实例，它表示元数据签名。</span><span class="sxs-lookup"><span data-stu-id="26341-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26341-108">要求</span><span class="sxs-lookup"><span data-stu-id="26341-108">Requirements</span></span>  
 <span data-ttu-id="26341-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="26341-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26341-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="26341-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26341-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="26341-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="26341-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26341-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26341-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="26341-113">See also</span></span>

- [<span data-ttu-id="26341-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="26341-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="26341-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="26341-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
