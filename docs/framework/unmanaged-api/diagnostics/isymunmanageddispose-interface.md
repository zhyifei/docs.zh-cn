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
ms.openlocfilehash: 973fc35bb99bea6b3302760763069b9df6c548e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424399"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="4b766-102">ISymUnmanagedDispose 接口</span><span class="sxs-lookup"><span data-stu-id="4b766-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="4b766-103">释放非托管资源。</span><span class="sxs-lookup"><span data-stu-id="4b766-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4b766-104">方法</span><span class="sxs-lookup"><span data-stu-id="4b766-104">Methods</span></span>  
  
|<span data-ttu-id="4b766-105">方法</span><span class="sxs-lookup"><span data-stu-id="4b766-105">Method</span></span>|<span data-ttu-id="4b766-106">描述</span><span class="sxs-lookup"><span data-stu-id="4b766-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4b766-107">Destroy 方法</span><span class="sxs-lookup"><span data-stu-id="4b766-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="4b766-108">导致要释放所有内部引用，并在任何后续方法调用返回失败的基础对象。</span><span class="sxs-lookup"><span data-stu-id="4b766-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4b766-109">要求</span><span class="sxs-lookup"><span data-stu-id="4b766-109">Requirements</span></span>  
 <span data-ttu-id="4b766-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4b766-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b766-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b766-111">See Also</span></span>  
 [<span data-ttu-id="4b766-112">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="4b766-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
