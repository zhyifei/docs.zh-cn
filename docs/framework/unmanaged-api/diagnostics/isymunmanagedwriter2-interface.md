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
ms.openlocfilehash: 97df6d6ec9a446e89eef8a9f8a5e5e8ddc85c0f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127395"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="b1934-102">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="b1934-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="b1934-103">表示符号编写器，并提供方法用于定义文档、 序列点、 词法作用域和变量。</span><span class="sxs-lookup"><span data-stu-id="b1934-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="b1934-104">此接口扩展[ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b1934-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1934-105">方法</span><span class="sxs-lookup"><span data-stu-id="b1934-105">Methods</span></span>  
  
|<span data-ttu-id="b1934-106">方法</span><span class="sxs-lookup"><span data-stu-id="b1934-106">Method</span></span>|<span data-ttu-id="b1934-107">描述</span><span class="sxs-lookup"><span data-stu-id="b1934-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1934-108">DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="b1934-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="b1934-109">定义常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="b1934-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="b1934-110">DefineGlobalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="b1934-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="b1934-111">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="b1934-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="b1934-112">DefineLocalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="b1934-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="b1934-113">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="b1934-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1934-114">要求</span><span class="sxs-lookup"><span data-stu-id="b1934-114">Requirements</span></span>  
 <span data-ttu-id="b1934-115">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b1934-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1934-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1934-116">See also</span></span>

- [<span data-ttu-id="b1934-117">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="b1934-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="b1934-118">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="b1934-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="b1934-119">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="b1934-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
