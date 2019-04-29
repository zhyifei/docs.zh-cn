---
title: ISymUnmanagedBinder 接口
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6d91f68ac737ce28cdbef926119bb3711bc1096
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940057"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="4e536-102">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="4e536-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="4e536-103">表示非托管代码的符号联编程序。</span><span class="sxs-lookup"><span data-stu-id="4e536-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4e536-104">它是从受信任的源打开程序数据库 (PDB) 文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="4e536-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e536-105">方法</span><span class="sxs-lookup"><span data-stu-id="4e536-105">Methods</span></span>  
  
|<span data-ttu-id="4e536-106">方法</span><span class="sxs-lookup"><span data-stu-id="4e536-106">Method</span></span>|<span data-ttu-id="4e536-107">描述</span><span class="sxs-lookup"><span data-stu-id="4e536-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e536-108">GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="4e536-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="4e536-109">给定元数据接口和文件名称，返回的正确[ISymUnmanagedReader](isymunmanagedreader-interface.md)结构，它将读取与模块关联的调试符号。</span><span class="sxs-lookup"><span data-stu-id="4e536-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="4e536-110">GetReaderFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="4e536-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="4e536-111">给定元数据接口并包含符号存储区的流，返回的正确[ISymUnmanagedReader](isymunmanagedreader-interface.md)从给定的符号存储区的结构，它将读取调试符号。</span><span class="sxs-lookup"><span data-stu-id="4e536-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e536-112">要求</span><span class="sxs-lookup"><span data-stu-id="4e536-112">Requirements</span></span>  
 <span data-ttu-id="4e536-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4e536-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e536-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e536-114">See also</span></span>

- [<span data-ttu-id="4e536-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="4e536-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="4e536-116">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="4e536-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="4e536-117">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="4e536-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
