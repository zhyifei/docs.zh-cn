---
title: "隔离的类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- storing data using isolated storage, accessing isolated storage
- storing data using isolated storage, isolation types
- authentication [.NET Framework], isolated storage
- assemblies [.NET Framework], identity
- isolated storage, accessing
- data storage using isolated storage, isolation types
- data storage using isolated storage, accessing isolated storage
- domain identity
- isolated storage, types
- user authentication, isolated storage
ms.assetid: 14812988-473f-44ae-b75f-fd5c2f21fb7b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6b07c090a381925f5330a820214126a121d3790b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-isolation"></a><span data-ttu-id="6f851-102">隔离的类型</span><span class="sxs-lookup"><span data-stu-id="6f851-102">Types of Isolation</span></span>
<span data-ttu-id="6f851-103">访问独立存储始终仅限于创建它的用户。</span><span class="sxs-lookup"><span data-stu-id="6f851-103">Access to isolated storage is always restricted to the user who created it.</span></span> <span data-ttu-id="6f851-104">若要实现这种类型的隔离，公共语言运行时使用的相同的概念是用户标识的操作系统能够识别，这是与时打开的存储，代码为运行的进程关联的标识。</span><span class="sxs-lookup"><span data-stu-id="6f851-104">To implement this type of isolation, the common language runtime uses the same notion of user identity that the operating system recognizes, which is the identity associated with the process in which the code is running when the store is opened.</span></span> <span data-ttu-id="6f851-105">此标识的身份验证的用户标识，但模拟可能会导致要动态更改的当前用户的标识。</span><span class="sxs-lookup"><span data-stu-id="6f851-105">This identity is an authenticated user identity, but impersonation can cause the identity of the current user to change dynamically.</span></span>  
  
 <span data-ttu-id="6f851-106">访问独立存储也是根据与应用程序的域和程序集，或单独的程序集关联的标识受限制的。</span><span class="sxs-lookup"><span data-stu-id="6f851-106">Access to isolated storage is also restricted according to the identity associated with the application's domain and assembly, or with the assembly alone.</span></span> <span data-ttu-id="6f851-107">运行时通过以下方式获得这些标识：</span><span class="sxs-lookup"><span data-stu-id="6f851-107">The runtime obtains these identities in the following ways:</span></span>  
  
-   <span data-ttu-id="6f851-108">域标识表示应用程序，这对于 web 应用程序可能是完整的 URL 的证据。</span><span class="sxs-lookup"><span data-stu-id="6f851-108">Domain identity represents the evidence of the application, which in the case of a web application might be the full URL.</span></span> <span data-ttu-id="6f851-109">对于命令行程序托管代码中，域标识可能基于应用程序目录路径。</span><span class="sxs-lookup"><span data-stu-id="6f851-109">For shell-hosted code, the domain identity might be based on the application directory path.</span></span> <span data-ttu-id="6f851-110">例如，如果从路径 C:\Office\MyApp.exe 运行可执行文件，则域标识将 C:\Office\MyApp.exe。</span><span class="sxs-lookup"><span data-stu-id="6f851-110">For example, if the executable runs from the path C:\Office\MyApp.exe, the domain identity would be C:\Office\MyApp.exe.</span></span>  
  
-   <span data-ttu-id="6f851-111">程序集标识是程序集的证据。</span><span class="sxs-lookup"><span data-stu-id="6f851-111">Assembly identity is the evidence of the assembly.</span></span> <span data-ttu-id="6f851-112">这可能来自于加密的数字签名，它可以是程序集的[强名称](../../../docs/framework/app-domains/strong-named-assemblies.md)，该程序集，或者其 URL 标识的软件发布者。</span><span class="sxs-lookup"><span data-stu-id="6f851-112">This might come from a cryptographic digital signature, which can be the assembly's [strong name](../../../docs/framework/app-domains/strong-named-assemblies.md), the software publisher of the assembly, or its URL identity.</span></span> <span data-ttu-id="6f851-113">如果程序集具有强名称和软件发布者标识，则使用软件发布者标识。</span><span class="sxs-lookup"><span data-stu-id="6f851-113">If an assembly has both a strong name and a software publisher identity, then the software publisher identity is used.</span></span> <span data-ttu-id="6f851-114">如果程序集来自 Internet，并且是无符号，则使用的 URL 标识。</span><span class="sxs-lookup"><span data-stu-id="6f851-114">If the assembly comes from the Internet and is unsigned, the URL identity is used.</span></span> <span data-ttu-id="6f851-115">有关程序集和强名称的详细信息，请参阅[使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="6f851-115">For more information about assemblies and strong names, see [Programming with Assemblies](../../../docs/framework/app-domains/programming-with-assemblies.md).</span></span>  
  
