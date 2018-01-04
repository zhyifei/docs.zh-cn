---
title: "ISymUnmanagedBinder3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder3
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder3 Interface
helpviewer_keywords: ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c93275fc32e68f49618d93bdd0b54f1970121ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="d3ef0-102">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="d3ef0-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="d3ef0-103">扩展的符号联编程序接口。</span><span class="sxs-lookup"><span data-stu-id="d3ef0-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="d3ef0-104">通过调用来获取此接口`QueryInterface`上实现的对象`ISymUnmanagedBinder`接口。</span><span class="sxs-lookup"><span data-stu-id="d3ef0-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d3ef0-105">它是从受信任的源中打开程序数据库 (PDB) 文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="d3ef0-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3ef0-106">方法</span><span class="sxs-lookup"><span data-stu-id="d3ef0-106">Methods</span></span>  
  
|<span data-ttu-id="d3ef0-107">方法</span><span class="sxs-lookup"><span data-stu-id="d3ef0-107">Method</span></span>|<span data-ttu-id="d3ef0-108">描述</span><span class="sxs-lookup"><span data-stu-id="d3ef0-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3ef0-109">GetReaderFromCallback 方法</span><span class="sxs-lookup"><span data-stu-id="d3ef0-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="d3ef0-110">允许用户实现或通过回调提供`IID_IDiaReadExeAtRVACallback`或`IID_IDiaReadExeAtOffsetCallback`以从内存中获取的调试目录信息</span><span class="sxs-lookup"><span data-stu-id="d3ef0-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3ef0-111">惠?</span><span class="sxs-lookup"><span data-stu-id="d3ef0-111">Requirements</span></span>  
 <span data-ttu-id="d3ef0-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d3ef0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ef0-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3ef0-113">See Also</span></span>  
 [<span data-ttu-id="d3ef0-114">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="d3ef0-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="d3ef0-115">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="d3ef0-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="d3ef0-116">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="d3ef0-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
