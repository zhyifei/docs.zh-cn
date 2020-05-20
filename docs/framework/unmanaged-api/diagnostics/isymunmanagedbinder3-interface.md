---
title: ISymUnmanagedBinder3 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
ms.openlocfilehash: 5a26de2a8f5439b7c81560927c991d449e57b76c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441586"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="18829-102">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="18829-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="18829-103">扩展符号联编程序接口。</span><span class="sxs-lookup"><span data-stu-id="18829-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="18829-104">通过对实现接口的对象调用来获取此接口 `QueryInterface` `ISymUnmanagedBinder` 。</span><span class="sxs-lookup"><span data-stu-id="18829-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="18829-105">打开不受信任的源中的程序数据库（PDB）文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="18829-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="18829-106">方法</span><span class="sxs-lookup"><span data-stu-id="18829-106">Methods</span></span>  
  
|<span data-ttu-id="18829-107">方法</span><span class="sxs-lookup"><span data-stu-id="18829-107">Method</span></span>|<span data-ttu-id="18829-108">说明</span><span class="sxs-lookup"><span data-stu-id="18829-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18829-109">GetReaderFromCallback 方法</span><span class="sxs-lookup"><span data-stu-id="18829-109">GetReaderFromCallback Method</span></span>](isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="18829-110">允许用户通过回调来实现或提供， `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` 以从内存中获取调试目录信息</span><span class="sxs-lookup"><span data-stu-id="18829-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18829-111">要求</span><span class="sxs-lookup"><span data-stu-id="18829-111">Requirements</span></span>  
 <span data-ttu-id="18829-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="18829-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18829-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18829-113">See also</span></span>

- [<span data-ttu-id="18829-114">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="18829-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="18829-115">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="18829-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="18829-116">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="18829-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
