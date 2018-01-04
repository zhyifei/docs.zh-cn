---
title: "ISymUnmanagedBinder2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2 Interface
helpviewer_keywords: ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0fff140f6848b91e811ef4546a3e8fd50eb61e05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="d90e7-102">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="d90e7-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="d90e7-103">表示非托管代码的符号联编程序和扩展[ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="d90e7-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d90e7-104">它是从受信任的源中打开程序数据库 (PDB) 文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="d90e7-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d90e7-105">方法</span><span class="sxs-lookup"><span data-stu-id="d90e7-105">Methods</span></span>  
  
|<span data-ttu-id="d90e7-106">方法</span><span class="sxs-lookup"><span data-stu-id="d90e7-106">Method</span></span>|<span data-ttu-id="d90e7-107">描述</span><span class="sxs-lookup"><span data-stu-id="d90e7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d90e7-108">GetReaderForFile2 方法</span><span class="sxs-lookup"><span data-stu-id="d90e7-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="d90e7-109">指定元数据接口和文件名称，则会返回正确 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 将读取与模块关联的调试符号的接口。</span><span class="sxs-lookup"><span data-stu-id="d90e7-109">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="d90e7-110">提供比更广泛的搜索[isymunmanagedbinder:: Getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d90e7-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d90e7-111">惠?</span><span class="sxs-lookup"><span data-stu-id="d90e7-111">Requirements</span></span>  
 <span data-ttu-id="d90e7-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d90e7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d90e7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d90e7-113">See Also</span></span>  
 [<span data-ttu-id="d90e7-114">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="d90e7-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="d90e7-115">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="d90e7-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="d90e7-116">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="d90e7-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
