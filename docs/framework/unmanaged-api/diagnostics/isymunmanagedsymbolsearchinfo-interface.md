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
ms.openlocfilehash: d7371361b074454e8aa359c49b964193c12f3034
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446144"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="4521a-102">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="4521a-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="4521a-103">提供获取有关搜索路径的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="4521a-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="4521a-104">通过对实现[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口的对象调用 `QueryInterface` 获取此接口。</span><span class="sxs-lookup"><span data-stu-id="4521a-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4521a-105">方法</span><span class="sxs-lookup"><span data-stu-id="4521a-105">Methods</span></span>  
  
|<span data-ttu-id="4521a-106">方法</span><span class="sxs-lookup"><span data-stu-id="4521a-106">Method</span></span>|<span data-ttu-id="4521a-107">说明</span><span class="sxs-lookup"><span data-stu-id="4521a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4521a-108">GetHRESULT 方法</span><span class="sxs-lookup"><span data-stu-id="4521a-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="4521a-109">获取 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="4521a-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="4521a-110">GetSearchPath 方法</span><span class="sxs-lookup"><span data-stu-id="4521a-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="4521a-111">获取搜索路径。</span><span class="sxs-lookup"><span data-stu-id="4521a-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="4521a-112">GetSearchPathLength 方法</span><span class="sxs-lookup"><span data-stu-id="4521a-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="4521a-113">获取搜索路径长度。</span><span class="sxs-lookup"><span data-stu-id="4521a-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4521a-114">要求</span><span class="sxs-lookup"><span data-stu-id="4521a-114">Requirements</span></span>  
 <span data-ttu-id="4521a-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="4521a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4521a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4521a-116">See also</span></span>

- [<span data-ttu-id="4521a-117">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="4521a-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
