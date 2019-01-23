---
title: ISymUnmanagedWriter2 接口
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99e8b8bbb25bc55c7d4f2f44aac8e24210d30b83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560538"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="a15fc-102">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="a15fc-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="a15fc-103">表示符号编写器，并提供方法用于定义文档、 序列点、 词法作用域和变量。</span><span class="sxs-lookup"><span data-stu-id="a15fc-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="a15fc-104">此接口扩展[ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="a15fc-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a15fc-105">方法</span><span class="sxs-lookup"><span data-stu-id="a15fc-105">Methods</span></span>  
  
|<span data-ttu-id="a15fc-106">方法</span><span class="sxs-lookup"><span data-stu-id="a15fc-106">Method</span></span>|<span data-ttu-id="a15fc-107">描述</span><span class="sxs-lookup"><span data-stu-id="a15fc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a15fc-108">DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="a15fc-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="a15fc-109">定义常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="a15fc-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="a15fc-110">DefineGlobalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="a15fc-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="a15fc-111">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="a15fc-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="a15fc-112">DefineLocalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="a15fc-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="a15fc-113">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="a15fc-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a15fc-114">要求</span><span class="sxs-lookup"><span data-stu-id="a15fc-114">Requirements</span></span>  
 <span data-ttu-id="a15fc-115">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a15fc-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a15fc-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a15fc-116">See also</span></span>
- [<span data-ttu-id="a15fc-117">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="a15fc-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="a15fc-118">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="a15fc-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="a15fc-119">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="a15fc-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
