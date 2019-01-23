---
title: ISymUnmanagedWriter3 接口
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c14706068e50fd79fb39ac9d75afacd181f7ab4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504075"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="481c7-102">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="481c7-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="481c7-103">表示符号编写器，并提供方法用于定义文档、 序列点、 词法作用域和变量。</span><span class="sxs-lookup"><span data-stu-id="481c7-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="481c7-104">此接口扩展[ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="481c7-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="481c7-105">方法</span><span class="sxs-lookup"><span data-stu-id="481c7-105">Methods</span></span>  
  
|<span data-ttu-id="481c7-106">方法</span><span class="sxs-lookup"><span data-stu-id="481c7-106">Method</span></span>|<span data-ttu-id="481c7-107">描述</span><span class="sxs-lookup"><span data-stu-id="481c7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="481c7-108">Commit 方法</span><span class="sxs-lookup"><span data-stu-id="481c7-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="481c7-109">提交所做的更改写入到流的到目前为止。</span><span class="sxs-lookup"><span data-stu-id="481c7-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="481c7-110">OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="481c7-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="481c7-111">打开一个方法，并提供其实际节偏移量为映像中。</span><span class="sxs-lookup"><span data-stu-id="481c7-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="481c7-112">要求</span><span class="sxs-lookup"><span data-stu-id="481c7-112">Requirements</span></span>  
 <span data-ttu-id="481c7-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="481c7-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="481c7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="481c7-114">See also</span></span>
- [<span data-ttu-id="481c7-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="481c7-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="481c7-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="481c7-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="481c7-117">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="481c7-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
