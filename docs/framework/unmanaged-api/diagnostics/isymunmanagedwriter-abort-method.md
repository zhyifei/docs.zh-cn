---
title: ISymUnmanagedWriter::Abort 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb6a3e65b1f1d59cde3bff99e491bcf09816c8ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="e1fc1-102">ISymUnmanagedWriter::Abort 方法</span><span class="sxs-lookup"><span data-stu-id="e1fc1-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="e1fc1-103">关闭而不将符号提交到符号存储区的符号编写器。</span><span class="sxs-lookup"><span data-stu-id="e1fc1-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="e1fc1-104">此调用后，符号编写器将变为无效进一步更新。</span><span class="sxs-lookup"><span data-stu-id="e1fc1-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="e1fc1-105">若要提交符号并关闭符号编写器，请使用[isymunmanagedwriter:: Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="e1fc1-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1fc1-106">语法</span><span class="sxs-lookup"><span data-stu-id="e1fc1-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e1fc1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e1fc1-107">Return Value</span></span>  
 <span data-ttu-id="e1fc1-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e1fc1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1fc1-109">要求</span><span class="sxs-lookup"><span data-stu-id="e1fc1-109">Requirements</span></span>  
 <span data-ttu-id="e1fc1-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e1fc1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1fc1-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1fc1-111">See Also</span></span>  
 [<span data-ttu-id="e1fc1-112">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="e1fc1-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
