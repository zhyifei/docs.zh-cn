---
title: "Init 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.Init
api_location: alink.dll
api_type: COM
f1_keywords: Init
helpviewer_keywords: Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 19e37a4df8055f14a72a4c9093cd594a234ae80d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="init-method"></a><span data-ttu-id="c7e39-102">Init 方法</span><span class="sxs-lookup"><span data-stu-id="c7e39-102">Init Method</span></span>
<span data-ttu-id="c7e39-103">准备对象实现[IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)供使用。</span><span class="sxs-lookup"><span data-stu-id="c7e39-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7e39-104">语法</span><span class="sxs-lookup"><span data-stu-id="c7e39-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7e39-105">参数</span><span class="sxs-lookup"><span data-stu-id="c7e39-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="c7e39-106">[IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)指向元数据分配器。</span><span class="sxs-lookup"><span data-stu-id="c7e39-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="c7e39-107">[IMetaDataError 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)到一个可选错误处理接口的指针。</span><span class="sxs-lookup"><span data-stu-id="c7e39-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7e39-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c7e39-108">Return Value</span></span>  
 <span data-ttu-id="c7e39-109">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="c7e39-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7e39-110">惠?</span><span class="sxs-lookup"><span data-stu-id="c7e39-110">Requirements</span></span>  
 <span data-ttu-id="c7e39-111">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="c7e39-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e39-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7e39-112">See Also</span></span>  
 [<span data-ttu-id="c7e39-113">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="c7e39-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c7e39-114">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="c7e39-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c7e39-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="c7e39-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