-   <span data-ttu-id="6f851-116">与用户拥有漫游用户配置文件一起移动漫游存储区。</span><span class="sxs-lookup"><span data-stu-id="6f851-116">Roaming stores move with a user that has a roaming user profile.</span></span> <span data-ttu-id="6f851-117">文件写入到网络目录和下载到的任何计算机在用户登录到。</span><span class="sxs-lookup"><span data-stu-id="6f851-117">Files are written to a network directory and are downloaded to any computer the user logs into.</span></span> <span data-ttu-id="6f851-118">有关漫游用户配置文件的详细信息，请参阅<xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="6f851-118">For more information about roaming user profiles, see <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="6f851-119">通过组合的用户、 域和程序集标识的概念，独立的存储可通过以下方式，其中每个有其自己的使用方案隔离数据：</span><span class="sxs-lookup"><span data-stu-id="6f851-119">By combining the concepts of user, domain, and assembly identity, isolated storage can isolate data in the following ways, each of which has its own usage scenarios:</span></span>  
  
-   [<span data-ttu-id="6f851-120">按用户和程序集隔离</span><span class="sxs-lookup"><span data-stu-id="6f851-120">Isolation by user and assembly</span></span>](#UserAssembly)  
  
-   [<span data-ttu-id="6f851-121">按用户、 域和程序集隔离</span><span class="sxs-lookup"><span data-stu-id="6f851-121">Isolation by user, domain, and assembly</span></span>](#UserDomainAssembly)  
  
 <span data-ttu-id="6f851-122">这些隔离任一可以结合漫游用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="6f851-122">Either of these isolations can be combined with a roaming user profile.</span></span> <span data-ttu-id="6f851-123">有关详细信息，请参阅明[独立存储和漫游](#Roaming)。</span><span class="sxs-lookup"><span data-stu-id="6f851-123">For more information, see the section [Isolated Storage and Roaming](#Roaming).</span></span>  
  
 <span data-ttu-id="6f851-124">下图演示了如何将存储隔离在不同的作用域中。</span><span class="sxs-lookup"><span data-stu-id="6f851-124">The following illustration demonstrates how stores are isolated in different scopes.</span></span>  
  
 <span data-ttu-id="6f851-125">![按用户和程序集隔离](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")</span><span class="sxs-lookup"><span data-stu-id="6f851-125">![Isolation by user and assembly](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")</span></span>  
<span data-ttu-id="6f851-126">独立存储的类型</span><span class="sxs-lookup"><span data-stu-id="6f851-126">Types of isolated storage</span></span>  
  
 <span data-ttu-id="6f851-127">请注意，除了漫游存储区，独立的存储始终隐式按隔离计算机因为它使用给定计算机本地存储设施。</span><span class="sxs-lookup"><span data-stu-id="6f851-127">Note that except for roaming stores, isolated storage is always implicitly isolated by computer because it uses the storage facilities that are local to a given computer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f851-128">独立存储不适用于 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用。</span><span class="sxs-lookup"><span data-stu-id="6f851-128">Isolated storage is not available for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="6f851-129">相反，使用 `Windows.Storage` API 中包含的 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 命名空间中的应用程序数据类来存储本地数据和文件。</span><span class="sxs-lookup"><span data-stu-id="6f851-129">Instead, use the application data classes in the `Windows.Storage` namespaces included in the [!INCLUDE[wrt](../../../includes/wrt-md.md)] API to store local data and files.</span></span> <span data-ttu-id="6f851-130">有关详细信息，请参阅 Windows 开发人员中心的 [应用程序数据](http://go.microsoft.com/fwlink/?LinkId=229175) 。</span><span class="sxs-lookup"><span data-stu-id="6f851-130">For more information, see [Application data](http://go.microsoft.com/fwlink/?LinkId=229175) in the Windows Dev Center.</span></span>  
  
<a name="UserAssembly"></a>   
## <a name="isolation-by-user-and-assembly"></a><span data-ttu-id="6f851-131">按用户和程序集隔离</span><span class="sxs-lookup"><span data-stu-id="6f851-131">Isolation by User and Assembly</span></span>  
 <span data-ttu-id="6f851-132">如果使用的数据的程序集存储需求，可从任何应用程序的域，按用户和程序集隔离适合。</span><span class="sxs-lookup"><span data-stu-id="6f851-132">When the assembly that uses the data store needs to be accessible from any application's domain, isolation by user and assembly is appropriate.</span></span> <span data-ttu-id="6f851-133">通常情况下，在此情况下，独立的存储用于存储应用跨多个应用程序并不依赖于任何特定的应用程序，如用户的名称或许可证信息的数据。</span><span class="sxs-lookup"><span data-stu-id="6f851-133">Typically, in this situation, isolated storage is used to store data that applies across multiple applications and is not tied to any particular application, such as the user's name or license information.</span></span> <span data-ttu-id="6f851-134">若要访问按用户和程序集隔离的存储，代码必须是受信任应用程序之间传输信息。</span><span class="sxs-lookup"><span data-stu-id="6f851-134">To access storage isolated by user and assembly, code must be trusted to transfer information between applications.</span></span> <span data-ttu-id="6f851-135">通常情况下，在 intranet 上但不是能在 Internet 允许按用户和程序集隔离。</span><span class="sxs-lookup"><span data-stu-id="6f851-135">Typically, isolation by user and assembly is allowed on intranets but not on the Internet.</span></span> <span data-ttu-id="6f851-136">调用静态<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType>方法并传入用户和程序集<xref:System.IO.IsolatedStorage.IsolatedStorageScope>返回具有这种隔离的存储。</span><span class="sxs-lookup"><span data-stu-id="6f851-136">Calling the static <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> method and passing in a user and an assembly <xref:System.IO.IsolatedStorage.IsolatedStorageScope> returns storage with this kind of isolation.</span></span>  
  
 <span data-ttu-id="6f851-137">下面的代码示例检索按用户和程序集隔离的存储区。</span><span class="sxs-lookup"><span data-stu-id="6f851-137">The following code example retrieves a store that is isolated by user and assembly.</span></span> <span data-ttu-id="6f851-138">可以通过访问该存储区`isoFile`对象。</span><span class="sxs-lookup"><span data-stu-id="6f851-138">The store can be accessed through the `isoFile` object.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 <span data-ttu-id="6f851-139">使用证据参数示例，请参阅<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>。</span><span class="sxs-lookup"><span data-stu-id="6f851-139">For an example that uses the evidence parameters, see <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.</span></span>  
  
 <span data-ttu-id="6f851-140"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>方法可作为快捷方式，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="6f851-140">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> method is available as a shortcut, as shown in the following code example.</span></span> <span data-ttu-id="6f851-141">此快捷方式不能用于打开能够漫游; 的存储使用<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>这种情况下。</span><span class="sxs-lookup"><span data-stu-id="6f851-141">This shortcut cannot be used to open stores that are capable of roaming; use <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> in such cases.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## <a name="isolation-by-user-domain-and-assembly"></a><span data-ttu-id="6f851-142">按用户、域和程序集隔离</span><span class="sxs-lookup"><span data-stu-id="6f851-142">Isolation by User, Domain, and Assembly</span></span>  
 <span data-ttu-id="6f851-143">如果你的应用程序使用第三方程序集，需要专用数据存储，你可以使用独立的存储来存储的专用数据。</span><span class="sxs-lookup"><span data-stu-id="6f851-143">If your application uses a third-party assembly that requires a private data store, you can use isolated storage to store the private data.</span></span> <span data-ttu-id="6f851-144">按用户、 域和程序集隔离可确保只有给定程序集中的代码可以访问数据，并仅当程序集使用的应用程序时创建程序集的应用商店中，正在运行且仅当的用户为其创建存储在运行时 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6f851-144">Isolation by user, domain, and assembly ensures that only code in a given assembly can access the data, and only when the assembly is used by the application that was running when the assembly created the store, and only when the user for whom the store was created runs the application.</span></span> <span data-ttu-id="6f851-145">按用户、 域和程序集隔离保留泄漏到其他应用程序的数据的第三方程序集。</span><span class="sxs-lookup"><span data-stu-id="6f851-145">Isolation by user, domain, and assembly keeps the third-party assembly from leaking data to other applications.</span></span> <span data-ttu-id="6f851-146">如果你知道你想要使用独立的存储，但不确定哪种类型的隔离使用，此隔离类型应为默认选择。</span><span class="sxs-lookup"><span data-stu-id="6f851-146">This isolation type should be your default choice if you know that you want to use isolated storage but are not sure which type of isolation to use.</span></span> <span data-ttu-id="6f851-147">调用静态<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>方法<xref:System.IO.IsolatedStorage.IsolatedStorageFile>并传入用户、 域和程序集<xref:System.IO.IsolatedStorage.IsolatedStorageScope>返回具有这种隔离的存储。</span><span class="sxs-lookup"><span data-stu-id="6f851-147">Calling the static <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method of <xref:System.IO.IsolatedStorage.IsolatedStorageFile> and passing in a user, domain, and assembly <xref:System.IO.IsolatedStorage.IsolatedStorageScope> returns storage with this kind of isolation.</span></span>  
  
 <span data-ttu-id="6f851-148">下面的代码示例检索按用户、 域和程序集隔离的存储区。</span><span class="sxs-lookup"><span data-stu-id="6f851-148">The following code example retrieves a store isolated by user, domain, and assembly.</span></span> <span data-ttu-id="6f851-149">可以通过访问该存储区`isoFile`对象。</span><span class="sxs-lookup"><span data-stu-id="6f851-149">The store can be accessed through the `isoFile` object.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 <span data-ttu-id="6f851-150">另一种方法可作为快捷方式，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="6f851-150">Another method is available as a shortcut, as shown in the following code example.</span></span> <span data-ttu-id="6f851-151">此快捷方式不能用于打开能够漫游; 的存储使用<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>这种情况下。</span><span class="sxs-lookup"><span data-stu-id="6f851-151">This shortcut cannot be used to open stores that are capable of roaming; use <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> in such cases.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## <a name="isolated-storage-and-roaming"></a><span data-ttu-id="6f851-152">独立存储和漫游</span><span class="sxs-lookup"><span data-stu-id="6f851-152">Isolated Storage and Roaming</span></span>  
 <span data-ttu-id="6f851-153">漫游用户配置文件是一种 Windows 功能，使用户能够设置在网络上的标识和使用该标识登录到任何网络计算机，又于所有个性化设置。</span><span class="sxs-lookup"><span data-stu-id="6f851-153">Roaming user profiles are a Windows feature that enables a user to set up an identity on a network and use that identity to log into any network computer, carrying over all personalized settings.</span></span> <span data-ttu-id="6f851-154">使用独立的存储程序集可以指定用户的独立的存储应具有漫游用户配置文件迁移。</span><span class="sxs-lookup"><span data-stu-id="6f851-154">An assembly that uses isolated storage can specify that the user's isolated storage should move with the roaming user profile.</span></span> <span data-ttu-id="6f851-155">漫游可在按用户和程序集隔离或隔离一起按用户、 域和程序集。</span><span class="sxs-lookup"><span data-stu-id="6f851-155">Roaming can be used in conjunction with isolation by user and assembly or with isolation by user, domain, and assembly.</span></span> <span data-ttu-id="6f851-156">如果未使用的漫游的作用域，将不会漫游存储区，即使使用漫游用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="6f851-156">If a roaming scope is not used, stores will not roam even if a roaming user profile is used.</span></span>  
  
 <span data-ttu-id="6f851-157">下面的代码示例检索按用户和程序集隔离的漫游存储区。</span><span class="sxs-lookup"><span data-stu-id="6f851-157">The following code example retrieves a roaming store isolated by user and assembly.</span></span> <span data-ttu-id="6f851-158">可以通过访问该存储区`isoFile`对象。</span><span class="sxs-lookup"><span data-stu-id="6f851-158">The store can be accessed through the `isoFile` object.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 <span data-ttu-id="6f851-159">可以添加域作用域，以创建按用户、 域和应用程序隔离的漫游存储区。</span><span class="sxs-lookup"><span data-stu-id="6f851-159">A domain scope can be added to create a roaming store isolated by user, domain, and application.</span></span> <span data-ttu-id="6f851-160">下面的代码示例说明这一点。</span><span class="sxs-lookup"><span data-stu-id="6f851-160">The following code example demonstrates this.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="6f851-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f851-161">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [<span data-ttu-id="6f851-162">独立存储</span><span class="sxs-lookup"><span data-stu-id="6f851-162">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
