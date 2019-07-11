---
title: ISymUnmanagedWriter::CloseMethod 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23f77f30b84622dffd8c76bb9302ad564f40ed41
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778188"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="27481-102">ISymUnmanagedWriter::CloseMethod 方法</span><span class="sxs-lookup"><span data-stu-id="27481-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="27481-103">关闭当前方法。</span><span class="sxs-lookup"><span data-stu-id="27481-103">Closes the current method.</span></span> <span data-ttu-id="27481-104">一种方法关闭之后，可以在其中定义没有更多的符号。</span><span class="sxs-lookup"><span data-stu-id="27481-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27481-105">语法</span><span class="sxs-lookup"><span data-stu-id="27481-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="27481-106">返回值</span><span class="sxs-lookup"><span data-stu-id="27481-106">Return Value</span></span>  
 <span data-ttu-id="27481-107">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="27481-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27481-108">要求</span><span class="sxs-lookup"><span data-stu-id="27481-108">Requirements</span></span>  
 <span data-ttu-id="27481-109">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="27481-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27481-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="27481-110">See also</span></span>

- [<span data-ttu-id="27481-111">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="27481-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="27481-112">OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="27481-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
