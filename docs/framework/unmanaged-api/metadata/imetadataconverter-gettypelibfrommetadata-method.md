---
title: IMetaDataConverter::GetTypeLibFromMetaData 方法
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: 79bd8901641ee587e94861c0aec85b812591ea48
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008412"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="143e0-102">IMetaDataConverter::GetTypeLibFromMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="143e0-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="143e0-103">获取一个指针，该指针指向 `ITypeLib` 表示具有指定库和模块名称的类型库的实例。</span><span class="sxs-lookup"><span data-stu-id="143e0-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="143e0-104">语法</span><span class="sxs-lookup"><span data-stu-id="143e0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="143e0-105">参数</span><span class="sxs-lookup"><span data-stu-id="143e0-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="143e0-106">中类型库的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="143e0-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="143e0-107">中类型库的名称。</span><span class="sxs-lookup"><span data-stu-id="143e0-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="143e0-108">弄指向一个位置的指针，该位置接收 `ITypeLib` 表示类型库的实例的地址。</span><span class="sxs-lookup"><span data-stu-id="143e0-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="143e0-109">要求</span><span class="sxs-lookup"><span data-stu-id="143e0-109">Requirements</span></span>  
 <span data-ttu-id="143e0-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="143e0-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="143e0-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="143e0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="143e0-112">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="143e0-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="143e0-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="143e0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="143e0-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="143e0-114">See also</span></span>

- [<span data-ttu-id="143e0-115">IMetaDataConverter 接口</span><span class="sxs-lookup"><span data-stu-id="143e0-115">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)
