---
title: "CloseEnum 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CloseEnum
- IALink.CloseEnum
api_location: alink.dll
api_type: COM
f1_keywords: CloseEnum
helpviewer_keywords: CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6ade939969069fb35221d83f8c7e4e380e903a00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="closeenum-method"></a><span data-ttu-id="8017d-102">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="8017d-102">CloseEnum Method</span></span>
<span data-ttu-id="8017d-103">关闭指定的枚举并释放关联的资源。</span><span class="sxs-lookup"><span data-stu-id="8017d-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8017d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8017d-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8017d-105">参数</span><span class="sxs-lookup"><span data-stu-id="8017d-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="8017d-106">枚举即将关闭句柄。</span><span class="sxs-lookup"><span data-stu-id="8017d-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8017d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="8017d-107">Return Value</span></span>  
 <span data-ttu-id="8017d-108">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="8017d-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8017d-109">要求</span><span class="sxs-lookup"><span data-stu-id="8017d-109">Requirements</span></span>  
 <span data-ttu-id="8017d-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="8017d-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8017d-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8017d-111">See Also</span></span>  
 [<span data-ttu-id="8017d-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="8017d-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="8017d-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="8017d-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="8017d-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="8017d-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
