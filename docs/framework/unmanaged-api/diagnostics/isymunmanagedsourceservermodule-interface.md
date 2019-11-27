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
ms.openlocfilehash: 9eac87d7627f502b13d805b8c5656e01ac578e7f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446205"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="81e42-102">ISymUnmanagedSourceServerModule 接口</span><span class="sxs-lookup"><span data-stu-id="81e42-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="81e42-103">提供模块的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="81e42-103">Provides source server data for a module.</span></span> <span data-ttu-id="81e42-104">通过对实现[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口的对象调用 `QueryInterface` 获取此接口。</span><span class="sxs-lookup"><span data-stu-id="81e42-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81e42-105">方法</span><span class="sxs-lookup"><span data-stu-id="81e42-105">Methods</span></span>  
  
|<span data-ttu-id="81e42-106">方法</span><span class="sxs-lookup"><span data-stu-id="81e42-106">Method</span></span>|<span data-ttu-id="81e42-107">说明</span><span class="sxs-lookup"><span data-stu-id="81e42-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81e42-108">GetSourceServerData 方法</span><span class="sxs-lookup"><span data-stu-id="81e42-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="81e42-109">返回模块的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="81e42-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81e42-110">要求</span><span class="sxs-lookup"><span data-stu-id="81e42-110">Requirements</span></span>  
 <span data-ttu-id="81e42-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="81e42-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e42-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81e42-112">See also</span></span>

- [<span data-ttu-id="81e42-113">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="81e42-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
