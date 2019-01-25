---
title: ISymUnmanagedReaderSymbolSearchInfo 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a6eb99de44c2d3f1afe6dda2d6ec895ec57c617
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634995"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="d922f-102">ISymUnmanagedReaderSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="d922f-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="d922f-103">提供用于获取符号搜索信息的方法。</span><span class="sxs-lookup"><span data-stu-id="d922f-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="d922f-104">通过调用来获取此接口`QueryInterface`上实现的对象[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="d922f-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d922f-105">方法</span><span class="sxs-lookup"><span data-stu-id="d922f-105">Methods</span></span>  
  
|<span data-ttu-id="d922f-106">方法</span><span class="sxs-lookup"><span data-stu-id="d922f-106">Method</span></span>|<span data-ttu-id="d922f-107">描述</span><span class="sxs-lookup"><span data-stu-id="d922f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d922f-108">GetSymbolSearchInfo 方法</span><span class="sxs-lookup"><span data-stu-id="d922f-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="d922f-109">获取符号搜索信息。</span><span class="sxs-lookup"><span data-stu-id="d922f-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="d922f-110">GetSymbolSearchInfoCount 方法</span><span class="sxs-lookup"><span data-stu-id="d922f-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="d922f-111">获取符号搜索信息的计数。</span><span class="sxs-lookup"><span data-stu-id="d922f-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d922f-112">要求</span><span class="sxs-lookup"><span data-stu-id="d922f-112">Requirements</span></span>  
 <span data-ttu-id="d922f-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d922f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d922f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d922f-114">See also</span></span>
- [<span data-ttu-id="d922f-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="d922f-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
