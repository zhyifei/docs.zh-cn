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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfd8e8fc419809a3a490639ada1c533f286fe8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157503"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="22d67-102">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="22d67-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="22d67-103">扩展符号联编程序接口。</span><span class="sxs-lookup"><span data-stu-id="22d67-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="22d67-104">通过调用来获取此接口`QueryInterface`实现的对象上`ISymUnmanagedBinder`接口。</span><span class="sxs-lookup"><span data-stu-id="22d67-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="22d67-105">它是从受信任的源打开程序数据库 (PDB) 文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="22d67-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22d67-106">方法</span><span class="sxs-lookup"><span data-stu-id="22d67-106">Methods</span></span>  
  
|<span data-ttu-id="22d67-107">方法</span><span class="sxs-lookup"><span data-stu-id="22d67-107">Method</span></span>|<span data-ttu-id="22d67-108">描述</span><span class="sxs-lookup"><span data-stu-id="22d67-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22d67-109">GetReaderFromCallback 方法</span><span class="sxs-lookup"><span data-stu-id="22d67-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="22d67-110">允许用户实现或通过回调提供`IID_IDiaReadExeAtRVACallback`或`IID_IDiaReadExeAtOffsetCallback`从内存中获取的调试目录信息</span><span class="sxs-lookup"><span data-stu-id="22d67-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22d67-111">要求</span><span class="sxs-lookup"><span data-stu-id="22d67-111">Requirements</span></span>  
 <span data-ttu-id="22d67-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="22d67-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d67-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="22d67-113">See also</span></span>

- [<span data-ttu-id="22d67-114">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="22d67-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="22d67-115">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="22d67-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="22d67-116">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="22d67-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
