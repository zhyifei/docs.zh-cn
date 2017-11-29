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
ms.openlocfilehash: 999f572d27f75094ecc72c59acee7d35f86d5342
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="init-method"></a><span data-ttu-id="732fa-102">Init 方法</span><span class="sxs-lookup"><span data-stu-id="732fa-102">Init Method</span></span>
<span data-ttu-id="732fa-103">准备对象实现[IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)供使用。</span><span class="sxs-lookup"><span data-stu-id="732fa-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="732fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="732fa-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="732fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="732fa-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="732fa-106">[IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)指向元数据分配器。</span><span class="sxs-lookup"><span data-stu-id="732fa-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="732fa-107">[IMetaDataError 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)到一个可选错误处理接口的指针。</span><span class="sxs-lookup"><span data-stu-id="732fa-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="732fa-108">返回值</span><span class="sxs-lookup"><span data-stu-id="732fa-108">Return Value</span></span>  
 <span data-ttu-id="732fa-109">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="732fa-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="732fa-110">要求</span><span class="sxs-lookup"><span data-stu-id="732fa-110">Requirements</span></span>  
 <span data-ttu-id="732fa-111">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="732fa-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="732fa-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="732fa-112">See Also</span></span>  
 [<span data-ttu-id="732fa-113">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="732fa-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="732fa-114">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="732fa-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="732fa-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="732fa-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
