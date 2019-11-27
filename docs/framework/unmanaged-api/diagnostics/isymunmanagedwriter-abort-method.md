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
ms.openlocfilehash: 6074ec5248d27b1405d2367349904f6630df951b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445991"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="414d6-102">ISymUnmanagedWriter::Abort 方法</span><span class="sxs-lookup"><span data-stu-id="414d6-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="414d6-103">关闭符号编写器，而不将符号提交到符号存储区。</span><span class="sxs-lookup"><span data-stu-id="414d6-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="414d6-104">在此调用之后，符号编写器将变为无效以便进一步更新。</span><span class="sxs-lookup"><span data-stu-id="414d6-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="414d6-105">若要提交符号并关闭符号编写器，请改为使用[ISymUnmanagedWriter：： close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="414d6-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="414d6-106">语法</span><span class="sxs-lookup"><span data-stu-id="414d6-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="414d6-107">返回值</span><span class="sxs-lookup"><span data-stu-id="414d6-107">Return Value</span></span>  
 <span data-ttu-id="414d6-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="414d6-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="414d6-109">要求</span><span class="sxs-lookup"><span data-stu-id="414d6-109">Requirements</span></span>  
 <span data-ttu-id="414d6-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="414d6-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="414d6-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="414d6-111">See also</span></span>

- [<span data-ttu-id="414d6-112">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="414d6-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
