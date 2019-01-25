---
title: ISymUnmanagedSymbolSearchInfo 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f5fc951b629a3158fc2c2d6047234fb661f3741
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494894"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="e3c00-102">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="e3c00-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="e3c00-103">提供了获取有关搜索路径的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="e3c00-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="e3c00-104">通过调用来获取此接口`QueryInterface`上实现的对象[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e3c00-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3c00-105">方法</span><span class="sxs-lookup"><span data-stu-id="e3c00-105">Methods</span></span>  
  
|<span data-ttu-id="e3c00-106">方法</span><span class="sxs-lookup"><span data-stu-id="e3c00-106">Method</span></span>|<span data-ttu-id="e3c00-107">描述</span><span class="sxs-lookup"><span data-stu-id="e3c00-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3c00-108">GetHRESULT 方法</span><span class="sxs-lookup"><span data-stu-id="e3c00-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="e3c00-109">获取 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="e3c00-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="e3c00-110">GetSearchPath 方法</span><span class="sxs-lookup"><span data-stu-id="e3c00-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="e3c00-111">获取搜索路径。</span><span class="sxs-lookup"><span data-stu-id="e3c00-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="e3c00-112">GetSearchPathLength 方法</span><span class="sxs-lookup"><span data-stu-id="e3c00-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="e3c00-113">获取搜索路径长度。</span><span class="sxs-lookup"><span data-stu-id="e3c00-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3c00-114">要求</span><span class="sxs-lookup"><span data-stu-id="e3c00-114">Requirements</span></span>  
 <span data-ttu-id="e3c00-115">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e3c00-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c00-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3c00-116">See also</span></span>
- [<span data-ttu-id="e3c00-117">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="e3c00-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
