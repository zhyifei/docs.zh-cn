---
title: ISymUnmanagedSourceServerModule 接口
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a63700abf77d56134ca30620033c398af735599
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426734"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="1a725-102">ISymUnmanagedSourceServerModule 接口</span><span class="sxs-lookup"><span data-stu-id="1a725-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="1a725-103">模块提供源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="1a725-103">Provides source server data for a module.</span></span> <span data-ttu-id="1a725-104">通过调用来获取此接口`QueryInterface`上实现的对象[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="1a725-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1a725-105">方法</span><span class="sxs-lookup"><span data-stu-id="1a725-105">Methods</span></span>  
  
|<span data-ttu-id="1a725-106">方法</span><span class="sxs-lookup"><span data-stu-id="1a725-106">Method</span></span>|<span data-ttu-id="1a725-107">描述</span><span class="sxs-lookup"><span data-stu-id="1a725-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1a725-108">GetSourceServerData 方法</span><span class="sxs-lookup"><span data-stu-id="1a725-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="1a725-109">返回模块的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="1a725-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a725-110">要求</span><span class="sxs-lookup"><span data-stu-id="1a725-110">Requirements</span></span>  
 <span data-ttu-id="1a725-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1a725-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a725-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a725-112">See Also</span></span>  
 [<span data-ttu-id="1a725-113">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="1a725-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
