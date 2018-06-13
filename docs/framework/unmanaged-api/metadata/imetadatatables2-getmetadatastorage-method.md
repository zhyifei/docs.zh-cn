---
title: IMetaDataTables2::GetMetaDataStorage 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33064fe8292eb7a8079d2f68bcdea767d306be6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452314"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="6e083-102">IMetaDataTables2::GetMetaDataStorage 方法</span><span class="sxs-lookup"><span data-stu-id="6e083-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="6e083-103">获取的大小和存储在指定的节中的元数据的内容。</span><span class="sxs-lookup"><span data-stu-id="6e083-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e083-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e083-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e083-105">参数</span><span class="sxs-lookup"><span data-stu-id="6e083-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="6e083-106">[在中，out]指向元数据部分的指针。</span><span class="sxs-lookup"><span data-stu-id="6e083-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="6e083-107">[out]元数据流的大小。</span><span class="sxs-lookup"><span data-stu-id="6e083-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e083-108">要求</span><span class="sxs-lookup"><span data-stu-id="6e083-108">Requirements</span></span>  
 <span data-ttu-id="6e083-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e083-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e083-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e083-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e083-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6e083-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e083-112">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e083-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e083-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e083-113">See Also</span></span>  
 [<span data-ttu-id="6e083-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="6e083-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 [<span data-ttu-id="6e083-115">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="6e083-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
