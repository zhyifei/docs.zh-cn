---
title: GetResolutionScope 方法
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c6d298c84b801b87832c56026b05f647cb5a9dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789826"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="d4709-102">GetResolutionScope 方法</span><span class="sxs-lookup"><span data-stu-id="d4709-102">GetResolutionScope Method</span></span>
<span data-ttu-id="d4709-103">检索给定类型的作用域。</span><span class="sxs-lookup"><span data-stu-id="d4709-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4709-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4709-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4709-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4709-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d4709-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="d4709-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d4709-107">需要一个引用的文件。</span><span class="sxs-lookup"><span data-stu-id="d4709-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="d4709-108">标记文件的该类型定义中，通常使用检索[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d4709-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="d4709-109">接收的程序集或模块引用。</span><span class="sxs-lookup"><span data-stu-id="d4709-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4709-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d4709-110">Return Value</span></span>  
 <span data-ttu-id="d4709-111">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d4709-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4709-112">要求</span><span class="sxs-lookup"><span data-stu-id="d4709-112">Requirements</span></span>  
 <span data-ttu-id="d4709-113">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="d4709-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4709-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4709-114">See also</span></span>

- [<span data-ttu-id="d4709-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="d4709-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d4709-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="d4709-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d4709-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="d4709-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
