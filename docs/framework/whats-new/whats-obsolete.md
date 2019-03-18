---
title: .NET Framework 类库中过时的内容
ms.custom: updateeachrelease
ms.date: 04/10/2018
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 416192d431234b2ce7d6e53f21803f88371a6805
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2019
ms.locfileid: "58018742"
---
# <a name="whats-obsolete-in-the-net-framework-class-library"></a><span data-ttu-id="1b303-102">.NET Framework 类库中过时的内容</span><span class="sxs-lookup"><span data-stu-id="1b303-102">What's Obsolete in the .NET Framework Class Library</span></span>
<span data-ttu-id="1b303-103">.NET Framework 随时间推移而变化。</span><span class="sxs-lookup"><span data-stu-id="1b303-103">The .NET Framework changes over time.</span></span> <span data-ttu-id="1b303-104">每个新版本都添加了提供新功能的新类型和类型成员。</span><span class="sxs-lookup"><span data-stu-id="1b303-104">Each new version adds new types and type members that provide new functionality.</span></span> <span data-ttu-id="1b303-105">现有类型和成员也会随着时间推移而变化。</span><span class="sxs-lookup"><span data-stu-id="1b303-105">Existing types and their members also change over time.</span></span> <span data-ttu-id="1b303-106">例如，某些类型变得不太重要，因为它们支持的技术由新技术所替代，而某些方法由更方便或功能更全面的方法所取代。</span><span class="sxs-lookup"><span data-stu-id="1b303-106">For example, some types become less important as the technology they support is replaced by a new technology, and some methods are superseded by newer methods that are either more convenient or more full-featured.</span></span>  
  
 <span data-ttu-id="1b303-107">.NET Framework 和公共语言运行时会努力支持向后兼容（允许使用一个版本的 .NET Framework 开发的应用程序在下一版本的 .NET Framework 上运行）。</span><span class="sxs-lookup"><span data-stu-id="1b303-107">The .NET Framework and the common language runtime strive to support backward compatibility (allowing applications that were developed with one version of the .NET Framework to run on the next version of the .NET Framework).</span></span> <span data-ttu-id="1b303-108">这便难以仅仅删除类型或类型成员。</span><span class="sxs-lookup"><span data-stu-id="1b303-108">This makes it difficult to simply remove a type or a type member.</span></span> <span data-ttu-id="1b303-109">相反，.NET Framework 通过将类型或类型成员标记为已过时或已弃用，来指示应不再使用它。</span><span class="sxs-lookup"><span data-stu-id="1b303-109">Instead, the .NET Framework indicates that a type or a type member should no longer be used by marking it as obsolete or deprecated.</span></span> <span data-ttu-id="1b303-110">弃用某个类型或成员涉及对它进行标记，以便开发人员知道它将消失，从而有时间来响应其删除。</span><span class="sxs-lookup"><span data-stu-id="1b303-110">Deprecating a type or a member involves marking it so that developers are aware it will go away and have time to respond to its removal.</span></span> <span data-ttu-id="1b303-111">但是，使用该类型或成员的现有代码会继续在新版本的 .NET Framework 中运行。</span><span class="sxs-lookup"><span data-stu-id="1b303-111">However, existing code that uses the type or member continues to run in the new version of the .NET Framework.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b303-112">术语 *“已过时”* 和 *“已弃用”* 在应用于 .NET Framework 的类型和成员时含义相同。</span><span class="sxs-lookup"><span data-stu-id="1b303-112">The terms *obsolete* and *deprecated* have the same meaning when applied to the types and members of the .NET Framework.</span></span>  
  
