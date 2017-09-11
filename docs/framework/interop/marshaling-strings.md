---
title: "封送处理字符串"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- marshaling, samples
- platform invoke, marshaling data
- data marshaling, strings
- data marshaling, samples
- data marshaling, platform invoke
- marshaling. strings
- marshaling, platform invoke
- sample applications [.NET Framework], marshaling strings
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8d8455d4f1b4dbb463176c06d680b2bd0b1ff9d9
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="marshaling-strings"></a><span data-ttu-id="b1c85-102">封送处理字符串</span><span class="sxs-lookup"><span data-stu-id="b1c85-102">Marshaling Strings</span></span>
<span data-ttu-id="b1c85-103">平台调用复制字符串参数，根据需要将其从 .NET Framework 格式 (Unicode) 转换为非托管格式 (ANSI)。</span><span class="sxs-lookup"><span data-stu-id="b1c85-103">Platform invoke copies string parameters, converting them from the .NET Framework format (Unicode) to the unmanaged format (ANSI), if needed.</span></span> <span data-ttu-id="b1c85-104">由于托管的字符串不可变，在函数返回时，平台调用并不将它们从非托管内存复制回托管内存。</span><span class="sxs-lookup"><span data-stu-id="b1c85-104">Because managed strings are immutable, platform invoke does not copy them back from unmanaged memory to managed memory when the function returns.</span></span>  
  
 <span data-ttu-id="b1c85-105">下表列出了字符串的封送处理选项，描述了它们的用法，并提供了指向相应 .NET Framework 示例的链接。</span><span class="sxs-lookup"><span data-stu-id="b1c85-105">The following table lists marshaling options for strings, describes their usage, and provides a link to the corresponding .NET Framework sample.</span></span>  
  
