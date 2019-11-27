---
title: SetAssemblyFile2 方法
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
ms.openlocfilehash: 4f710ef9741869a2b4fd8473ed3ecf379cfcc56d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445576"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="a558b-102">SetAssemblyFile2 方法</span><span class="sxs-lookup"><span data-stu-id="a558b-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="a558b-103">为新的程序集设置和选项的名称。</span><span class="sxs-lookup"><span data-stu-id="a558b-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="a558b-104">生成未绑定的模块时，请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="a558b-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a558b-105">语法</span><span class="sxs-lookup"><span data-stu-id="a558b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a558b-106">参数</span><span class="sxs-lookup"><span data-stu-id="a558b-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="a558b-107">清单文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a558b-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="a558b-108">此文件的[IMetaDataEmit2 接口](../metadata/imetadataemit2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="a558b-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="a558b-109">[AssemblyFlags 枚举](../metadata/assemblyflags-enumeration.md)表示的选项。</span><span class="sxs-lookup"><span data-stu-id="a558b-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="a558b-110">接收正在构造的程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a558b-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a558b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="a558b-111">Return Value</span></span>  
 <span data-ttu-id="a558b-112">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="a558b-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a558b-113">要求</span><span class="sxs-lookup"><span data-stu-id="a558b-113">Requirements</span></span>  
 <span data-ttu-id="a558b-114">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="a558b-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a558b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a558b-115">See also</span></span>

- [<span data-ttu-id="a558b-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="a558b-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a558b-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="a558b-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a558b-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="a558b-118">ALink API</span></span>](index.md)
