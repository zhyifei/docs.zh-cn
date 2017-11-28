---
title: "ISymUnmanagedWriter3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter3
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter3
helpviewer_keywords: ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3babf8b3a54f07ac4eb14e326f66c70834953dfe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="5cbd8-102">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="5cbd8-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="5cbd8-103">表示符号编写器，并提供方法来定义文档、 序列点、 词法作用域和变量。</span><span class="sxs-lookup"><span data-stu-id="5cbd8-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="5cbd8-104">此接口扩展[ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5cbd8-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5cbd8-105">方法</span><span class="sxs-lookup"><span data-stu-id="5cbd8-105">Methods</span></span>  
  
|<span data-ttu-id="5cbd8-106">方法</span><span class="sxs-lookup"><span data-stu-id="5cbd8-106">Method</span></span>|<span data-ttu-id="5cbd8-107">描述</span><span class="sxs-lookup"><span data-stu-id="5cbd8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5cbd8-108">Commit 方法</span><span class="sxs-lookup"><span data-stu-id="5cbd8-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="5cbd8-109">提交到目前为止写入到流的更改。</span><span class="sxs-lookup"><span data-stu-id="5cbd8-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="5cbd8-110">OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="5cbd8-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="5cbd8-111">打开一个方法，并提供其实际节偏移量在映像中。</span><span class="sxs-lookup"><span data-stu-id="5cbd8-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5cbd8-112">要求</span><span class="sxs-lookup"><span data-stu-id="5cbd8-112">Requirements</span></span>  
 <span data-ttu-id="5cbd8-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5cbd8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cbd8-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cbd8-114">See Also</span></span>  
 [<span data-ttu-id="5cbd8-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="5cbd8-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="5cbd8-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="5cbd8-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="5cbd8-117">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="5cbd8-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
