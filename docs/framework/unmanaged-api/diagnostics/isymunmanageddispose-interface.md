---
title: ISymUnmanagedDispose 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose
helpviewer_keywords:
- ISymUnmanagedDispose interface [.NET Framework debugging]
ms.assetid: b1d74e83-a200-4d00-8fbd-27918808616d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8e81cea13fb8d25701ccbe163f112904baf47a9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939914"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="badf2-102">ISymUnmanagedDispose 接口</span><span class="sxs-lookup"><span data-stu-id="badf2-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="badf2-103">释放非托管资源。</span><span class="sxs-lookup"><span data-stu-id="badf2-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="badf2-104">方法</span><span class="sxs-lookup"><span data-stu-id="badf2-104">Methods</span></span>  
  
|<span data-ttu-id="badf2-105">方法</span><span class="sxs-lookup"><span data-stu-id="badf2-105">Method</span></span>|<span data-ttu-id="badf2-106">描述</span><span class="sxs-lookup"><span data-stu-id="badf2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="badf2-107">Destroy 方法</span><span class="sxs-lookup"><span data-stu-id="badf2-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="badf2-108">导致要释放内部的所有引用和任何后续方法调用上返回失败的基础对象。</span><span class="sxs-lookup"><span data-stu-id="badf2-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="badf2-109">要求</span><span class="sxs-lookup"><span data-stu-id="badf2-109">Requirements</span></span>  
 <span data-ttu-id="badf2-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="badf2-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="badf2-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="badf2-111">See also</span></span>

- [<span data-ttu-id="badf2-112">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="badf2-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
