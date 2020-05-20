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
ms.openlocfilehash: 3f6cea68a4379f8769ccbdbc6911cc5c425d3369
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614872"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="d0594-102">ISymUnmanagedReaderSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="d0594-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="d0594-103">提供用于获取符号搜索信息的方法。</span><span class="sxs-lookup"><span data-stu-id="d0594-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="d0594-104">通过 `QueryInterface` 对实现[ISymUnmanagedReader](isymunmanagedreader-interface.md)接口的对象调用来获取此接口。</span><span class="sxs-lookup"><span data-stu-id="d0594-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0594-105">方法</span><span class="sxs-lookup"><span data-stu-id="d0594-105">Methods</span></span>  
  
|<span data-ttu-id="d0594-106">方法</span><span class="sxs-lookup"><span data-stu-id="d0594-106">Method</span></span>|<span data-ttu-id="d0594-107">说明</span><span class="sxs-lookup"><span data-stu-id="d0594-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d0594-108">GetSymbolSearchInfo 方法</span><span class="sxs-lookup"><span data-stu-id="d0594-108">GetSymbolSearchInfo Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="d0594-109">获取符号搜索信息。</span><span class="sxs-lookup"><span data-stu-id="d0594-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="d0594-110">GetSymbolSearchInfoCount 方法</span><span class="sxs-lookup"><span data-stu-id="d0594-110">GetSymbolSearchInfoCount Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="d0594-111">获取符号搜索信息的计数。</span><span class="sxs-lookup"><span data-stu-id="d0594-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0594-112">要求</span><span class="sxs-lookup"><span data-stu-id="d0594-112">Requirements</span></span>  
 <span data-ttu-id="d0594-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="d0594-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0594-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0594-114">See also</span></span>

- [<span data-ttu-id="d0594-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="d0594-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
