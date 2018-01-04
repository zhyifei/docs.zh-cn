---
title: "IMetaDataTables::GetNumTables 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNumTables
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d65b17899f0a6856daf3d99fe8b8025d5d4c462
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="963dc-102">IMetaDataTables::GetNumTables 方法</span><span class="sxs-lookup"><span data-stu-id="963dc-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="963dc-103">获取当前的作用域中的表数`IMetaDataTables`实例。</span><span class="sxs-lookup"><span data-stu-id="963dc-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="963dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="963dc-104">Syntax</span></span>  
  
```  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="963dc-105">参数</span><span class="sxs-lookup"><span data-stu-id="963dc-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="963dc-106">[out]指向当前实例作用域中的表数的指针。</span><span class="sxs-lookup"><span data-stu-id="963dc-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="963dc-107">惠?</span><span class="sxs-lookup"><span data-stu-id="963dc-107">Requirements</span></span>  
 <span data-ttu-id="963dc-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="963dc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="963dc-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="963dc-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="963dc-110">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="963dc-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="963dc-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="963dc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="963dc-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="963dc-112">See Also</span></span>  
 [<span data-ttu-id="963dc-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="963dc-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="963dc-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="963dc-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