## <a name="the-obsoleteattribute-attribute"></a><span data-ttu-id="1b303-113">ObsoleteAttribute 特性</span><span class="sxs-lookup"><span data-stu-id="1b303-113">The ObsoleteAttribute Attribute</span></span>  
 <span data-ttu-id="1b303-114">.NET Framework 通过使用 <xref:System.ObsoleteAttribute> 特性标记类型或类型成员来指示它已过时。</span><span class="sxs-lookup"><span data-stu-id="1b303-114">The .NET Framework indicates that a type or type member is obsolete by marking it with the <xref:System.ObsoleteAttribute> attribute.</span></span> <span data-ttu-id="1b303-115">将该特性应用于某个类型或成员指示该类型或成员会在将来某个版本的 .NET Framework 中删除，但不会破坏使用该成员的已编译代码。</span><span class="sxs-lookup"><span data-stu-id="1b303-115">Applying the attribute to a type or member indicates that type or member will be removed in some future version of the .NET Framework without breaking compiled code that uses that member.</span></span>  
  
 <span data-ttu-id="1b303-116">除了指示类型或类型成员已过时之外，<xref:System.ObsoleteAttribute> 还定义编译器如何处理包含该类型或成员的源代码。</span><span class="sxs-lookup"><span data-stu-id="1b303-116">In addition to indicating that a type or a type member is obsolete, <xref:System.ObsoleteAttribute> defines how the compiler handles source code that includes that type or member.</span></span> <span data-ttu-id="1b303-117">编译器可以编译代码但发出警告消息，也可以将该类型或成员的使用视为错误。</span><span class="sxs-lookup"><span data-stu-id="1b303-117">The compiler can compile the code but emit a warning message, or it can treat the use of the type or member as an error.</span></span> <span data-ttu-id="1b303-118">在第一种情况下，代码可以成功编译，但警告消息会指示类型或成员已过时。</span><span class="sxs-lookup"><span data-stu-id="1b303-118">In the first case, the code can successfully compile, but a warning message indicates that the type or member is obsolete.</span></span> <span data-ttu-id="1b303-119">在第二种情况下，编译会失败。</span><span class="sxs-lookup"><span data-stu-id="1b303-119">In the second case, compilation fails.</span></span>  
  
 <span data-ttu-id="1b303-120">即使编译生成错误而不是警告消息，<xref:System.ObsoleteAttribute> 也不会影响运行时行为。</span><span class="sxs-lookup"><span data-stu-id="1b303-120">Even if compilation produces an error instead of a warning message, <xref:System.ObsoleteAttribute> does not affect run-time behavior.</span></span> <span data-ttu-id="1b303-121">也就是说，使用该类型或成员并且已成功编译的应用程序会始终成功运行。</span><span class="sxs-lookup"><span data-stu-id="1b303-121">That is, applications that use the type or member and that have compiled successfully will always run successfully.</span></span> <span data-ttu-id="1b303-122">只有重新编译使用该类型或成员的应用程序的尝试会失败。</span><span class="sxs-lookup"><span data-stu-id="1b303-122">Only the attempt to recompile an application that uses the type or member fails.</span></span>  
  
## <a name="how-to-handle-obsolete-types-and-members"></a><span data-ttu-id="1b303-123">如何处理已过时的类型和成员</span><span class="sxs-lookup"><span data-stu-id="1b303-123">How to Handle Obsolete Types and Members</span></span>  
 <span data-ttu-id="1b303-124">升级和重新编译现有代码时，使用会在应用程序中生成编译器警告的已过时类型或成员是完全可以接受的。</span><span class="sxs-lookup"><span data-stu-id="1b303-124">When you upgrade and recompile existing code, using an obsolete type or member that produces a compiler warning in your application is perfectly acceptable.</span></span> <span data-ttu-id="1b303-125">但是，应查看编译器警告消息，以确定是否应更改应用程序代码。</span><span class="sxs-lookup"><span data-stu-id="1b303-125">However, you should review the compiler warning message to determine whether you should change your application code.</span></span> <span data-ttu-id="1b303-126">如果该消息不指向合适的替代方法，则应执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="1b303-126">If the message does not point to a suitable alternative, you should do either of the following:</span></span>  
  
