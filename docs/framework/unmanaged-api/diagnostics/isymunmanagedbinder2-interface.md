---
title: ISymUnmanagedBinder2 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 29501eeb6085dbc235112d98e8099fcfa4565000
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427790"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="e7847-102">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="e7847-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="e7847-103">表示非托管代码的符号联编程序和扩展[ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e7847-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e7847-104">它是从受信任的源中打开程序数据库 (PDB) 文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="e7847-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7847-105">方法</span><span class="sxs-lookup"><span data-stu-id="e7847-105">Methods</span></span>  
  
|<span data-ttu-id="e7847-106">方法</span><span class="sxs-lookup"><span data-stu-id="e7847-106">Method</span></span>|<span data-ttu-id="e7847-107">描述</span><span class="sxs-lookup"><span data-stu-id="e7847-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7847-108">GetReaderForFile2 方法</span><span class="sxs-lookup"><span data-stu-id="e7847-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="e7847-109">指定元数据接口和文件名称，则会返回正确 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 将读取与模块关联的调试符号的接口。</span><span class="sxs-lookup"><span data-stu-id="e7847-109">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="e7847-110">提供比更广泛的搜索[isymunmanagedbinder:: Getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e7847-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e7847-111">要求</span><span class="sxs-lookup"><span data-stu-id="e7847-111">Requirements</span></span>  
 <span data-ttu-id="e7847-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e7847-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7847-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7847-113">See Also</span></span>  
 [<span data-ttu-id="e7847-114">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="e7847-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="e7847-115">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="e7847-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="e7847-116">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="e7847-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
