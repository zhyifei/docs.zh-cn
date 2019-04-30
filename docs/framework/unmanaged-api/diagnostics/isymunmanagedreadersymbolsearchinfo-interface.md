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
ms.openlocfilehash: 2a872774b1c4510c8d0325c59ae7678c867c1aff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986227"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="55773-102">ISymUnmanagedReaderSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="55773-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="55773-103">提供用于获取符号搜索信息的方法。</span><span class="sxs-lookup"><span data-stu-id="55773-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="55773-104">通过调用来获取此接口`QueryInterface`上实现的对象[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="55773-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55773-105">方法</span><span class="sxs-lookup"><span data-stu-id="55773-105">Methods</span></span>  
  
|<span data-ttu-id="55773-106">方法</span><span class="sxs-lookup"><span data-stu-id="55773-106">Method</span></span>|<span data-ttu-id="55773-107">描述</span><span class="sxs-lookup"><span data-stu-id="55773-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="55773-108">GetSymbolSearchInfo 方法</span><span class="sxs-lookup"><span data-stu-id="55773-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="55773-109">获取符号搜索信息。</span><span class="sxs-lookup"><span data-stu-id="55773-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="55773-110">GetSymbolSearchInfoCount 方法</span><span class="sxs-lookup"><span data-stu-id="55773-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="55773-111">获取符号搜索信息的计数。</span><span class="sxs-lookup"><span data-stu-id="55773-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55773-112">要求</span><span class="sxs-lookup"><span data-stu-id="55773-112">Requirements</span></span>  
 <span data-ttu-id="55773-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="55773-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55773-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="55773-114">See also</span></span>

- [<span data-ttu-id="55773-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="55773-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
