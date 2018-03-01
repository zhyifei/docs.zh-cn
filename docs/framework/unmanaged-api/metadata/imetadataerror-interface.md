---
title: "IMetaDataError 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4df7aa7400a180151de5420effc8738955d51c26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="eb333-102">IMetaDataError 接口</span><span class="sxs-lookup"><span data-stu-id="eb333-102">IMetaDataError Interface</span></span>
<span data-ttu-id="eb333-103">提供用于元数据合并期间报告错误的回调机制。</span><span class="sxs-lookup"><span data-stu-id="eb333-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb333-104">`IMetaDataError`由客户端必须实现接口。</span><span class="sxs-lookup"><span data-stu-id="eb333-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb333-105">方法</span><span class="sxs-lookup"><span data-stu-id="eb333-105">Methods</span></span>  
  
|<span data-ttu-id="eb333-106">方法</span><span class="sxs-lookup"><span data-stu-id="eb333-106">Method</span></span>|<span data-ttu-id="eb333-107">描述</span><span class="sxs-lookup"><span data-stu-id="eb333-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb333-108">OnError 方法</span><span class="sxs-lookup"><span data-stu-id="eb333-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="eb333-109">提供在元数据合并过程中发生的错误的通知。</span><span class="sxs-lookup"><span data-stu-id="eb333-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb333-110">惠?</span><span class="sxs-lookup"><span data-stu-id="eb333-110">Requirements</span></span>  
 <span data-ttu-id="eb333-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb333-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb333-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eb333-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb333-113">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eb333-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb333-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb333-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb333-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb333-115">See Also</span></span>  
 [<span data-ttu-id="eb333-116">元数据接口</span><span class="sxs-lookup"><span data-stu-id="eb333-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