|<span data-ttu-id="b1c85-106">String</span><span class="sxs-lookup"><span data-stu-id="b1c85-106">String</span></span>|<span data-ttu-id="b1c85-107">描述</span><span class="sxs-lookup"><span data-stu-id="b1c85-107">Description</span></span>|<span data-ttu-id="b1c85-108">示例</span><span class="sxs-lookup"><span data-stu-id="b1c85-108">Sample</span></span>|  
|------------|-----------------|------------|  
|<span data-ttu-id="b1c85-109">按值。</span><span class="sxs-lookup"><span data-stu-id="b1c85-109">By value.</span></span>|<span data-ttu-id="b1c85-110">将字符串作为 In 参数传递。</span><span class="sxs-lookup"><span data-stu-id="b1c85-110">Passes strings as In parameters.</span></span>|[<span data-ttu-id="b1c85-111">MsgBox</span><span class="sxs-lookup"><span data-stu-id="b1c85-111">MsgBox</span></span>](../../../docs/framework/interop/msgbox-sample.md)|  
|<span data-ttu-id="b1c85-112">作为结果。</span><span class="sxs-lookup"><span data-stu-id="b1c85-112">As result.</span></span>|<span data-ttu-id="b1c85-113">从非托管代码返回字符串。</span><span class="sxs-lookup"><span data-stu-id="b1c85-113">Returns strings from unmanaged code.</span></span>|[<span data-ttu-id="b1c85-114">字符串</span><span class="sxs-lookup"><span data-stu-id="b1c85-114">Strings</span></span>](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|<span data-ttu-id="b1c85-115">按引用。</span><span class="sxs-lookup"><span data-stu-id="b1c85-115">By reference.</span></span>|<span data-ttu-id="b1c85-116">使用 <xref:System.Text.StringBuilder> 将字符串作为 In/Out 参数传递。</span><span class="sxs-lookup"><span data-stu-id="b1c85-116">Passes strings as In/Out parameters using <xref:System.Text.StringBuilder>.</span></span>|[<span data-ttu-id="b1c85-117">缓冲区</span><span class="sxs-lookup"><span data-stu-id="b1c85-117">Buffers</span></span>](http://msdn.microsoft.com/en-us/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|<span data-ttu-id="b1c85-118">结构中按值。</span><span class="sxs-lookup"><span data-stu-id="b1c85-118">In a structure by value.</span></span>|<span data-ttu-id="b1c85-119">在作为 In 参数的结构中传递字符串。</span><span class="sxs-lookup"><span data-stu-id="b1c85-119">Passes strings in a structure that is an In parameter.</span></span>|[<span data-ttu-id="b1c85-120">结构</span><span class="sxs-lookup"><span data-stu-id="b1c85-120">Structs</span></span>](http://msdn.microsoft.com/en-us/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|<span data-ttu-id="b1c85-121">结构中按引用 (char\*)。</span><span class="sxs-lookup"><span data-stu-id="b1c85-121">In a structure by reference **(char\*)**.</span></span>|<span data-ttu-id="b1c85-122">在作为 In/Out 参数的结构中传递字符串。</span><span class="sxs-lookup"><span data-stu-id="b1c85-122">Passes strings in a structure that is an In/Out parameter.</span></span> <span data-ttu-id="b1c85-123">非托管函数需要指向字符缓冲区的指针，并且该缓冲区大小是结构的成员。</span><span class="sxs-lookup"><span data-stu-id="b1c85-123">The unmanaged function expects a pointer to a character buffer and the buffer size is a member of the structure.</span></span>|[<span data-ttu-id="b1c85-124">字符串</span><span class="sxs-lookup"><span data-stu-id="b1c85-124">Strings</span></span>](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|<span data-ttu-id="b1c85-125">结构中按引用 (char[])。</span><span class="sxs-lookup"><span data-stu-id="b1c85-125">In a structure by reference **(char[])**.</span></span>|<span data-ttu-id="b1c85-126">在作为 In/Out 参数的结构中传递字符串。</span><span class="sxs-lookup"><span data-stu-id="b1c85-126">Passes strings in a structure that is an In/Out parameter.</span></span> <span data-ttu-id="b1c85-127">非托管函数需要嵌入字符缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b1c85-127">The unmanaged function expects an embedded character buffer.</span></span>|[<span data-ttu-id="b1c85-128">OSInfo</span><span class="sxs-lookup"><span data-stu-id="b1c85-128">OSInfo</span></span>](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|<span data-ttu-id="b1c85-129">类中按值 (char\*)。</span><span class="sxs-lookup"><span data-stu-id="b1c85-129">In a class by value **(char\*)**.</span></span>|<span data-ttu-id="b1c85-130">在类（类是 In/Out 参数）中传递字符串。</span><span class="sxs-lookup"><span data-stu-id="b1c85-130">Passes strings in a class (a class is an In/Out parameter).</span></span> <span data-ttu-id="b1c85-131">非托管函数需要指向字符缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="b1c85-131">The unmanaged function expects a pointer to a character buffer.</span></span>|[<span data-ttu-id="b1c85-132">OpenFileDlg</span><span class="sxs-lookup"><span data-stu-id="b1c85-132">OpenFileDlg</span></span>](http://msdn.microsoft.com/en-us/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|<span data-ttu-id="b1c85-133">类中按值 (char[])。</span><span class="sxs-lookup"><span data-stu-id="b1c85-133">In a class by value **(char[])**.</span></span>|<span data-ttu-id="b1c85-134">在类（类是 In/Out 参数）中传递字符串。</span><span class="sxs-lookup"><span data-stu-id="b1c85-134">Passes strings in a class (a class is an In/Out parameter).</span></span> <span data-ttu-id="b1c85-135">非托管函数需要嵌入字符缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b1c85-135">The unmanaged function expects an embedded character buffer.</span></span>|[<span data-ttu-id="b1c85-136">OSInfo</span><span class="sxs-lookup"><span data-stu-id="b1c85-136">OSInfo</span></span>](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|<span data-ttu-id="b1c85-137">作为字符串数组按值。</span><span class="sxs-lookup"><span data-stu-id="b1c85-137">As an array of strings by value.</span></span>|<span data-ttu-id="b1c85-138">创建按值传递的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="b1c85-138">Creates an array of strings that is passed by value.</span></span>|[<span data-ttu-id="b1c85-139">阵列</span><span class="sxs-lookup"><span data-stu-id="b1c85-139">Arrays</span></span>](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|<span data-ttu-id="b1c85-140">作为包含字符串的结构数组按值。</span><span class="sxs-lookup"><span data-stu-id="b1c85-140">As an array of structures that contain strings by value.</span></span>|<span data-ttu-id="b1c85-141">创建包含字符串的结构数组，且该数组是按值传递的。</span><span class="sxs-lookup"><span data-stu-id="b1c85-141">Creates an array of structures that contain strings and the array is passed by value.</span></span>|[<span data-ttu-id="b1c85-142">阵列</span><span class="sxs-lookup"><span data-stu-id="b1c85-142">Arrays</span></span>](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a><span data-ttu-id="b1c85-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1c85-143">See Also</span></span>  
 <span data-ttu-id="b1c85-144">[使用平台调用封送数据](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md) </span><span class="sxs-lookup"><span data-stu-id="b1c85-144">[Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md) </span></span>  
 <span data-ttu-id="b1c85-145">[平台调用数据类型](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f) </span><span class="sxs-lookup"><span data-stu-id="b1c85-145">[Platform Invoke Data Types](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f) </span></span>  
 <span data-ttu-id="b1c85-146">[封送类、结构和联合](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md) </span><span class="sxs-lookup"><span data-stu-id="b1c85-146">[Marshaling Classes, Structures, and Unions](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md) </span></span>  
 <span data-ttu-id="b1c85-147">[封送类型数组](http://msdn.microsoft.com/en-us/049b1c1b-228f-4445-88ec-91bc7fd4b1e8) </span><span class="sxs-lookup"><span data-stu-id="b1c85-147">[Marshaling Arrays of Types](http://msdn.microsoft.com/en-us/049b1c1b-228f-4445-88ec-91bc7fd4b1e8) </span></span>  
 [<span data-ttu-id="b1c85-148">其他封送处理示例</span><span class="sxs-lookup"><span data-stu-id="b1c85-148">Miscellaneous Marshaling Samples</span></span>](http://msdn.microsoft.com/en-us/a915c948-54e9-4d0f-a525-95a77fd8ed70)

