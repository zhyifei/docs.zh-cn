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
ms.openlocfilehash: a2bfb43002b79fd3e499272b87756bdc3ab0b589
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787337"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="6412d-102">GetResolutionScope 方法</span><span class="sxs-lookup"><span data-stu-id="6412d-102">GetResolutionScope Method</span></span>
<span data-ttu-id="6412d-103">检索给定类型的作用域。</span><span class="sxs-lookup"><span data-stu-id="6412d-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6412d-104">语法</span><span class="sxs-lookup"><span data-stu-id="6412d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6412d-105">参数</span><span class="sxs-lookup"><span data-stu-id="6412d-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6412d-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="6412d-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="6412d-107">需要引用的文件。</span><span class="sxs-lookup"><span data-stu-id="6412d-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="6412d-108">在中定义类型的文件的标记，通常用[ImportFile 方法](importfile-method.md)进行检索。</span><span class="sxs-lookup"><span data-stu-id="6412d-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="6412d-109">接收程序集或模块引用。</span><span class="sxs-lookup"><span data-stu-id="6412d-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6412d-110">返回值</span><span class="sxs-lookup"><span data-stu-id="6412d-110">Return Value</span></span>  
 <span data-ttu-id="6412d-111">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="6412d-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6412d-112">要求</span><span class="sxs-lookup"><span data-stu-id="6412d-112">Requirements</span></span>  
 <span data-ttu-id="6412d-113">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="6412d-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6412d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6412d-114">See also</span></span>

- [<span data-ttu-id="6412d-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="6412d-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6412d-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="6412d-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6412d-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="6412d-117">ALink API</span></span>](index.md)
