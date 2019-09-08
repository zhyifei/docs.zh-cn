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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76d341aca7c96e5932a1fc155ccaee17ce6585da
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776999"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="7793f-102">SetAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="7793f-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="7793f-103">指定要生成的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="7793f-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="7793f-104">不在生成未绑定的模块时使用。</span><span class="sxs-lookup"><span data-stu-id="7793f-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7793f-105">语法</span><span class="sxs-lookup"><span data-stu-id="7793f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7793f-106">参数</span><span class="sxs-lookup"><span data-stu-id="7793f-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="7793f-107">清单文件的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="7793f-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="7793f-108">指向[IMetaDataEmit 接口](../metadata/imetadataemit-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="7793f-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="7793f-109">[AssemblyFlags 枚举](../metadata/assemblyflags-enumeration.md)中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="7793f-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="7793f-110">指向生成的程序集的 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="7793f-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7793f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="7793f-111">Return Value</span></span>  
 <span data-ttu-id="7793f-112">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="7793f-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7793f-113">要求</span><span class="sxs-lookup"><span data-stu-id="7793f-113">Requirements</span></span>  
 <span data-ttu-id="7793f-114">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="7793f-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7793f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7793f-115">See also</span></span>

- [<span data-ttu-id="7793f-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="7793f-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7793f-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="7793f-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7793f-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="7793f-118">ALink API</span></span>](index.md)