-   <span data-ttu-id="1b303-127">通过删除该类型或成员的使用（如果可能）来更改代码。</span><span class="sxs-lookup"><span data-stu-id="1b303-127">Change your code by removing the use of the type or member, if possible.</span></span>  
  
     <span data-ttu-id="1b303-128">或</span><span class="sxs-lookup"><span data-stu-id="1b303-128">-or-</span></span>  
  
-   <span data-ttu-id="1b303-129">查看有关此技术领域的文档，以确定如何响应弃用情况。</span><span class="sxs-lookup"><span data-stu-id="1b303-129">Review the documentation for this technology area to determine how to respond to the deprecation.</span></span>  
  
 <span data-ttu-id="1b303-130">可以选择不针对更高版本的 .NET Framework 重新编译现有代码。</span><span class="sxs-lookup"><span data-stu-id="1b303-130">You may choose not to recompile existing code against a later version of the .NET Framework.</span></span> <span data-ttu-id="1b303-131">相反，可以指定针对其运行现有已编译代码的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="1b303-131">Instead, you can specify the version of the .NET Framework against which your existing compiled code runs.</span></span> <span data-ttu-id="1b303-132">例如，假设有一个名为 app1.exe 并且针对 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 进行了编译的应用程序，但是希望针对 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="1b303-132">For example, suppose that you have an application named app1.exe that was compiled against the [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)], but you want the application to run against the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="1b303-133">这需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1b303-133">This requires the following steps:</span></span>  
  
1.  <span data-ttu-id="1b303-134">为主可执行文件创建一个配置文件并将它命名为 *appName*.exe.config，其中 *appName* 是应用程序可执行文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1b303-134">Create a configuration file for your main executable and name it *appName*.exe.config, where *appName* is the name of the application executable.</span></span> <span data-ttu-id="1b303-135">对于我们示例中名为 app1.exe 的应用程序，会创建一个名为 app1.exe.config 的配置文件。</span><span class="sxs-lookup"><span data-stu-id="1b303-135">For the application named app1.exe in our example, you would create a configuration file named app1.exe.config.</span></span>  
  
2.  <span data-ttu-id="1b303-136">向该配置文件添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="1b303-136">Add the following to the configuration file.</span></span>  
  
    ```xml  
    <configuration>  
       <startup>   
          <supportedRuntime version="v4.0" />  
       </startup>  
    </configuration>  
    ```  
  
 <span data-ttu-id="1b303-137">下表列出可以分配给 `version` 特性以针对特定 .NET Framework 版本的字符串值。</span><span class="sxs-lookup"><span data-stu-id="1b303-137">The following table lists the string values that you can assign to the `version` attribute to target a specific version of the .NET Framework.</span></span>  
  
