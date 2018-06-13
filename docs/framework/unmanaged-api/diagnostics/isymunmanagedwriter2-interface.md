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
ms.openlocfilehash: cbafe39fffd28a9bfccaa275c9009bc03549cda6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429422"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="619f5-102">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="619f5-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="619f5-103">表示符号编写器，并提供方法来定义文档、 序列点、 词法作用域和变量。</span><span class="sxs-lookup"><span data-stu-id="619f5-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="619f5-104">此接口扩展[ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="619f5-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="619f5-105">方法</span><span class="sxs-lookup"><span data-stu-id="619f5-105">Methods</span></span>  
  
|<span data-ttu-id="619f5-106">方法</span><span class="sxs-lookup"><span data-stu-id="619f5-106">Method</span></span>|<span data-ttu-id="619f5-107">描述</span><span class="sxs-lookup"><span data-stu-id="619f5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="619f5-108">DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="619f5-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="619f5-109">定义的常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="619f5-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="619f5-110">DefineGlobalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="619f5-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="619f5-111">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="619f5-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="619f5-112">DefineLocalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="619f5-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="619f5-113">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="619f5-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="619f5-114">要求</span><span class="sxs-lookup"><span data-stu-id="619f5-114">Requirements</span></span>  
 <span data-ttu-id="619f5-115">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="619f5-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="619f5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="619f5-116">See Also</span></span>  
 [<span data-ttu-id="619f5-117">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="619f5-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="619f5-118">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="619f5-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="619f5-119">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="619f5-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
