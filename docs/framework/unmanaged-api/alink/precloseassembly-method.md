---
title: "PreCloseAssembly 方法"
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
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a4d1f2eed036552ab17b6768b7b2d84f4a52c9c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="precloseassembly-method"></a><span data-ttu-id="92a57-102">PreCloseAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="92a57-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="92a57-103">关闭该程序集文件。</span><span class="sxs-lookup"><span data-stu-id="92a57-103">Closes the assembly file.</span></span> <span data-ttu-id="92a57-104">在关闭所有其他文件之后, 但在关闭的程序集文件之前，请调用此方法。</span><span class="sxs-lookup"><span data-stu-id="92a57-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="92a57-105">请勿对未绑定模块中调用此方法。</span><span class="sxs-lookup"><span data-stu-id="92a57-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92a57-106">语法</span><span class="sxs-lookup"><span data-stu-id="92a57-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92a57-107">参数</span><span class="sxs-lookup"><span data-stu-id="92a57-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="92a57-108">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="92a57-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92a57-109">返回值</span><span class="sxs-lookup"><span data-stu-id="92a57-109">Return Value</span></span>  
 <span data-ttu-id="92a57-110">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="92a57-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92a57-111">惠?</span><span class="sxs-lookup"><span data-stu-id="92a57-111">Requirements</span></span>  
 <span data-ttu-id="92a57-112">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="92a57-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92a57-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="92a57-113">See Also</span></span>  
 [<span data-ttu-id="92a57-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="92a57-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="92a57-115">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="92a57-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="92a57-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="92a57-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
