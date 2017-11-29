---
title: "GetFileDef 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetFileDef
api_location: alink.dll
api_type: COM
f1_keywords: GetFileDef
helpviewer_keywords: GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a31dee6bb1af4f555211822a3b7ec108353214a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="getfiledef-method"></a><span data-ttu-id="df656-102">GetFileDef 方法</span><span class="sxs-lookup"><span data-stu-id="df656-102">GetFileDef Method</span></span>
<span data-ttu-id="df656-103">检索元数据 （而不是由 ALink 分配的令牌） 中使用的实际 FileDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="df656-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df656-104">语法</span><span class="sxs-lookup"><span data-stu-id="df656-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df656-105">参数</span><span class="sxs-lookup"><span data-stu-id="df656-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="df656-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="df656-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="df656-107">添加的文件的令牌从 AddFile 方法或 AddImport 方法中检索。</span><span class="sxs-lookup"><span data-stu-id="df656-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="df656-108">收到 FileDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="df656-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df656-109">返回值</span><span class="sxs-lookup"><span data-stu-id="df656-109">Return Value</span></span>  
 <span data-ttu-id="df656-110">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="df656-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df656-111">要求</span><span class="sxs-lookup"><span data-stu-id="df656-111">Requirements</span></span>  
 <span data-ttu-id="df656-112">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="df656-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df656-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df656-113">See Also</span></span>  
 [<span data-ttu-id="df656-114">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="df656-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="df656-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="df656-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="df656-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="df656-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
