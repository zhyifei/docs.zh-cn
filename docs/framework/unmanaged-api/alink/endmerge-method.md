---
title: "EndMerge 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EndMerge
- EndMerge
api_location: alink.dll
api_type: COM
f1_keywords: EndMerge
helpviewer_keywords: EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7f29abf03c636fc552fe550534ca1b1395b43aae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="endmerge-method"></a><span data-ttu-id="c910f-102">EndMerge 方法</span><span class="sxs-lookup"><span data-stu-id="c910f-102">EndMerge Method</span></span>
<span data-ttu-id="c910f-103">指示所有自定义特性有已合并到发出范围。</span><span class="sxs-lookup"><span data-stu-id="c910f-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c910f-104">语法</span><span class="sxs-lookup"><span data-stu-id="c910f-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c910f-105">参数</span><span class="sxs-lookup"><span data-stu-id="c910f-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c910f-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="c910f-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c910f-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c910f-107">Return Value</span></span>  
 <span data-ttu-id="c910f-108">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="c910f-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c910f-109">要求</span><span class="sxs-lookup"><span data-stu-id="c910f-109">Requirements</span></span>  
 <span data-ttu-id="c910f-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="c910f-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c910f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c910f-111">See Also</span></span>  
 [<span data-ttu-id="c910f-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="c910f-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c910f-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="c910f-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c910f-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="c910f-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