|<span data-ttu-id="1b303-138">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="1b303-138">.NET Framework version</span></span>|<span data-ttu-id="1b303-139">`version` 字符串</span><span class="sxs-lookup"><span data-stu-id="1b303-139">`version` string</span></span>|
|-|-|  
|<span data-ttu-id="1b303-140">4.7（包括 4.7.1 和 4.7.2）</span><span class="sxs-lookup"><span data-stu-id="1b303-140">4.7 (including 4.7.1 and 4.7.2)</span></span>|<span data-ttu-id="1b303-141">v4.0</span><span class="sxs-lookup"><span data-stu-id="1b303-141">v4.0</span></span>|  
|<span data-ttu-id="1b303-142">4.6（包括 4.6.1 和 4.6.2）</span><span class="sxs-lookup"><span data-stu-id="1b303-142">4.6 (including 4.6.1 and 4.6.2)</span></span>|<span data-ttu-id="1b303-143">v4.0</span><span class="sxs-lookup"><span data-stu-id="1b303-143">v4.0</span></span>|  
|<span data-ttu-id="1b303-144">4.5（包括 4.5.1 和 4.5.2）</span><span class="sxs-lookup"><span data-stu-id="1b303-144">4.5 (including 4.5.1 and 4.5.2)</span></span>|<span data-ttu-id="1b303-145">v4.0</span><span class="sxs-lookup"><span data-stu-id="1b303-145">v4.0</span></span>|  
|<span data-ttu-id="1b303-146">4</span><span class="sxs-lookup"><span data-stu-id="1b303-146">4</span></span>|<span data-ttu-id="1b303-147">v4.0</span><span class="sxs-lookup"><span data-stu-id="1b303-147">v4.0</span></span>|  
|<span data-ttu-id="1b303-148">3.5</span><span class="sxs-lookup"><span data-stu-id="1b303-148">3.5</span></span>|<span data-ttu-id="1b303-149">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="1b303-149">v2.0.50727</span></span>|  
|<span data-ttu-id="1b303-150">2.0</span><span class="sxs-lookup"><span data-stu-id="1b303-150">2.0</span></span>|<span data-ttu-id="1b303-151">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="1b303-151">v2.0.50727</span></span>|  
|<span data-ttu-id="1b303-152">1.1</span><span class="sxs-lookup"><span data-stu-id="1b303-152">1.1</span></span>|<span data-ttu-id="1b303-153">v1.1.4322</span><span class="sxs-lookup"><span data-stu-id="1b303-153">v1.1.4322</span></span>|  
|<span data-ttu-id="1b303-154">1.0</span><span class="sxs-lookup"><span data-stu-id="1b303-154">1.0</span></span>|<span data-ttu-id="1b303-155">v1.0.3705</span><span class="sxs-lookup"><span data-stu-id="1b303-155">v1.0.3705</span></span>|  
  
## <a name="obsolete-lists-for-the-net-framework-45-and-later-versions"></a><span data-ttu-id="1b303-156">.NET Framework 4.5 和更高版本的过时列表</span><span class="sxs-lookup"><span data-stu-id="1b303-156">Obsolete Lists for the .NET Framework 4.5 and later versions</span></span>  
 [<span data-ttu-id="1b303-157">过时类型</span><span class="sxs-lookup"><span data-stu-id="1b303-157">Obsolete Types</span></span>](obsolete-types.md)  
  
 [<span data-ttu-id="1b303-158">过时成员</span><span class="sxs-lookup"><span data-stu-id="1b303-158">Obsolete Members</span></span>](obsolete-members.md)  
  
## <a name="obsolete-lists-for-previous-versions"></a><span data-ttu-id="1b303-159">以前版本的过时列表</span><span class="sxs-lookup"><span data-stu-id="1b303-159">Obsolete Lists for Previous Versions</span></span>  
 [<span data-ttu-id="1b303-160">.NET Framework 4 中的过时类型</span><span class="sxs-lookup"><span data-stu-id="1b303-160">Obsolete Types in the .NET Framework 4</span></span>](https://go.microsoft.com/fwlink/?LinkId=224224)  
  
 [<span data-ttu-id="1b303-161">.NET Framework 4 中的过时成员</span><span class="sxs-lookup"><span data-stu-id="1b303-161">Obsolete Members in the .NET Framework 4</span></span>](https://go.microsoft.com/fwlink/?LinkId=224227)  
  
 [<span data-ttu-id="1b303-162">.NET Framework 3.5 过时列表</span><span class="sxs-lookup"><span data-stu-id="1b303-162">.NET Framework 3.5 Obsolete List</span></span>](https://go.microsoft.com/fwlink/?LinkId=163710)  
  
 [<span data-ttu-id="1b303-163">.NET Framework 2.0 过时列表</span><span class="sxs-lookup"><span data-stu-id="1b303-163">.NET Framework 2.0 Obsolete List</span></span>](https://go.microsoft.com/fwlink/?LinkID=125264)  
  
## <a name="see-also"></a><span data-ttu-id="1b303-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b303-164">See also</span></span>
- [<span data-ttu-id="1b303-165">\<supportedRuntime> 元素</span><span class="sxs-lookup"><span data-stu-id="1b303-165">\<supportedRuntime> Element</span></span>](../configure-apps/file-schema/startup/supportedruntime-element.md)
