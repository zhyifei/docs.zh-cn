---
title: "ISymUnmanagedReaderSymbolSearchInfo 接口"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7f53e45eb321f114483648afc63d2669065a791
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="b69bd-102">ISymUnmanagedReaderSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="b69bd-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="b69bd-103">提供用于获取符号搜索信息的方法。</span><span class="sxs-lookup"><span data-stu-id="b69bd-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="b69bd-104">通过调用来获取此接口`QueryInterface`上实现的对象[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b69bd-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b69bd-105">方法</span><span class="sxs-lookup"><span data-stu-id="b69bd-105">Methods</span></span>  
  
|<span data-ttu-id="b69bd-106">方法</span><span class="sxs-lookup"><span data-stu-id="b69bd-106">Method</span></span>|<span data-ttu-id="b69bd-107">描述</span><span class="sxs-lookup"><span data-stu-id="b69bd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b69bd-108">GetSymbolSearchInfo 方法</span><span class="sxs-lookup"><span data-stu-id="b69bd-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="b69bd-109">获取符号搜索信息。</span><span class="sxs-lookup"><span data-stu-id="b69bd-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="b69bd-110">GetSymbolSearchInfoCount 方法</span><span class="sxs-lookup"><span data-stu-id="b69bd-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="b69bd-111">获取符号搜索信息的计数。</span><span class="sxs-lookup"><span data-stu-id="b69bd-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b69bd-112">惠?</span><span class="sxs-lookup"><span data-stu-id="b69bd-112">Requirements</span></span>  
 <span data-ttu-id="b69bd-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b69bd-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b69bd-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b69bd-114">See Also</span></span>  
 [<span data-ttu-id="b69bd-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="b69bd-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
