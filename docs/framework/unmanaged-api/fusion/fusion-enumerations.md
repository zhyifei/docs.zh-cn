---
title: 合成枚举
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged enumerations [.NET Framework], fusion
- fusion enumerations [.NET Framework]
- enumerations [.NET Framework fusion]
ms.assetid: 5817b4bc-b0ba-4b2f-a11c-a03dd8cb8f84
ms.openlocfilehash: 9a030d1f0ec6cc4fd7ca526574caa4c281e2573e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108508"
---
# <a name="fusion-enumerations"></a><span data-ttu-id="4b6a2-102">合成枚举</span><span class="sxs-lookup"><span data-stu-id="4b6a2-102">Fusion Enumerations</span></span>
<span data-ttu-id="4b6a2-103">本部分介绍了合成 API 使用的非托管枚举。</span><span class="sxs-lookup"><span data-stu-id="4b6a2-103">This section describes the unmanaged enumerations that the fusion API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b6a2-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="4b6a2-104">In This Section</span></span>  
 [<span data-ttu-id="4b6a2-105">ASM_CACHE_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="4b6a2-105">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)  
 <span data-ttu-id="4b6a2-106">指示由[IAssemblyCacheItem](iassemblycacheitem-interface.md)在全局程序集缓存中表示的程序集的源。</span><span class="sxs-lookup"><span data-stu-id="4b6a2-106">Indicates the source of an assembly represented by [IAssemblyCacheItem](iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="4b6a2-107">ASM_CMP_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="4b6a2-107">ASM_CMP_FLAGS Enumeration</span></span>](asm-cmp-flags-enumeration.md)  
 <span data-ttu-id="4b6a2-108">指示由[IAssemblyName：： IsEqual](iassemblyname-isequal-method.md)方法进行比较的两个程序集的版本、生成、区域性、签名等。</span><span class="sxs-lookup"><span data-stu-id="4b6a2-108">Indicates the version, build, culture, signature, and so on, of two assemblies to be compared by the [IAssemblyName::IsEqual](iassemblyname-isequal-method.md) method.</span></span>  
  
 [<span data-ttu-id="4b6a2-109">ASM_DISPLAY_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="4b6a2-109">ASM_DISPLAY_FLAGS Enumeration</span></span>](asm-display-flags-enumeration.md)  
 <span data-ttu-id="4b6a2-110">指示程序集的版本、生成、区域性、签名等，其显示名称将由[IAssemblyName：： GetDisplayName](iassemblyname-getdisplayname-method.md)方法检索。</span><span class="sxs-lookup"><span data-stu-id="4b6a2-110">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](iassemblyname-getdisplayname-method.md) method.</span></span>  
  
 [<span data-ttu-id="4b6a2-111">ASM_NAME 枚举</span><span class="sxs-lookup"><span data-stu-id="4b6a2-111">ASM_NAME Enumeration</span></span>](asm-name-enumeration.md)  
 <span data-ttu-id="4b6a2-112">指示程序集的版本、生成、区域性、签名等，其属性将由[IAssemblyName](iassemblyname-interface.md)方法检索或设置。</span><span class="sxs-lookup"><span data-stu-id="4b6a2-112">Indicates the version, build, culture, signature, and so on, of the assembly whose properties will be retrieved or set by [IAssemblyName](iassemblyname-interface.md) methods.</span></span>  
  
 [<span data-ttu-id="4b6a2-113">AssemblyComparisonResult 枚举</span><span class="sxs-lookup"><span data-stu-id="4b6a2-113">AssemblyComparisonResult Enumeration</span></span>](assemblycomparisonresult-enumeration.md)  
 <span data-ttu-id="4b6a2-114">指示由[CompareAssemblyIdentity](compareassemblyidentity-function.md)函数确定的两个程序集标识的等效性。</span><span class="sxs-lookup"><span data-stu-id="4b6a2-114">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
 [<span data-ttu-id="4b6a2-115">CREATE_ASM_NAME_OBJ_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="4b6a2-115">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>](create-asm-name-obj-flags-enumeration.md)  
 <span data-ttu-id="4b6a2-116">指定由[CreateAssemblyNameObject](createassemblynameobject-function.md)函数构造的 `IAssemblyName` 对象的特性。</span><span class="sxs-lookup"><span data-stu-id="4b6a2-116">Specifies the attributes of an `IAssemblyName` object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4b6a2-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="4b6a2-117">Related Sections</span></span>  
 [<span data-ttu-id="4b6a2-118">合成接口</span><span class="sxs-lookup"><span data-stu-id="4b6a2-118">Fusion Interfaces</span></span>](fusion-interfaces.md)  
  
 [<span data-ttu-id="4b6a2-119">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="4b6a2-119">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)  
  
 [<span data-ttu-id="4b6a2-120">合成结构</span><span class="sxs-lookup"><span data-stu-id="4b6a2-120">Fusion Structures</span></span>](fusion-structures.md)
