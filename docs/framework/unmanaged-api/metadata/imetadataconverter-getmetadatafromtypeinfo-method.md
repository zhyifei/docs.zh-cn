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
ms.openlocfilehash: f9f3e3f196f74a7dea3c722925f1d03968688882
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008997"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="a9eb0-102">IMetaDataConverter::GetMetaDataFromTypeInfo 方法</span><span class="sxs-lookup"><span data-stu-id="a9eb0-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="a9eb0-103">获取一个指针，该指针指向表示指定实例引用的类型库的元数据签名的[IMetaDataImport](imetadataimport-interface.md)实例 `ITypeInfo` 。</span><span class="sxs-lookup"><span data-stu-id="a9eb0-103">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9eb0-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9eb0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9eb0-105">参数</span><span class="sxs-lookup"><span data-stu-id="a9eb0-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="a9eb0-106">中指向 `ITypeInfo` 引用类型库的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="a9eb0-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="a9eb0-107">弄指向一个位置的指针，该位置接收 `IMetaDataImport` 表示元数据签名的实例的地址。</span><span class="sxs-lookup"><span data-stu-id="a9eb0-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9eb0-108">要求</span><span class="sxs-lookup"><span data-stu-id="a9eb0-108">Requirements</span></span>  
 <span data-ttu-id="a9eb0-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9eb0-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9eb0-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="a9eb0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9eb0-111">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a9eb0-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9eb0-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9eb0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9eb0-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9eb0-113">See also</span></span>

- [<span data-ttu-id="a9eb0-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="a9eb0-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a9eb0-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="a9eb0-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
