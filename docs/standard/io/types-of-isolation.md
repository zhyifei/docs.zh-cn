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
# <a name="types-of-isolation"></a>隔离的类型
访问独立存储始终仅限于创建它的用户。 若要实现这种类型的隔离，公共语言运行时使用的相同的概念是用户标识的操作系统能够识别，这是与时打开的存储，代码为运行的进程关联的标识。 此标识的身份验证的用户标识，但模拟可能会导致要动态更改的当前用户的标识。  
  
 访问独立存储也是根据与应用程序的域和程序集，或单独的程序集关联的标识受限制的。 运行时通过以下方式获得这些标识：  
  
-   域标识表示应用程序，这对于 web 应用程序可能是完整的 URL 的证据。 对于命令行程序托管代码中，域标识可能基于应用程序目录路径。 例如，如果从路径 C:\Office\MyApp.exe 运行可执行文件，则域标识将 C:\Office\MyApp.exe。  
  
-   程序集标识是程序集的证据。 这可能来自于加密的数字签名，它可以是程序集的[强名称](../../../docs/framework/app-domains/strong-named-assemblies.md)，该程序集，或者其 URL 标识的软件发布者。 如果程序集具有强名称和软件发布者标识，则使用软件发布者标识。 如果程序集来自 Internet，并且是无符号，则使用的 URL 标识。 有关程序集和强名称的详细信息，请参阅[使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)。  
  
-   与用户拥有漫游用户配置文件一起移动漫游存储区。 文件写入到网络目录和下载到的任何计算机在用户登录到。 有关漫游用户配置文件的详细信息，请参阅<xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>。  
  
 通过组合的用户、 域和程序集标识的概念，独立的存储可通过以下方式，其中每个有其自己的使用方案隔离数据：  
  
-   [按用户和程序集隔离](#UserAssembly)  
  
-   [按用户、 域和程序集隔离](#UserDomainAssembly)  
  
 这些隔离任一可以结合漫游用户配置文件。 有关详细信息，请参阅明[独立存储和漫游](#Roaming)。  
  
 下图演示了如何将存储隔离在不同的作用域中。  
  
 ![按用户和程序集隔离](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")  
独立存储的类型  
  
 请注意，除了漫游存储区，独立的存储始终隐式按隔离计算机因为它使用给定计算机本地存储设施。  
  
> [!IMPORTANT]
>  独立存储不适用于 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用。 相反，使用 `Windows.Storage` API 中包含的 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 命名空间中的应用程序数据类来存储本地数据和文件。 有关详细信息，请参阅 Windows 开发人员中心的 [应用程序数据](http://go.microsoft.com/fwlink/?LinkId=229175) 。  
  
<a name="UserAssembly"></a>   
## <a name="isolation-by-user-and-assembly"></a>按用户和程序集隔离  
 如果使用的数据的程序集存储需求，可从任何应用程序的域，按用户和程序集隔离适合。 通常情况下，在此情况下，独立的存储用于存储应用跨多个应用程序并不依赖于任何特定的应用程序，如用户的名称或许可证信息的数据。 若要访问按用户和程序集隔离的存储，代码必须是受信任应用程序之间传输信息。 通常情况下，在 intranet 上但不是能在 Internet 允许按用户和程序集隔离。 调用静态<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType>方法并传入用户和程序集<xref:System.IO.IsolatedStorage.IsolatedStorageScope>返回具有这种隔离的存储。  
  
 下面的代码示例检索按用户和程序集隔离的存储区。 可以通过访问该存储区`isoFile`对象。  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 使用证据参数示例，请参阅<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>。  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>方法可作为快捷方式，如下面的代码示例中所示。 此快捷方式不能用于打开能够漫游; 的存储使用<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>这种情况下。  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## <a name="isolation-by-user-domain-and-assembly"></a>按用户、域和程序集隔离  
 如果你的应用程序使用第三方程序集，需要专用数据存储，你可以使用独立的存储来存储的专用数据。 按用户、 域和程序集隔离可确保只有给定程序集中的代码可以访问数据，并仅当程序集使用的应用程序时创建程序集的应用商店中，正在运行且仅当的用户为其创建存储在运行时 应用程序。 按用户、 域和程序集隔离保留泄漏到其他应用程序的数据的第三方程序集。 如果你知道你想要使用独立的存储，但不确定哪种类型的隔离使用，此隔离类型应为默认选择。 调用静态<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>方法<xref:System.IO.IsolatedStorage.IsolatedStorageFile>并传入用户、 域和程序集<xref:System.IO.IsolatedStorage.IsolatedStorageScope>返回具有这种隔离的存储。  
  
 下面的代码示例检索按用户、 域和程序集隔离的存储区。 可以通过访问该存储区`isoFile`对象。  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 另一种方法可作为快捷方式，如下面的代码示例中所示。 此快捷方式不能用于打开能够漫游; 的存储使用<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>这种情况下。  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## <a name="isolated-storage-and-roaming"></a>独立存储和漫游  
 漫游用户配置文件是一种 Windows 功能，使用户能够设置在网络上的标识和使用该标识登录到任何网络计算机，又于所有个性化设置。 使用独立的存储程序集可以指定用户的独立的存储应具有漫游用户配置文件迁移。 漫游可在按用户和程序集隔离或隔离一起按用户、 域和程序集。 如果未使用的漫游的作用域，将不会漫游存储区，即使使用漫游用户配置文件。  
  
 下面的代码示例检索按用户和程序集隔离的漫游存储区。 可以通过访问该存储区`isoFile`对象。  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 可以添加域作用域，以创建按用户、 域和应用程序隔离的漫游存储区。 下面的代码示例说明这一点。  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [独立存储](../../../docs/standard/io/isolated-storage.md)
