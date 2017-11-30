---
title: "ISymUnmanagedBinder 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder
helpviewer_keywords: ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 00b0b5ee330a606ae7417185a804f3d37ab6664a
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="565b2-102">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="565b2-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="565b2-103">表示非托管代码的符号联编程序。</span><span class="sxs-lookup"><span data-stu-id="565b2-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="565b2-104">它是从受信任的源中打开程序数据库 (PDB) 文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="565b2-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="565b2-105">方法</span><span class="sxs-lookup"><span data-stu-id="565b2-105">Methods</span></span>  
  
|<span data-ttu-id="565b2-106">方法</span><span class="sxs-lookup"><span data-stu-id="565b2-106">Method</span></span>|<span data-ttu-id="565b2-107">描述</span><span class="sxs-lookup"><span data-stu-id="565b2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="565b2-108">GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="565b2-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="565b2-109">指定元数据接口和文件名称，则会返回正确[ISymUnmanagedReader](isymunmanagedreader-interface.md)将读取与模块关联的调试符号的结构。</span><span class="sxs-lookup"><span data-stu-id="565b2-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="565b2-110">GetReaderFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="565b2-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="565b2-111">指定元数据接口和包含符号存储区的流，则会返回正确[ISymUnmanagedReader](isymunmanagedreader-interface.md)结构，它将读取调试符号从给定的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="565b2-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="565b2-112">要求</span><span class="sxs-lookup"><span data-stu-id="565b2-112">Requirements</span></span>  
 <span data-ttu-id="565b2-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="565b2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="565b2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="565b2-114">See Also</span></span>  
 [<span data-ttu-id="565b2-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="565b2-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="565b2-116">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="565b2-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="565b2-117">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="565b2-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
