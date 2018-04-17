---
title: 封送处理字符串
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
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
ms.workload:
- dotnet
ms.openlocfilehash: adcdf55f3e33a48c4fd10ea243bb0ce3497f522f
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="marshaling-strings"></a><span data-ttu-id="24655-102">封送处理字符串</span><span class="sxs-lookup"><span data-stu-id="24655-102">Marshaling Strings</span></span>
<span data-ttu-id="24655-103">平台调用复制字符串参数，根据需要将其从 .NET Framework 格式 (Unicode) 转换为非托管格式 (ANSI)。</span><span class="sxs-lookup"><span data-stu-id="24655-103">Platform invoke copies string parameters, converting them from the .NET Framework format (Unicode) to the unmanaged format (ANSI), if needed.</span></span> <span data-ttu-id="24655-104">由于托管的字符串不可变，在函数返回时，平台调用并不将它们从非托管内存复制回托管内存。</span><span class="sxs-lookup"><span data-stu-id="24655-104">Because managed strings are immutable, platform invoke does not copy them back from unmanaged memory to managed memory when the function returns.</span></span>  
  
 <span data-ttu-id="24655-105">下表列出了字符串的封送处理选项，描述了它们的用法，并提供了指向相应 .NET Framework 示例的链接。</span><span class="sxs-lookup"><span data-stu-id="24655-105">The following table lists marshaling options for strings, describes their usage, and provides a link to the corresponding .NET Framework sample.</span></span>  
  
