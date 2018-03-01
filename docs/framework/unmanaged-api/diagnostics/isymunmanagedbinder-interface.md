---
title: "ISymUnmanagedBinder 接口"
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
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 79d3758f57976d08d4599de500e2e12e4d67cb4b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="eb8ee-102">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="eb8ee-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="eb8ee-103">表示非托管代码的符号联编程序。</span><span class="sxs-lookup"><span data-stu-id="eb8ee-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb8ee-104">它是从受信任的源中打开程序数据库 (PDB) 文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="eb8ee-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb8ee-105">方法</span><span class="sxs-lookup"><span data-stu-id="eb8ee-105">Methods</span></span>  
  
|<span data-ttu-id="eb8ee-106">方法</span><span class="sxs-lookup"><span data-stu-id="eb8ee-106">Method</span></span>|<span data-ttu-id="eb8ee-107">描述</span><span class="sxs-lookup"><span data-stu-id="eb8ee-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb8ee-108">GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="eb8ee-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="eb8ee-109">指定元数据接口和文件名称，则会返回正确[ISymUnmanagedReader](isymunmanagedreader-interface.md)将读取与模块关联的调试符号的结构。</span><span class="sxs-lookup"><span data-stu-id="eb8ee-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="eb8ee-110">GetReaderFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="eb8ee-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="eb8ee-111">指定元数据接口和包含符号存储区的流，则会返回正确[ISymUnmanagedReader](isymunmanagedreader-interface.md)结构，它将读取调试符号从给定的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="eb8ee-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb8ee-112">惠?</span><span class="sxs-lookup"><span data-stu-id="eb8ee-112">Requirements</span></span>  
 <span data-ttu-id="eb8ee-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="eb8ee-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb8ee-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb8ee-114">See Also</span></span>  
 [<span data-ttu-id="eb8ee-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="eb8ee-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="eb8ee-116">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="eb8ee-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="eb8ee-117">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="eb8ee-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
