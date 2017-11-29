---
title: "IMetaDataEmit::SetFieldRVA 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetFieldRVA
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 463f40b933924108378f6cf9c6109e54b01ce293
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="9d4d9-102">IMetaDataEmit::SetFieldRVA 方法</span><span class="sxs-lookup"><span data-stu-id="9d4d9-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="9d4d9-103">设置指定标记所引用的字段的相对虚拟地址的全局变量值。</span><span class="sxs-lookup"><span data-stu-id="9d4d9-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d4d9-104">语法</span><span class="sxs-lookup"><span data-stu-id="9d4d9-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d4d9-105">参数</span><span class="sxs-lookup"><span data-stu-id="9d4d9-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="9d4d9-106">[in]目标字段的标记。</span><span class="sxs-lookup"><span data-stu-id="9d4d9-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="9d4d9-107">[in]代码或数据区域的地址。</span><span class="sxs-lookup"><span data-stu-id="9d4d9-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d4d9-108">要求</span><span class="sxs-lookup"><span data-stu-id="9d4d9-108">Requirements</span></span>  
 <span data-ttu-id="9d4d9-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d4d9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d4d9-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d4d9-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d4d9-111">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9d4d9-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d4d9-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d4d9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d4d9-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d4d9-113">See Also</span></span>  
 [<span data-ttu-id="9d4d9-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="9d4d9-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9d4d9-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="9d4d9-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