|<span data-ttu-id="24655-106">String</span><span class="sxs-lookup"><span data-stu-id="24655-106">String</span></span>|<span data-ttu-id="24655-107">描述</span><span class="sxs-lookup"><span data-stu-id="24655-107">Description</span></span>|<span data-ttu-id="24655-108">示例</span><span class="sxs-lookup"><span data-stu-id="24655-108">Sample</span></span>|  
|------------|-----------------|------------|  
|<span data-ttu-id="24655-109">按值。</span><span class="sxs-lookup"><span data-stu-id="24655-109">By value.</span></span>|<span data-ttu-id="24655-110">将字符串作为 In 参数传递。</span><span class="sxs-lookup"><span data-stu-id="24655-110">Passes strings as In parameters.</span></span>|[<span data-ttu-id="24655-111">MsgBox</span><span class="sxs-lookup"><span data-stu-id="24655-111">MsgBox</span></span>](msgbox-sample.md)|  
|<span data-ttu-id="24655-112">作为结果。</span><span class="sxs-lookup"><span data-stu-id="24655-112">As result.</span></span>|<span data-ttu-id="24655-113">从非托管代码返回字符串。</span><span class="sxs-lookup"><span data-stu-id="24655-113">Returns strings from unmanaged code.</span></span>|<span data-ttu-id="24655-114">[字符串](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24655-114">[Strings](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span></span>|  
|<span data-ttu-id="24655-115">按引用。</span><span class="sxs-lookup"><span data-stu-id="24655-115">By reference.</span></span>|<span data-ttu-id="24655-116">使用 <xref:System.Text.StringBuilder> 将字符串作为 In/Out 参数传递。</span><span class="sxs-lookup"><span data-stu-id="24655-116">Passes strings as In/Out parameters using <xref:System.Text.StringBuilder>.</span></span>|<span data-ttu-id="24655-117">[缓冲区](https://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24655-117">[Buffers](https://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5(v=vs.100))</span></span>|  
|<span data-ttu-id="24655-118">结构中按值。</span><span class="sxs-lookup"><span data-stu-id="24655-118">In a structure by value.</span></span>|<span data-ttu-id="24655-119">在作为 In 参数的结构中传递字符串。</span><span class="sxs-lookup"><span data-stu-id="24655-119">Passes strings in a structure that is an In parameter.</span></span>|<span data-ttu-id="24655-120">[结构](https://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24655-120">[Structs](https://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e(v=vs.100))</span></span>|  
|<span data-ttu-id="24655-121">结构中按引用 (char\*)。</span><span class="sxs-lookup"><span data-stu-id="24655-121">In a structure by reference **(char\*)**.</span></span>|<span data-ttu-id="24655-122">在作为 In/Out 参数的结构中传递字符串。</span><span class="sxs-lookup"><span data-stu-id="24655-122">Passes strings in a structure that is an In/Out parameter.</span></span> <span data-ttu-id="24655-123">非托管函数需要指向字符缓冲区的指针，并且该缓冲区大小是结构的成员。</span><span class="sxs-lookup"><span data-stu-id="24655-123">The unmanaged function expects a pointer to a character buffer and the buffer size is a member of the structure.</span></span>|<span data-ttu-id="24655-124">[字符串](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24655-124">[Strings](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span></span>|  
|<span data-ttu-id="24655-125">结构中按引用 (char[])。</span><span class="sxs-lookup"><span data-stu-id="24655-125">In a structure by reference **(char[])**.</span></span>|<span data-ttu-id="24655-126">在作为 In/Out 参数的结构中传递字符串。</span><span class="sxs-lookup"><span data-stu-id="24655-126">Passes strings in a structure that is an In/Out parameter.</span></span> <span data-ttu-id="24655-127">非托管函数需要嵌入字符缓冲区。</span><span class="sxs-lookup"><span data-stu-id="24655-127">The unmanaged function expects an embedded character buffer.</span></span>|<span data-ttu-id="24655-128">[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24655-128">[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))</span></span>|  
|<span data-ttu-id="24655-129">类中按值 (char\*)。</span><span class="sxs-lookup"><span data-stu-id="24655-129">In a class by value **(char\*)**.</span></span>|<span data-ttu-id="24655-130">在类（类是 In/Out 参数）中传递字符串。</span><span class="sxs-lookup"><span data-stu-id="24655-130">Passes strings in a class (a class is an In/Out parameter).</span></span> <span data-ttu-id="24655-131">非托管函数需要指向字符缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="24655-131">The unmanaged function expects a pointer to a character buffer.</span></span>|<span data-ttu-id="24655-132">[OpenFileDlg](https://msdn.microsoft.com/library/b7dea792-cb92-4baf-ac7b-6a24803e6c75(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24655-132">[OpenFileDlg](https://msdn.microsoft.com/library/b7dea792-cb92-4baf-ac7b-6a24803e6c75(v=vs.100))</span></span>|  
|<span data-ttu-id="24655-133">类中按值 (char[])。</span><span class="sxs-lookup"><span data-stu-id="24655-133">In a class by value **(char[])**.</span></span>|<span data-ttu-id="24655-134">在类（类是 In/Out 参数）中传递字符串。</span><span class="sxs-lookup"><span data-stu-id="24655-134">Passes strings in a class (a class is an In/Out parameter).</span></span> <span data-ttu-id="24655-135">非托管函数需要嵌入字符缓冲区。</span><span class="sxs-lookup"><span data-stu-id="24655-135">The unmanaged function expects an embedded character buffer.</span></span>|<span data-ttu-id="24655-136">[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24655-136">[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))</span></span>|  
|<span data-ttu-id="24655-137">作为字符串数组按值。</span><span class="sxs-lookup"><span data-stu-id="24655-137">As an array of strings by value.</span></span>|<span data-ttu-id="24655-138">创建按值传递的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="24655-138">Creates an array of strings that is passed by value.</span></span>|[<span data-ttu-id="24655-139">数组</span><span class="sxs-lookup"><span data-stu-id="24655-139">Arrays</span></span>](marshaling-different-types-of-arrays.md)|  
|<span data-ttu-id="24655-140">作为包含字符串的结构数组按值。</span><span class="sxs-lookup"><span data-stu-id="24655-140">As an array of structures that contain strings by value.</span></span>|<span data-ttu-id="24655-141">创建包含字符串的结构数组，且该数组是按值传递的。</span><span class="sxs-lookup"><span data-stu-id="24655-141">Creates an array of structures that contain strings and the array is passed by value.</span></span>|[<span data-ttu-id="24655-142">数组</span><span class="sxs-lookup"><span data-stu-id="24655-142">Arrays</span></span>](marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a><span data-ttu-id="24655-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24655-143">See Also</span></span>  
 [<span data-ttu-id="24655-144">用平台调用封送数据</span><span class="sxs-lookup"><span data-stu-id="24655-144">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="24655-145">[平台调用数据类型](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24655-145">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>  
 [<span data-ttu-id="24655-146">封送类、结构和联合</span><span class="sxs-lookup"><span data-stu-id="24655-146">Marshaling Classes, Structures, and Unions</span></span>](marshaling-classes-structures-and-unions.md)  
 <span data-ttu-id="24655-147">[封送类型数组](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24655-147">[Marshaling Arrays of Types](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))</span></span>  
 <span data-ttu-id="24655-148">[其他封送处理示例](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24655-148">[Miscellaneous Marshaling Samples](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span></span>
