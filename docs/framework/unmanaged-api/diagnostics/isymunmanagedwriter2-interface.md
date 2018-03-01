---
title: "ISymUnmanagedWriter2 接口"
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
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 98461cd2c2bc26d78f3f3f747b95d46576ba01e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="f2df8-102">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="f2df8-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="f2df8-103">表示符号编写器，并提供方法来定义文档、 序列点、 词法作用域和变量。</span><span class="sxs-lookup"><span data-stu-id="f2df8-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="f2df8-104">此接口扩展[ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f2df8-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2df8-105">方法</span><span class="sxs-lookup"><span data-stu-id="f2df8-105">Methods</span></span>  
  
|<span data-ttu-id="f2df8-106">方法</span><span class="sxs-lookup"><span data-stu-id="f2df8-106">Method</span></span>|<span data-ttu-id="f2df8-107">描述</span><span class="sxs-lookup"><span data-stu-id="f2df8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2df8-108">DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="f2df8-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="f2df8-109">定义的常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="f2df8-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="f2df8-110">DefineGlobalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="f2df8-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="f2df8-111">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="f2df8-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="f2df8-112">DefineLocalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="f2df8-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="f2df8-113">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="f2df8-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2df8-114">惠?</span><span class="sxs-lookup"><span data-stu-id="f2df8-114">Requirements</span></span>  
 <span data-ttu-id="f2df8-115">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f2df8-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2df8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2df8-116">See Also</span></span>  
 [<span data-ttu-id="f2df8-117">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="f2df8-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="f2df8-118">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="f2df8-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="f2df8-119">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="f2df8-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
