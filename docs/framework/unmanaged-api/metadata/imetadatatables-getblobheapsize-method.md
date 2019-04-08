---
title: IMetaDataTables::GetBlobHeapSize 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d22e61d28e0fbf06fa1cfe9e9ac18a534726f01d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076450"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="99dae-102">IMetaDataTables::GetBlobHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="99dae-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="99dae-103">获取以字节为单位的二进制大型对象 (BLOB) 堆的大小。</span><span class="sxs-lookup"><span data-stu-id="99dae-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99dae-104">语法</span><span class="sxs-lookup"><span data-stu-id="99dae-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="99dae-105">参数</span><span class="sxs-lookup"><span data-stu-id="99dae-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="99dae-106">[out]指向大小 （字节） 对在 BLOB 堆的指针。</span><span class="sxs-lookup"><span data-stu-id="99dae-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99dae-107">要求</span><span class="sxs-lookup"><span data-stu-id="99dae-107">Requirements</span></span>  
 <span data-ttu-id="99dae-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="99dae-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99dae-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="99dae-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99dae-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="99dae-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="99dae-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="99dae-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99dae-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="99dae-112">See also</span></span>

- [<span data-ttu-id="99dae-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="99dae-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="99dae-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="99dae-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
