---
title: ISymUnmanagedBinder3 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
ms.openlocfilehash: e4a415b21e3980e7603319d7acbb3831462fac9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449293"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="4e786-102">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="4e786-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="4e786-103">Extends the symbol binder interface.</span><span class="sxs-lookup"><span data-stu-id="4e786-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="4e786-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="4e786-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4e786-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span><span class="sxs-lookup"><span data-stu-id="4e786-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e786-106">方法</span><span class="sxs-lookup"><span data-stu-id="4e786-106">Methods</span></span>  
  
|<span data-ttu-id="4e786-107">方法</span><span class="sxs-lookup"><span data-stu-id="4e786-107">Method</span></span>|<span data-ttu-id="4e786-108">描述</span><span class="sxs-lookup"><span data-stu-id="4e786-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e786-109">GetReaderFromCallback 方法</span><span class="sxs-lookup"><span data-stu-id="4e786-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="4e786-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span><span class="sxs-lookup"><span data-stu-id="4e786-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e786-111">要求</span><span class="sxs-lookup"><span data-stu-id="4e786-111">Requirements</span></span>  
 <span data-ttu-id="4e786-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4e786-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e786-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e786-113">See also</span></span>

- [<span data-ttu-id="4e786-114">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="4e786-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="4e786-115">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="4e786-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="4e786-116">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="4e786-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
