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
ms.openlocfilehash: a33d8b489551dc69542e1b12bcf83602ec5a2008
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427243"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="95547-102">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="95547-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="95547-103">表示的方法内的词法范围。</span><span class="sxs-lookup"><span data-stu-id="95547-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="95547-104">此接口扩展[ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)使用的方法来获取有关定义的常量的信息的范围内的接口。</span><span class="sxs-lookup"><span data-stu-id="95547-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95547-105">方法</span><span class="sxs-lookup"><span data-stu-id="95547-105">Methods</span></span>  
  
|<span data-ttu-id="95547-106">方法</span><span class="sxs-lookup"><span data-stu-id="95547-106">Method</span></span>|<span data-ttu-id="95547-107">描述</span><span class="sxs-lookup"><span data-stu-id="95547-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95547-108">GetConstantCount 方法</span><span class="sxs-lookup"><span data-stu-id="95547-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="95547-109">获取此范围内定义的常量的计数。</span><span class="sxs-lookup"><span data-stu-id="95547-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="95547-110">GetConstants 方法</span><span class="sxs-lookup"><span data-stu-id="95547-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="95547-111">获取此范围内定义的局部常量。</span><span class="sxs-lookup"><span data-stu-id="95547-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95547-112">要求</span><span class="sxs-lookup"><span data-stu-id="95547-112">Requirements</span></span>  
 <span data-ttu-id="95547-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="95547-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95547-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="95547-114">See Also</span></span>  
 [<span data-ttu-id="95547-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="95547-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="95547-116">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="95547-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
