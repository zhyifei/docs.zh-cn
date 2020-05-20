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
ms.openlocfilehash: 7a4ffc0c417ae839e5c97ffe6884bc3230a603b7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610101"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="a1738-102">ISymUnmanagedWriter::CloseNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="a1738-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="a1738-103">关闭最近打开的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a1738-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1738-104">语法</span><span class="sxs-lookup"><span data-stu-id="a1738-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a1738-105">返回值</span><span class="sxs-lookup"><span data-stu-id="a1738-105">Return Value</span></span>  
 <span data-ttu-id="a1738-106">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="a1738-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1738-107">要求</span><span class="sxs-lookup"><span data-stu-id="a1738-107">Requirements</span></span>  
 <span data-ttu-id="a1738-108">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="a1738-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1738-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1738-109">See also</span></span>

- [<span data-ttu-id="a1738-110">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="a1738-110">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="a1738-111">OpenNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="a1738-111">OpenNamespace Method</span></span>](isymunmanagedwriter-opennamespace-method.md)
