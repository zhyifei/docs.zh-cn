---
title: ISymUnmanagedScope2 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0109b25b1cdc42204fc4873577e495641c4ec4fd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131451"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="76f44-102">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="76f44-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="76f44-103">表示一种方法内的词法范围。</span><span class="sxs-lookup"><span data-stu-id="76f44-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="76f44-104">此接口扩展[ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)接口使用的范围内获取有关定义的常量的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="76f44-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76f44-105">方法</span><span class="sxs-lookup"><span data-stu-id="76f44-105">Methods</span></span>  
  
|<span data-ttu-id="76f44-106">方法</span><span class="sxs-lookup"><span data-stu-id="76f44-106">Method</span></span>|<span data-ttu-id="76f44-107">描述</span><span class="sxs-lookup"><span data-stu-id="76f44-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76f44-108">GetConstantCount 方法</span><span class="sxs-lookup"><span data-stu-id="76f44-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="76f44-109">获取此范围内定义的常量的计数。</span><span class="sxs-lookup"><span data-stu-id="76f44-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="76f44-110">GetConstants 方法</span><span class="sxs-lookup"><span data-stu-id="76f44-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="76f44-111">获取此范围内定义的局部常量。</span><span class="sxs-lookup"><span data-stu-id="76f44-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76f44-112">要求</span><span class="sxs-lookup"><span data-stu-id="76f44-112">Requirements</span></span>  
 <span data-ttu-id="76f44-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="76f44-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f44-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="76f44-114">See also</span></span>

- [<span data-ttu-id="76f44-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="76f44-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="76f44-116">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="76f44-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
