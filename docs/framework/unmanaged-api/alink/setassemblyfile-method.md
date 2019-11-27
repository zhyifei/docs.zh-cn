---
title: SetAssemblyFile 方法
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 1db4c4ab7e47e223a492e08297ac3cedcb3a27eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445605"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="93f95-102">SetAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="93f95-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="93f95-103">指定要生成的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="93f95-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="93f95-104">不在生成未绑定的模块时使用。</span><span class="sxs-lookup"><span data-stu-id="93f95-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93f95-105">语法</span><span class="sxs-lookup"><span data-stu-id="93f95-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="93f95-106">参数</span><span class="sxs-lookup"><span data-stu-id="93f95-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="93f95-107">清单文件的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="93f95-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="93f95-108">指向[IMetaDataEmit 接口](../metadata/imetadataemit-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="93f95-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="93f95-109">[AssemblyFlags 枚举](../metadata/assemblyflags-enumeration.md)中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="93f95-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="93f95-110">指向生成的程序集的 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="93f95-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93f95-111">返回值</span><span class="sxs-lookup"><span data-stu-id="93f95-111">Return Value</span></span>  
 <span data-ttu-id="93f95-112">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="93f95-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93f95-113">要求</span><span class="sxs-lookup"><span data-stu-id="93f95-113">Requirements</span></span>  
 <span data-ttu-id="93f95-114">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="93f95-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f95-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93f95-115">See also</span></span>

- [<span data-ttu-id="93f95-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="93f95-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="93f95-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="93f95-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="93f95-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="93f95-118">ALink API</span></span>](index.md)
