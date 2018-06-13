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
ms.openlocfilehash: 5d7e1e4da51445a55387b813e814183bf7433e45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426918"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="fc655-102">ISymUnmanagedWriter::CloseNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="fc655-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="fc655-103">关闭最近打开的命名空间。</span><span class="sxs-lookup"><span data-stu-id="fc655-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc655-104">语法</span><span class="sxs-lookup"><span data-stu-id="fc655-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fc655-105">返回值</span><span class="sxs-lookup"><span data-stu-id="fc655-105">Return Value</span></span>  
 <span data-ttu-id="fc655-106">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="fc655-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc655-107">要求</span><span class="sxs-lookup"><span data-stu-id="fc655-107">Requirements</span></span>  
 <span data-ttu-id="fc655-108">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fc655-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc655-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc655-109">See Also</span></span>  
 [<span data-ttu-id="fc655-110">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="fc655-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="fc655-111">OpenNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="fc655-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
