---
title: SetAssemblyProps 方法
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
ms.openlocfilehash: 4bfad8b985a8ef059031464e99a8004842b276c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445583"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="44e0d-102">SetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="44e0d-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="44e0d-103">分配程序集级别属性。</span><span class="sxs-lookup"><span data-stu-id="44e0d-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e0d-104">语法</span><span class="sxs-lookup"><span data-stu-id="44e0d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="44e0d-105">参数</span><span class="sxs-lookup"><span data-stu-id="44e0d-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="44e0d-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="44e0d-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="44e0d-107">定义属性的文件。</span><span class="sxs-lookup"><span data-stu-id="44e0d-107">File that defines the property.</span></span> <span data-ttu-id="44e0d-108">如果 `AssemblyID` 不指示未绑定 .netmodule，则可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="44e0d-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="44e0d-109">指示要修改的选项。</span><span class="sxs-lookup"><span data-stu-id="44e0d-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="44e0d-110">选项的新值。</span><span class="sxs-lookup"><span data-stu-id="44e0d-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44e0d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="44e0d-111">Return Value</span></span>  
 <span data-ttu-id="44e0d-112">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="44e0d-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44e0d-113">要求</span><span class="sxs-lookup"><span data-stu-id="44e0d-113">Requirements</span></span>  
 <span data-ttu-id="44e0d-114">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="44e0d-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e0d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44e0d-115">See also</span></span>

- [<span data-ttu-id="44e0d-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="44e0d-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="44e0d-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="44e0d-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="44e0d-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="44e0d-118">ALink API</span></span>](index.md)
