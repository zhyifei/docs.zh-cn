---
title: "ISymUnmanagedNamespace 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace
helpviewer_keywords:
- ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: d42bea4e-5848-4e43-a883-69af7a313ce9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1acca300362162b94410aadb10b123b4ecacc664
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespace-interface"></a><span data-ttu-id="e1fc4-102">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="e1fc4-102">ISymUnmanagedNamespace Interface</span></span>
<span data-ttu-id="e1fc4-103">表示一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="e1fc4-103">Represents a namespace.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1fc4-104">方法</span><span class="sxs-lookup"><span data-stu-id="e1fc4-104">Methods</span></span>  
  
|<span data-ttu-id="e1fc4-105">方法</span><span class="sxs-lookup"><span data-stu-id="e1fc4-105">Method</span></span>|<span data-ttu-id="e1fc4-106">描述</span><span class="sxs-lookup"><span data-stu-id="e1fc4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1fc4-107">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="e1fc4-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getname-method.md)|<span data-ttu-id="e1fc4-108">获取此命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="e1fc4-108">Gets the name of this namespace.</span></span>|  
|[<span data-ttu-id="e1fc4-109">GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="e1fc4-109">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getnamespaces-method.md)|<span data-ttu-id="e1fc4-110">获取此命名空间的子级。</span><span class="sxs-lookup"><span data-stu-id="e1fc4-110">Gets the children of this namespace.</span></span>|  
|[<span data-ttu-id="e1fc4-111">GetVariables 方法</span><span class="sxs-lookup"><span data-stu-id="e1fc4-111">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getvariables-method.md)|<span data-ttu-id="e1fc4-112">返回在此命名空间中的全局范围内定义的所有变量。</span><span class="sxs-lookup"><span data-stu-id="e1fc4-112">Returns all variables defined at global scope within this namespace.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1fc4-113">惠?</span><span class="sxs-lookup"><span data-stu-id="e1fc4-113">Requirements</span></span>  
 <span data-ttu-id="e1fc4-114">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e1fc4-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1fc4-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1fc4-115">See Also</span></span>  
 [<span data-ttu-id="e1fc4-116">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="e1fc4-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
