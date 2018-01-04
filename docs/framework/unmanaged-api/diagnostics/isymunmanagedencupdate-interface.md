---
title: "ISymUnmanagedENCUpdate 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate
helpviewer_keywords: ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f68d000824779fcffb90ec031b86b50e8c80eccd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="f7ac3-102">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="f7ac3-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="f7ac3-103">提供用于编辑并继续功能函数。</span><span class="sxs-lookup"><span data-stu-id="f7ac3-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7ac3-104">方法</span><span class="sxs-lookup"><span data-stu-id="f7ac3-104">Methods</span></span>  
  
|<span data-ttu-id="f7ac3-105">方法</span><span class="sxs-lookup"><span data-stu-id="f7ac3-105">Method</span></span>|<span data-ttu-id="f7ac3-106">描述</span><span class="sxs-lookup"><span data-stu-id="f7ac3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7ac3-107">GetLocalVariableCount 方法</span><span class="sxs-lookup"><span data-stu-id="f7ac3-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="f7ac3-108">获取本地变量的数目。</span><span class="sxs-lookup"><span data-stu-id="f7ac3-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="f7ac3-109">GetLocalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="f7ac3-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="f7ac3-110">获取本地变量。</span><span class="sxs-lookup"><span data-stu-id="f7ac3-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="f7ac3-111">InitializeForEnc 方法</span><span class="sxs-lookup"><span data-stu-id="f7ac3-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="f7ac3-112">允许在首次调用之前要计算的方法边界[isymunmanagedencupdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f7ac3-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="f7ac3-113">UpdateMethodLines 方法</span><span class="sxs-lookup"><span data-stu-id="f7ac3-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="f7ac3-114">允许更新的方法，不重新编译，但其行已独立移动的行信息。</span><span class="sxs-lookup"><span data-stu-id="f7ac3-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="f7ac3-115">允许的 delta 的每个语句。</span><span class="sxs-lookup"><span data-stu-id="f7ac3-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="f7ac3-116">UpdateSymbolStore2 方法</span><span class="sxs-lookup"><span data-stu-id="f7ac3-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="f7ac3-117">允许编译器忽略未修改的程序数据库 (PDB) 流中的函数，提供行信息符合要求。</span><span class="sxs-lookup"><span data-stu-id="f7ac3-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="f7ac3-118">可使用旧的 PDB 行信息以及该函数中的所有行的一个增量确定正确的行信息。</span><span class="sxs-lookup"><span data-stu-id="f7ac3-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7ac3-119">惠?</span><span class="sxs-lookup"><span data-stu-id="f7ac3-119">Requirements</span></span>  
 <span data-ttu-id="f7ac3-120">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f7ac3-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ac3-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7ac3-121">See Also</span></span>  
 [<span data-ttu-id="f7ac3-122">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="f7ac3-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
