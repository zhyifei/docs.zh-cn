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
ms.openlocfilehash: 591279a80b7d6a770127fb98eb71c056c48bdffd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934142"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="8da87-102">ISymUnmanagedWriter::CloseMethod 方法</span><span class="sxs-lookup"><span data-stu-id="8da87-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="8da87-103">关闭当前方法。</span><span class="sxs-lookup"><span data-stu-id="8da87-103">Closes the current method.</span></span> <span data-ttu-id="8da87-104">一种方法关闭之后，可以在其中定义没有更多的符号。</span><span class="sxs-lookup"><span data-stu-id="8da87-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8da87-105">语法</span><span class="sxs-lookup"><span data-stu-id="8da87-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8da87-106">返回值</span><span class="sxs-lookup"><span data-stu-id="8da87-106">Return Value</span></span>  
 <span data-ttu-id="8da87-107">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="8da87-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8da87-108">要求</span><span class="sxs-lookup"><span data-stu-id="8da87-108">Requirements</span></span>  
 <span data-ttu-id="8da87-109">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8da87-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8da87-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8da87-110">See also</span></span>

- [<span data-ttu-id="8da87-111">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="8da87-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="8da87-112">OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="8da87-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
