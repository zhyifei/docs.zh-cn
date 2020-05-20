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
ms.openlocfilehash: d90a55b53ba00540137e44fc190790c4710903e3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610790"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="85794-102">ISymUnmanagedSourceServerModule 接口</span><span class="sxs-lookup"><span data-stu-id="85794-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="85794-103">提供模块的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="85794-103">Provides source server data for a module.</span></span> <span data-ttu-id="85794-104">通过 `QueryInterface` 对实现[ISymUnmanagedReader](isymunmanagedreader-interface.md)接口的对象调用来获取此接口。</span><span class="sxs-lookup"><span data-stu-id="85794-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85794-105">方法</span><span class="sxs-lookup"><span data-stu-id="85794-105">Methods</span></span>  
  
|<span data-ttu-id="85794-106">方法</span><span class="sxs-lookup"><span data-stu-id="85794-106">Method</span></span>|<span data-ttu-id="85794-107">说明</span><span class="sxs-lookup"><span data-stu-id="85794-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85794-108">GetSourceServerData 方法</span><span class="sxs-lookup"><span data-stu-id="85794-108">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="85794-109">返回模块的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="85794-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85794-110">要求</span><span class="sxs-lookup"><span data-stu-id="85794-110">Requirements</span></span>  
 <span data-ttu-id="85794-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="85794-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85794-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85794-112">See also</span></span>

- [<span data-ttu-id="85794-113">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="85794-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
