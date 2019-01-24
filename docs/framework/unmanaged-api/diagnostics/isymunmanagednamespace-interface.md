---
title: ISymUnmanagedNamespace 接口
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb5a833f7d6ed8f681f1f8d7ae79ac6113b8f2bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744370"
---
# <a name="isymunmanagednamespace-interface"></a><span data-ttu-id="83bae-102">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="83bae-102">ISymUnmanagedNamespace Interface</span></span>
<span data-ttu-id="83bae-103">表示一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="83bae-103">Represents a namespace.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83bae-104">方法</span><span class="sxs-lookup"><span data-stu-id="83bae-104">Methods</span></span>  
  
|<span data-ttu-id="83bae-105">方法</span><span class="sxs-lookup"><span data-stu-id="83bae-105">Method</span></span>|<span data-ttu-id="83bae-106">描述</span><span class="sxs-lookup"><span data-stu-id="83bae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83bae-107">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="83bae-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getname-method.md)|<span data-ttu-id="83bae-108">获取此命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="83bae-108">Gets the name of this namespace.</span></span>|  
|[<span data-ttu-id="83bae-109">GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="83bae-109">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getnamespaces-method.md)|<span data-ttu-id="83bae-110">获取此命名空间的子级。</span><span class="sxs-lookup"><span data-stu-id="83bae-110">Gets the children of this namespace.</span></span>|  
|[<span data-ttu-id="83bae-111">GetVariables 方法</span><span class="sxs-lookup"><span data-stu-id="83bae-111">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getvariables-method.md)|<span data-ttu-id="83bae-112">返回在此命名空间中的全局范围内定义的所有变量。</span><span class="sxs-lookup"><span data-stu-id="83bae-112">Returns all variables defined at global scope within this namespace.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83bae-113">要求</span><span class="sxs-lookup"><span data-stu-id="83bae-113">Requirements</span></span>  
 <span data-ttu-id="83bae-114">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="83bae-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83bae-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="83bae-115">See also</span></span>
- [<span data-ttu-id="83bae-116">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="83bae-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
