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
ms.openlocfilehash: 08d9ba8f8c9a251bd0db0ffe256af7db0164ba2f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449226"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="bf3d7-102">ISymUnmanagedDispose 接口</span><span class="sxs-lookup"><span data-stu-id="bf3d7-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="bf3d7-103">释放非托管资源。</span><span class="sxs-lookup"><span data-stu-id="bf3d7-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf3d7-104">方法</span><span class="sxs-lookup"><span data-stu-id="bf3d7-104">Methods</span></span>  
  
|<span data-ttu-id="bf3d7-105">方法</span><span class="sxs-lookup"><span data-stu-id="bf3d7-105">Method</span></span>|<span data-ttu-id="bf3d7-106">说明</span><span class="sxs-lookup"><span data-stu-id="bf3d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf3d7-107">Destroy 方法</span><span class="sxs-lookup"><span data-stu-id="bf3d7-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="bf3d7-108">使基础对象释放所有内部引用，并在所有后续方法调用中返回失败。</span><span class="sxs-lookup"><span data-stu-id="bf3d7-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf3d7-109">要求</span><span class="sxs-lookup"><span data-stu-id="bf3d7-109">Requirements</span></span>  
 <span data-ttu-id="bf3d7-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="bf3d7-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3d7-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf3d7-111">See also</span></span>

- [<span data-ttu-id="bf3d7-112">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="bf3d7-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
