---
title: "GetFileDef 方法"
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
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 473cbaba8712ee247733ba3075c0163e259cf4dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getfiledef-method"></a><span data-ttu-id="26928-102">GetFileDef 方法</span><span class="sxs-lookup"><span data-stu-id="26928-102">GetFileDef Method</span></span>
<span data-ttu-id="26928-103">检索元数据 （而不是由 ALink 分配的令牌） 中使用的实际 FileDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="26928-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26928-104">语法</span><span class="sxs-lookup"><span data-stu-id="26928-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26928-105">参数</span><span class="sxs-lookup"><span data-stu-id="26928-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="26928-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="26928-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="26928-107">添加的文件的令牌从 AddFile 方法或 AddImport 方法中检索。</span><span class="sxs-lookup"><span data-stu-id="26928-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="26928-108">收到 FileDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="26928-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26928-109">返回值</span><span class="sxs-lookup"><span data-stu-id="26928-109">Return Value</span></span>  
 <span data-ttu-id="26928-110">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="26928-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26928-111">惠?</span><span class="sxs-lookup"><span data-stu-id="26928-111">Requirements</span></span>  
 <span data-ttu-id="26928-112">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="26928-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26928-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="26928-113">See Also</span></span>  
 [<span data-ttu-id="26928-114">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="26928-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="26928-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="26928-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="26928-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="26928-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
