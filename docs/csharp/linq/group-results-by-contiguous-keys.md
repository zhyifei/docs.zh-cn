---
title: "按连续键对结果进行分组"
description: "如何按连续键对结果进行分组。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ddd028a3aad5186ef6773b32e9f9e8e1cbff95fc
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="e5b99-104">按连续键对结果进行分组</span><span class="sxs-lookup"><span data-stu-id="e5b99-104">Group results by contiguous keys</span></span>

<span data-ttu-id="e5b99-105">下面的示例演示如何将元素分组为表示连续键子序列的区块。</span><span class="sxs-lookup"><span data-stu-id="e5b99-105">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="e5b99-106">例如，假设给定下列键值对的序列：</span><span class="sxs-lookup"><span data-stu-id="e5b99-106">For example, assume that you are given the following sequence of key-value pairs:</span></span>  
  
|<span data-ttu-id="e5b99-107">键</span><span class="sxs-lookup"><span data-stu-id="e5b99-107">Key</span></span>|<span data-ttu-id="e5b99-108">值</span><span class="sxs-lookup"><span data-stu-id="e5b99-108">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="e5b99-109">包含当前请求的 URL 的</span><span class="sxs-lookup"><span data-stu-id="e5b99-109">A</span></span>|<span data-ttu-id="e5b99-110">We</span><span class="sxs-lookup"><span data-stu-id="e5b99-110">We</span></span>|  
|<span data-ttu-id="e5b99-111">包含当前请求的 URL 的</span><span class="sxs-lookup"><span data-stu-id="e5b99-111">A</span></span>|<span data-ttu-id="e5b99-112">think</span><span class="sxs-lookup"><span data-stu-id="e5b99-112">think</span></span>|  
|<span data-ttu-id="e5b99-113">包含当前请求的 URL 的</span><span class="sxs-lookup"><span data-stu-id="e5b99-113">A</span></span>|<span data-ttu-id="e5b99-114">that</span><span class="sxs-lookup"><span data-stu-id="e5b99-114">that</span></span>|  
|<span data-ttu-id="e5b99-115">B</span><span class="sxs-lookup"><span data-stu-id="e5b99-115">B</span></span>|<span data-ttu-id="e5b99-116">Linq</span><span class="sxs-lookup"><span data-stu-id="e5b99-116">Linq</span></span>|  
|<span data-ttu-id="e5b99-117">C</span><span class="sxs-lookup"><span data-stu-id="e5b99-117">C</span></span>|<span data-ttu-id="e5b99-118">is</span><span class="sxs-lookup"><span data-stu-id="e5b99-118">is</span></span>|  
|<span data-ttu-id="e5b99-119">包含当前请求的 URL 的</span><span class="sxs-lookup"><span data-stu-id="e5b99-119">A</span></span>|<span data-ttu-id="e5b99-120">really</span><span class="sxs-lookup"><span data-stu-id="e5b99-120">really</span></span>|  
|<span data-ttu-id="e5b99-121">B</span><span class="sxs-lookup"><span data-stu-id="e5b99-121">B</span></span>|<span data-ttu-id="e5b99-122">cool</span><span class="sxs-lookup"><span data-stu-id="e5b99-122">cool</span></span>|  
|<span data-ttu-id="e5b99-123">B</span><span class="sxs-lookup"><span data-stu-id="e5b99-123">B</span></span>|<span data-ttu-id="e5b99-124">!</span><span class="sxs-lookup"><span data-stu-id="e5b99-124">!</span></span>|  
  
 <span data-ttu-id="e5b99-125">以下组将按此顺序创建：</span><span class="sxs-lookup"><span data-stu-id="e5b99-125">The following groups will be created in this order:</span></span>  
  
1.  <span data-ttu-id="e5b99-126">We, think, that</span><span class="sxs-lookup"><span data-stu-id="e5b99-126">We, think, that</span></span>  
  
2.  <span data-ttu-id="e5b99-127">Linq</span><span class="sxs-lookup"><span data-stu-id="e5b99-127">Linq</span></span>  
  
3.  <span data-ttu-id="e5b99-128">is</span><span class="sxs-lookup"><span data-stu-id="e5b99-128">is</span></span>  
  
4.  <span data-ttu-id="e5b99-129">really</span><span class="sxs-lookup"><span data-stu-id="e5b99-129">really</span></span>  
  
5.  <span data-ttu-id="e5b99-130">cool, !</span><span class="sxs-lookup"><span data-stu-id="e5b99-130">cool, !</span></span>  
  
 <span data-ttu-id="e5b99-131">此解决方案是以扩展方法实现的，该扩展方法是线程安全的，并以流的方式返回其结果。</span><span class="sxs-lookup"><span data-stu-id="e5b99-131">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="e5b99-132">换言之，它在源序列中遍历移动时生成其组。</span><span class="sxs-lookup"><span data-stu-id="e5b99-132">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="e5b99-133">与 `group` 或 `orderby` 运算符不同，它能在所有序列被读取之前开始将组返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="e5b99-133">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>  
  
 <span data-ttu-id="e5b99-134">线程安全通过在循环访问源序列的同时创建每个组或区块的副本来实现，如源代码注释中所述。</span><span class="sxs-lookup"><span data-stu-id="e5b99-134">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="e5b99-135">如果源序列具有大型的连续项序列，则公共语言运行时可能会引发 <xref:System.OutOfMemoryException>。</span><span class="sxs-lookup"><span data-stu-id="e5b99-135">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5b99-136">示例</span><span class="sxs-lookup"><span data-stu-id="e5b99-136">Example</span></span>  
 <span data-ttu-id="e5b99-137">下面的示例演示该扩展方法以及使用它的客户端代码。</span><span class="sxs-lookup"><span data-stu-id="e5b99-137">The following example shows both the extension method and the client code that uses it.</span></span>  
  
 <span data-ttu-id="e5b99-138">[!code-cs[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5b99-138">[!code-cs[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]</span></span>  
  
 <span data-ttu-id="e5b99-139">若要在项目中使用扩展方法，请将 `MyExtensions` 静态类复制到新的或现有源代码文件中，并且如有需要，请为它所在的命名空间添加 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="e5b99-139">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b99-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5b99-140">See also</span></span>  
 [<span data-ttu-id="e5b99-141">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="e5b99-141">LINQ Query Expressions</span></span>](index.md)   
 

