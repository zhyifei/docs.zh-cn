---
title: "GetResolutionScope 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetResolutionScope
api_location: alink.dll
api_type: COM
f1_keywords: GetResolutionScope
helpviewer_keywords: GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 11ccbce4d8e9783514050f6b41c6e32cde6c274f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="6a18c-102">GetResolutionScope 方法</span><span class="sxs-lookup"><span data-stu-id="6a18c-102">GetResolutionScope Method</span></span>
<span data-ttu-id="6a18c-103">检索给定类型的作用域。</span><span class="sxs-lookup"><span data-stu-id="6a18c-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a18c-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a18c-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a18c-105">参数</span><span class="sxs-lookup"><span data-stu-id="6a18c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6a18c-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="6a18c-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="6a18c-107">需要一个引用的文件。</span><span class="sxs-lookup"><span data-stu-id="6a18c-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="6a18c-108">令牌文件的该类型定义在中，通常使用检索[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="6a18c-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="6a18c-109">接收的程序集或模块引用。</span><span class="sxs-lookup"><span data-stu-id="6a18c-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a18c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="6a18c-110">Return Value</span></span>  
 <span data-ttu-id="6a18c-111">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="6a18c-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a18c-112">要求</span><span class="sxs-lookup"><span data-stu-id="6a18c-112">Requirements</span></span>  
 <span data-ttu-id="6a18c-113">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="6a18c-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a18c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a18c-114">See Also</span></span>  
 [<span data-ttu-id="6a18c-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="6a18c-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="6a18c-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="6a18c-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="6a18c-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="6a18c-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
