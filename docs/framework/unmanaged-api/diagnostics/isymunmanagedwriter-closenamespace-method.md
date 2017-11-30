---
title: "ISymUnmanagedWriter::CloseNamespace 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8423e21fbc868e4b6891279d19b2be7c1faef583
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="4c7f7-102">ISymUnmanagedWriter::CloseNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="4c7f7-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="4c7f7-103">关闭最近打开的命名空间。</span><span class="sxs-lookup"><span data-stu-id="4c7f7-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c7f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="4c7f7-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4c7f7-105">返回值</span><span class="sxs-lookup"><span data-stu-id="4c7f7-105">Return Value</span></span>  
 <span data-ttu-id="4c7f7-106">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="4c7f7-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c7f7-107">要求</span><span class="sxs-lookup"><span data-stu-id="4c7f7-107">Requirements</span></span>  
 <span data-ttu-id="4c7f7-108">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4c7f7-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c7f7-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c7f7-109">See Also</span></span>  
 [<span data-ttu-id="4c7f7-110">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="4c7f7-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="4c7f7-111">OpenNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="4c7f7-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
