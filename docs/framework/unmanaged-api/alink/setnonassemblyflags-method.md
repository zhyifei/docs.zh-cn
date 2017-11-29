---
title: "SetNonAssemblyFlags 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetNonAssemblyFlags
api_location: alink.dll
api_type: COM
f1_keywords: SetNonAssemblyFlags
helpviewer_keywords: SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5f8761259e89b4befd0eeaf893ffbe5d4142350
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="650e8-102">SetNonAssemblyFlags 方法</span><span class="sxs-lookup"><span data-stu-id="650e8-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="650e8-103">设置不是程序集特定的标志。</span><span class="sxs-lookup"><span data-stu-id="650e8-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="650e8-104">语法</span><span class="sxs-lookup"><span data-stu-id="650e8-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="650e8-105">参数</span><span class="sxs-lookup"><span data-stu-id="650e8-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="650e8-106">ALink 标志。</span><span class="sxs-lookup"><span data-stu-id="650e8-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="650e8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="650e8-107">Return Value</span></span>  
 <span data-ttu-id="650e8-108">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="650e8-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="650e8-109">要求</span><span class="sxs-lookup"><span data-stu-id="650e8-109">Requirements</span></span>  
 <span data-ttu-id="650e8-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="650e8-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="650e8-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="650e8-111">See Also</span></span>  
 [<span data-ttu-id="650e8-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="650e8-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="650e8-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="650e8-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="650e8-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="650e8-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
