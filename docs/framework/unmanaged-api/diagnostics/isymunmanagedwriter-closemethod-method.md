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
ms.openlocfilehash: fdf24bb8533da7914128f9477987c427442383bb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610114"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="5843d-102">ISymUnmanagedWriter::CloseMethod 方法</span><span class="sxs-lookup"><span data-stu-id="5843d-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="5843d-103">关闭当前方法。</span><span class="sxs-lookup"><span data-stu-id="5843d-103">Closes the current method.</span></span> <span data-ttu-id="5843d-104">方法关闭后，不能在其中定义更多符号。</span><span class="sxs-lookup"><span data-stu-id="5843d-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5843d-105">语法</span><span class="sxs-lookup"><span data-stu-id="5843d-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5843d-106">返回值</span><span class="sxs-lookup"><span data-stu-id="5843d-106">Return Value</span></span>  
 <span data-ttu-id="5843d-107">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="5843d-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5843d-108">要求</span><span class="sxs-lookup"><span data-stu-id="5843d-108">Requirements</span></span>  
 <span data-ttu-id="5843d-109">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="5843d-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5843d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5843d-110">See also</span></span>

- [<span data-ttu-id="5843d-111">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="5843d-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="5843d-112">OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="5843d-112">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
