---
title: ISymUnmanagedWriter::CloseNamespace 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f8804c911e053758442670afb3c3f27d0f7453
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986084"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="e8161-102">ISymUnmanagedWriter::CloseNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="e8161-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="e8161-103">关闭最近打开的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e8161-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8161-104">语法</span><span class="sxs-lookup"><span data-stu-id="e8161-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e8161-105">返回值</span><span class="sxs-lookup"><span data-stu-id="e8161-105">Return Value</span></span>  
 <span data-ttu-id="e8161-106">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e8161-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8161-107">要求</span><span class="sxs-lookup"><span data-stu-id="e8161-107">Requirements</span></span>  
 <span data-ttu-id="e8161-108">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e8161-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8161-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8161-109">See also</span></span>

- [<span data-ttu-id="e8161-110">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="e8161-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e8161-111">OpenNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="e8161-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
