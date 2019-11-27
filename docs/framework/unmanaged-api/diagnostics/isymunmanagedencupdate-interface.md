---
title: ISymUnmanagedENCUpdate 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: f3305a7bb003fc50f772f1100f8a17d385e4d5fc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449006"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="ed404-102">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="ed404-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="ed404-103">为 "编辑并继续" 功能提供函数。</span><span class="sxs-lookup"><span data-stu-id="ed404-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed404-104">方法</span><span class="sxs-lookup"><span data-stu-id="ed404-104">Methods</span></span>  
  
|<span data-ttu-id="ed404-105">方法</span><span class="sxs-lookup"><span data-stu-id="ed404-105">Method</span></span>|<span data-ttu-id="ed404-106">说明</span><span class="sxs-lookup"><span data-stu-id="ed404-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed404-107">GetLocalVariableCount 方法</span><span class="sxs-lookup"><span data-stu-id="ed404-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="ed404-108">获取局部变量的数目。</span><span class="sxs-lookup"><span data-stu-id="ed404-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="ed404-109">GetLocalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="ed404-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="ed404-110">获取局部变量。</span><span class="sxs-lookup"><span data-stu-id="ed404-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="ed404-111">InitializeForEnc 方法</span><span class="sxs-lookup"><span data-stu-id="ed404-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="ed404-112">允许在首次调用[ISymUnmanagedENCUpdate：： UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)方法之前计算方法边界。</span><span class="sxs-lookup"><span data-stu-id="ed404-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="ed404-113">UpdateMethodLines 方法</span><span class="sxs-lookup"><span data-stu-id="ed404-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="ed404-114">允许更新尚未重新编译但行已单独移动的方法的行信息。</span><span class="sxs-lookup"><span data-stu-id="ed404-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="ed404-115">允许每个语句的增量。</span><span class="sxs-lookup"><span data-stu-id="ed404-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="ed404-116">UpdateSymbolStore2 方法</span><span class="sxs-lookup"><span data-stu-id="ed404-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="ed404-117">如果行信息满足要求，则允许编译器省略未从程序数据库（PDB）流中修改的函数。</span><span class="sxs-lookup"><span data-stu-id="ed404-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="ed404-118">可以通过旧的 PDB 行信息和函数中所有行的一个增量来确定正确的行信息。</span><span class="sxs-lookup"><span data-stu-id="ed404-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed404-119">要求</span><span class="sxs-lookup"><span data-stu-id="ed404-119">Requirements</span></span>  
 <span data-ttu-id="ed404-120">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="ed404-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed404-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed404-121">See also</span></span>

- [<span data-ttu-id="ed404-122">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="ed404-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
