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
ms.openlocfilehash: e2160ad4174d9cdfe6e27d2ba7f4748bd473a5f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944236"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="36ea5-102">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="36ea5-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="36ea5-103">表示非托管代码的符号联编程序。</span><span class="sxs-lookup"><span data-stu-id="36ea5-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="36ea5-104">打开不受信任的源中的程序数据库 (PDB) 文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="36ea5-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36ea5-105">方法</span><span class="sxs-lookup"><span data-stu-id="36ea5-105">Methods</span></span>  
  
|<span data-ttu-id="36ea5-106">方法</span><span class="sxs-lookup"><span data-stu-id="36ea5-106">Method</span></span>|<span data-ttu-id="36ea5-107">描述</span><span class="sxs-lookup"><span data-stu-id="36ea5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36ea5-108">GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="36ea5-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="36ea5-109">给定元数据接口和文件名后, 将返回正确的[ISymUnmanagedReader](isymunmanagedreader-interface.md)结构, 该结构将读取与模块关联的调试符号。</span><span class="sxs-lookup"><span data-stu-id="36ea5-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="36ea5-110">GetReaderFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="36ea5-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="36ea5-111">给定元数据接口和包含符号存储区的流时, 将返回正确的[ISymUnmanagedReader](isymunmanagedreader-interface.md)结构, 该结构将从给定的符号存储区中读取调试符号。</span><span class="sxs-lookup"><span data-stu-id="36ea5-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36ea5-112">要求</span><span class="sxs-lookup"><span data-stu-id="36ea5-112">Requirements</span></span>  
 <span data-ttu-id="36ea5-113">**标头：** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="36ea5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ea5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="36ea5-114">See also</span></span>

- [<span data-ttu-id="36ea5-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="36ea5-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="36ea5-116">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="36ea5-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="36ea5-117">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="36ea5-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
