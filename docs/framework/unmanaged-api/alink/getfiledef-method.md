---
title: GetFileDef 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7cc7b83f7bf1657195778ea38944b2354b09c38
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471337"
---
# <a name="getfiledef-method"></a><span data-ttu-id="f593f-102">GetFileDef 方法</span><span class="sxs-lookup"><span data-stu-id="f593f-102">GetFileDef Method</span></span>
<span data-ttu-id="f593f-103">检索元数据 （而不是由 ALink 分配的令牌） 中使用的实际 FileDef 标记。</span><span class="sxs-lookup"><span data-stu-id="f593f-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f593f-104">语法</span><span class="sxs-lookup"><span data-stu-id="f593f-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f593f-105">参数</span><span class="sxs-lookup"><span data-stu-id="f593f-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f593f-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="f593f-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="f593f-107">添加文件的令牌从 AddFile 方法或 AddImport 方法检索。</span><span class="sxs-lookup"><span data-stu-id="f593f-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="f593f-108">收到 FileDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="f593f-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f593f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f593f-109">Return Value</span></span>  
 <span data-ttu-id="f593f-110">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="f593f-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f593f-111">要求</span><span class="sxs-lookup"><span data-stu-id="f593f-111">Requirements</span></span>  
 <span data-ttu-id="f593f-112">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="f593f-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f593f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f593f-113">See also</span></span>
- [<span data-ttu-id="f593f-114">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="f593f-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f593f-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="f593f-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f593f-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="f593f-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
