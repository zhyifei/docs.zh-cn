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
ms.openlocfilehash: 09f39d3b6486e2ec3c04c5d1858a85ce56895527
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610153"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="bcc95-102">ISymUnmanagedWriter::Abort 方法</span><span class="sxs-lookup"><span data-stu-id="bcc95-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="bcc95-103">关闭符号编写器，而不将符号提交到符号存储区。</span><span class="sxs-lookup"><span data-stu-id="bcc95-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="bcc95-104">在此调用之后，符号编写器将变为无效以便进一步更新。</span><span class="sxs-lookup"><span data-stu-id="bcc95-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="bcc95-105">若要提交符号并关闭符号编写器，请改为使用[ISymUnmanagedWriter：： close](isymunmanagedwriter-close-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="bcc95-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcc95-106">语法</span><span class="sxs-lookup"><span data-stu-id="bcc95-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bcc95-107">返回值</span><span class="sxs-lookup"><span data-stu-id="bcc95-107">Return Value</span></span>  
 <span data-ttu-id="bcc95-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="bcc95-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcc95-109">要求</span><span class="sxs-lookup"><span data-stu-id="bcc95-109">Requirements</span></span>  
 <span data-ttu-id="bcc95-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="bcc95-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc95-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcc95-111">See also</span></span>

- [<span data-ttu-id="bcc95-112">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="bcc95-112">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
