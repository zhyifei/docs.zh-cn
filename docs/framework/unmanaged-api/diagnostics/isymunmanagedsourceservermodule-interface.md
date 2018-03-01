---
title: "ISymUnmanagedSourceServerModule 接口"
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
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f183c3ea69de15387f729a67328bf5ea57931750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="e6d85-102">ISymUnmanagedSourceServerModule 接口</span><span class="sxs-lookup"><span data-stu-id="e6d85-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="e6d85-103">模块提供源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="e6d85-103">Provides source server data for a module.</span></span> <span data-ttu-id="e6d85-104">通过调用来获取此接口`QueryInterface`上实现的对象[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e6d85-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6d85-105">方法</span><span class="sxs-lookup"><span data-stu-id="e6d85-105">Methods</span></span>  
  
|<span data-ttu-id="e6d85-106">方法</span><span class="sxs-lookup"><span data-stu-id="e6d85-106">Method</span></span>|<span data-ttu-id="e6d85-107">描述</span><span class="sxs-lookup"><span data-stu-id="e6d85-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6d85-108">GetSourceServerData 方法</span><span class="sxs-lookup"><span data-stu-id="e6d85-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="e6d85-109">返回模块的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="e6d85-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6d85-110">惠?</span><span class="sxs-lookup"><span data-stu-id="e6d85-110">Requirements</span></span>  
 <span data-ttu-id="e6d85-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e6d85-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d85-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6d85-112">See Also</span></span>  
 [<span data-ttu-id="e6d85-113">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="e6d85-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
