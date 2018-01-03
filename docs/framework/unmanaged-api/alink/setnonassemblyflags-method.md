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
ms.workload: dotnet
ms.openlocfilehash: 7e944f285ee0925b76fdd9b95c824deee38cead2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="f07aa-102">SetNonAssemblyFlags 方法</span><span class="sxs-lookup"><span data-stu-id="f07aa-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="f07aa-103">设置不是程序集特定的标志。</span><span class="sxs-lookup"><span data-stu-id="f07aa-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f07aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="f07aa-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f07aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="f07aa-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="f07aa-106">ALink 标志。</span><span class="sxs-lookup"><span data-stu-id="f07aa-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f07aa-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f07aa-107">Return Value</span></span>  
 <span data-ttu-id="f07aa-108">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="f07aa-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f07aa-109">惠?</span><span class="sxs-lookup"><span data-stu-id="f07aa-109">Requirements</span></span>  
 <span data-ttu-id="f07aa-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="f07aa-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f07aa-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f07aa-111">See Also</span></span>  
 [<span data-ttu-id="f07aa-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="f07aa-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f07aa-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="f07aa-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f07aa-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="f07aa-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
