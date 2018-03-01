---
title: "ISymUnmanagedWriter3 接口"
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
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 49928044bcf2c598cdc0e4315d569f2c4eb02f1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="a4741-102">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="a4741-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="a4741-103">表示符号编写器，并提供方法来定义文档、 序列点、 词法作用域和变量。</span><span class="sxs-lookup"><span data-stu-id="a4741-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="a4741-104">此接口扩展[ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="a4741-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4741-105">方法</span><span class="sxs-lookup"><span data-stu-id="a4741-105">Methods</span></span>  
  
|<span data-ttu-id="a4741-106">方法</span><span class="sxs-lookup"><span data-stu-id="a4741-106">Method</span></span>|<span data-ttu-id="a4741-107">描述</span><span class="sxs-lookup"><span data-stu-id="a4741-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4741-108">Commit 方法</span><span class="sxs-lookup"><span data-stu-id="a4741-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="a4741-109">提交到目前为止写入到流的更改。</span><span class="sxs-lookup"><span data-stu-id="a4741-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="a4741-110">OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="a4741-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="a4741-111">打开一个方法，并提供其实际节偏移量在映像中。</span><span class="sxs-lookup"><span data-stu-id="a4741-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4741-112">惠?</span><span class="sxs-lookup"><span data-stu-id="a4741-112">Requirements</span></span>  
 <span data-ttu-id="a4741-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a4741-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4741-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4741-114">See Also</span></span>  
 [<span data-ttu-id="a4741-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="a4741-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="a4741-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="a4741-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="a4741-117">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="a4741-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
