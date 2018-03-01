---
title: "CloseEnum 方法"
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
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 89f5b7069af0bfdfd732ed1ab4935771a565a20f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="closeenum-method"></a><span data-ttu-id="0c968-102">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="0c968-102">CloseEnum Method</span></span>
<span data-ttu-id="0c968-103">关闭指定的枚举并释放关联的资源。</span><span class="sxs-lookup"><span data-stu-id="0c968-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c968-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c968-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c968-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c968-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="0c968-106">枚举即将关闭句柄。</span><span class="sxs-lookup"><span data-stu-id="0c968-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c968-107">返回值</span><span class="sxs-lookup"><span data-stu-id="0c968-107">Return Value</span></span>  
 <span data-ttu-id="0c968-108">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="0c968-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c968-109">惠?</span><span class="sxs-lookup"><span data-stu-id="0c968-109">Requirements</span></span>  
 <span data-ttu-id="0c968-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="0c968-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c968-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c968-111">See Also</span></span>  
 [<span data-ttu-id="0c968-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="0c968-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="0c968-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="0c968-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="0c968-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="0c968-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
