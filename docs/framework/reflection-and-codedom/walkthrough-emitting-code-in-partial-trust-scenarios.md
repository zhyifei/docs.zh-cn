---
title: "演练：在部分信任应用场景中发出代码 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "匿名承载的动态方法 [.NET Framework]"
  - "动态方法"
  - "发出动态程序集, 部分信任方案"
  - "部分信任, 发出动态方法"
  - "部分信任, 反射"
  - "反射发出, 匿名承载的动态方法"
  - "反射发出, 动态方法"
  - "反射发出, 部分信任方案"
ms.assetid: c45be261-2a9d-4c4e-9bd6-27f0931b7d25
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 演练：在部分信任应用场景中发出代码
反射发出在完全信任或部分信任的情况下使用相同的 API 集，但有些功能在部分受信任的代码中需要特殊权限。  此外，反射发出还具有一种功能 \- 匿名承载的动态方法，该功能旨在供安全透明的程序集在部分信任的情况下使用。  
  
> [!NOTE]
>  在 [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)]以前，发出代码需要具有 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> 标志的 <xref:System.Security.Permissions.ReflectionPermission>。  默认情况下，此权限包含在 `FullTrust` 和 `Intranet` 命名权限集中，但不在 `Internet` 权限集中。  因此，只有当它具有 <xref:System.Security.SecurityCriticalAttribute> 属性并为<xref:System.Security.Permissions.ReflectionPermissionFlag>执行了 <xref:System.Security.PermissionSet.Assert%2A>方法，一个方案库可以从部分信任使用。  这种库需要进行仔细的安全检查，因为编码错误可能会导致安全漏洞。  [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 允许在部分信任的方案中发出代码而无需发出任何安全请求，因为生成代码本身不是一项特权操作。  也就是说，生成的代码不会具有比发出它的程序集更多的权限。  这使得发出代码的库是安全透明的，且不再需要断言 <xref:System.Security.Permissions.ReflectionPermissionFlag>，这样一来，编写安全的库就不需要进行彻底的安全检查了。  
  
 本演练阐释了以下任务：  
  
-   [设置简单沙盒以测试部分信任的代码](#Setting_up)。  
  
    > [!IMPORTANT]
    >  这是一种试验处于部分信任模式的代码的简单方法。  若要运行实际上来自于不可信位置的代码，请参见[如何：运行沙盒中部分受信任的代码](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)。  
  
-   [在部分受信任的应用程序域中运行代码](#Running_code)。  
  
-   [使用匿名承载的动态方法在部分信任的情况下发出和执行代码](#Using_methods)。  
  
 有关在部分信任的方案中发出代码的更多信息，请参见[反射发出中的安全问题](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)。  
  
 有关这些过程中所显示的完整代码清单，请参见本演练结尾处的[“示例”一节](#Example)。  
  
<a name="Setting_up"></a>   
## 设置部分受信任的位置  
 下面的两个过程演示如何设置可从中对处于部分信任模式的代码进行测试的位置。  
  
-   第一个过程演示如何创建一个沙盒应用程序域，其中的代码将被授予 Internet 权限。  
  
-   第二个过程演示如何将具有 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> 标志的 <xref:System.Security.Permissions.ReflectionPermission> 添加到一个部分受信任的应用程序域中，以便允许访问具有相同或更低信任的程序集中的私有数据。  
  
### 创建沙盒应用程序域  
 若要创建您的程序集在其中在部分信任下运行的应用程序域，您必须通过使用 [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName> 方法重载创建应用程序域来指定要向这些程序集授予的权限集。  指定授予集的最简单方法是从安全策略中检索命名权限集。  
  
 下面的过程创建运行您的部分信任代码的沙盒应用程序域，以便测试发出的代码在其中只能访问公共类型的公共成员的方案。  后面的过程演示如何添加 <xref:System.Security.Permissions.ReflectionPermissionFlag>，以便测试发出的代码可在其中访问被授予相同或更低权限的程序集中非公共类型和成员的方案。  
  
##### 创建部分信任的应用程序域  
  
1.  创建一个权限集以将其授予沙盒应用程序域中的程序集。  在此例中，将使用 Internet 区域的权限集。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#2)]
     [!code-vb[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#2)]  
  
2.  创建一个 <xref:System.AppDomainSetup> 对象，以便初始化具有应用程序路径的应用程序域。  
  
    > [!IMPORTANT]
    >  为简单起见，此代码示例使用当前的文件夹。  若要运行实际上来自于 Internet 的代码，请对不受信任的代码使用单独的文件夹，如[如何：运行沙盒中部分受信任的代码](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)中所述。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#3)]
     [!code-vb[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#3)]  
  
3.  创建应用程序域，同时指定应用程序域设置信息，并为在应用程序域中执行的所有程序集指定授予集。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#5)]
     [!code-vb[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#5)]  
  
     [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName> 方法重载的最后一个参数可让您指定一组程序集，这些程序集将被授予完全信任而不是授予该应用程序域的授予集。  您不必指定您的应用程序使用的 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 程序集，因为这些程序集位于全局程序集缓存中。  全局程序集缓存中的程序集总是完全受信任。  可以使用此参数指定不在全局程序集缓存中的、具有强名称的程序集。  
  
### 将 RestrictedMemberAccess 添加到沙盒域  
 宿主应用程序允许匿名承载的动态方法具有程序集中私有数据的访问权限，前提是这些程序集的信任级别不高于发出代码的程序集的信任级别。  为了使此受限制的能力跳过实时 \(JIT\) 可见性检查，宿主应用程序会将具有 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> \(RMA\) 标志的 <xref:System.Security.Permissions.ReflectionPermission> 对象添加到授予集中。  
  
 例如，宿主可能会向 Internet 应用程序授予 Internet 权限及 RMA，以使 Internet 应用程序可以发出访问其自己的程序集中的私有数据的代码。  由于访问限于具有相同或更低信任的程序集，因此 Internet 应用程序无法访问 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 程序集等完全受信任的程序集的成员。  
  
> [!NOTE]
>  为了防止特权提升，在构造匿名承载的动态方法时会包括发出程序集的堆栈信息。  调用该方法时，会检查堆栈信息。  因此，从完全受信任的代码中调用的匿名承载的动态方法仍然仅限于发出程序集的信任级别。  
  
##### 创建部分信任的具有 RMA 的应用程序域  
  
1.  创建一个具有 <xref:System.Security.Permissions.ReflectionPermissionFlag> \(RMA\) 标志的新 <xref:System.Security.Permissions.ReflectionPermission> 对象，并使用 <xref:System.Security.PermissionSet.SetPermission%2A?displayProperty=fullName> 方法向授予集添加权限。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#7)]
     [!code-vb[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#7)]  
  
     如果授予集中尚无权限，<xref:System.Security.PermissionSet.AddPermission%2A> 方法会向其中添加权限。  如果授予集中已经包含权限，则指定的标志会添加给现有权限。  
  
    > [!NOTE]
    >  RMA 是匿名承载的动态方法的一个功能。  当普通的动态方法跳过 JIT 可见性检查时，发出的代码需要完全信任。  
  
2.  创建应用程序域，同时指定应用程序域设置信息和授予集。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#8)]
     [!code-vb[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#8)]  
  
<a name="Running_code"></a>   
## 在沙盒应用程序域内运行代码  
 下面的过程说明如何使用可在应用程序域中执行的方法定义一个类，如何在域中创建该类的实例以及如何执行其方法。  
  
#### 在应用程序域中定义和执行方法  
  
1.  定义一个从 <xref:System.MarshalByRefObject> 派生的类。  这样，您可以在其他应用程序域中创建该类的实例并跨应用程序域边界进行方法调用。  在本示例中，该类被命名为 `Worker`。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#10)]
     [!code-vb[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#10)]  
  
2.  定义其中包含您要执行的代码的公共方法。  在本示例中，代码发出简单的动态方法，创建委托来执行该方法并调用该委托。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#11)]
     [!code-vb[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#11)]  
  
3.  在您的主程序中，获取程序集的显示名称。  在沙盒应用程序域中创建 `Worker` 类的实例时要使用此名称。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#14)]
     [!code-vb[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#14)]  
  
4.  在您的主程序中，按照本演练的[第一个过程](#Setting_up)中的说明创建沙盒应用程序域。  不必向 `Internet` 权限集中添加任何权限，因为 `SimpleEmitDemo` 方法仅使用公共方法。  
  
5.  在您的主程序中，在沙盒应用程序域中创建 `Worker` 类的一个实例。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#12)]
     [!code-vb[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#12)]  
  
     <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> 方法在目标应用程序域中创建该对象并返回可用来调用该对象的属性和方法的代理。  
  
    > [!NOTE]
    >  如果在 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]使用该代码，则必须更改选件类的名称以包括命名空间。  默认情况下，命名空间是项目的名称。  例如，如果项目为“PartialTrust”，则类名必须为“PartialTrust.Worker”。  
  
6.  添加代码以调用 `SimpleEmitDemo` 方法。  该调用跨应用程序域边界封送，并且该代码在沙盒应用程序域中执行。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#13)]
     [!code-vb[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#13)]  
  
<a name="Using_methods"></a>   
## 使用匿名承载的动态方法  
 匿名承载的动态方法与系统提供的一个透明的程序集相关联。  因此，它们包含的代码是透明的。  另一方面，普通的动态方法必须与现有模块关联（是直接指定还是从关联的类型推断出），并从该模块获取其安全级别。  
  
> [!NOTE]
>  将动态方法与提供匿名承载的程序集相关联的唯一方式是使用以下过程中介绍的构造函数。  您不能在匿名承载程序集中显式指定模块。  
  
 普通的动态方法可以访问与之关联的模块的内部成员，或者访问与之关联的类型的私有成员。  由于匿名承载的动态方法独立于其他代码，因此它们不能访问私有数据。  但是，它们的确具有跳过 JIT 可见性检查的受限能力，能够获取对私有数据的访问权限。  这种能力仅限于信任级别不高于发出代码的程序集的信任级别的程序集。  
  
 为了防止特权提升，在构造匿名承载的动态方法时会包括发出程序集的堆栈信息。  调用该方法时，会检查堆栈信息。  从完全受信任的代码中调用的匿名承载的动态方法仍然仅限于发出该代码的程序集的信任级别。  
  
#### 使用匿名承载的动态方法  
  
-   通过使用未指定相关联模块或类型的构造函数来创建匿名承载的动态方法。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#15)]
     [!code-vb[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#15)]  
  
     如果匿名承载的动态方法仅使用公共类型和方法，则它不需要受限成员访问权限并且不必跳过 JIT 可见性检查。  
  
     发出动态方法不需任何特殊权限，但发出的代码需要其使用的类型和方法所请求的权限。  例如，如果发出的代码调用访问某个文件的方法，则该代码需要 <xref:System.Security.Permissions.FileIOPermission>。  如果信任级别中未包括该权限，则在执行该发出的代码时会引发安全异常。  此处显示的代码发出仅使用 <xref:System.Console.WriteLine%2A?displayProperty=fullName> 方法的动态方法。  因此，该代码可从部分受信任的位置执行。  
  
-   或者，通过使用 [DynamicMethod\(String, Type, Type\<xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29> 构造函数并为参数 `restrictedSkipVisibility` 指定 `true` 来创建匿名承载的动态方法，该方法具有跳过 JIT 可见性检查的受限能力。  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#16)]
     [!code-vb[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#16)]  
  
     该限制是匿名承载的动态方法只能访问信任级别不高于发出程序集信任级别的程序集中的私有数据。  例如，如果动态方法在 Internet 信任模式下执行，则它可以访问其他同样在 Internet 信任模式下执行的程序集中的私有数据，但它无法访问 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 程序集的私有数据。  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 程序集在全局程序集缓存中进行安装，并总是完全受信任。  
  
     仅当宿主应用程序授予具有 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> 标志的 <xref:System.Security.Permissions.ReflectionPermission> 时，匿名承载的动态方法才可以使用此跳过 JIT 可见性检查的受限能力。  对此权限的请求在调用该方法时发出。  
  
    > [!NOTE]
    >  在构造动态方法时，将包含发出程序集的调用堆栈信息。  因此，请求是针对发出程序集的权限而不是调用该方法的程序集的权限发出的。  这样可以阻止发出的代码以提升的权限执行。  
  
     本演练结尾处的[完整代码示例](#Example)演示受限成员访问权限的用法和限制。  其 `Worker` 类包含的方法可以创建具有或没有跳过可见性检查的受限能力的匿名承载的动态方法，并且该示例演示在具有不同信任级别的应用程序域中执行此方法的结果。  
  
    > [!NOTE]
    >  跳过可见性检查的受限能力是匿名承载的动态方法的一个功能。  当普通的动态方法跳过 JIT 可见性检查时，必须向它们授予完全信任。  
  
<a name="Example"></a>   
## 示例  
  
### 描述  
 下面的代码示例演示 <xref:System.Security.Permissions.ReflectionPermissionFlag> 标志的用法，以允许匿名承载的动态方法跳过 JIT 可见性检查，前提是目标成员的信任级别等于或低于发出此代码的程序集。  
  
 该示例定义了一个 `Worker` 类，该类可以跨应用程序域边界进行封送。  该类有两个发出并执行动态方法的 `AccessPrivateMethod` 方法重载。  第一个重载发出调用 `Worker` 类的私有 `PrivateMethod` 方法的动态方法，它可以发出跳过或不跳过 JIT 可见性检查的动态方法。  第二个重载发出访问 <xref:System.String> 类的 `internal` 属性（在 Visual Basic 中为 `Friend` 属性）的动态方法。  
  
 该示例使用帮助器方法来创建一个限于 `Internet` 权限的授予集，然后创建一个应用程序域，并使用 [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName> 方法重载来指定在该域中执行的所有代码都使用此授予集。  该示例在应用程序域中创建了 `Worker` 类的一个实例，并执行 `AccessPrivateMethod` 方法两次。  
  
-   第一次执行 `AccessPrivateMethod` 方法时，强制执行 JIT 可见性检查。  动态方法在调用时失败，因为 JIT 可见性检查阻止其访问私有方法。  
  
-   第二次执行 `AccessPrivateMethod` 方法时，跳过 JIT 可见性检查。  动态方法在编译时失败，因为 `Internet` 授予集未授予足够的权限跳过可见性检查。  
  
 下面的示例将带有 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> 的 <xref:System.Security.Permissions.ReflectionPermission> 添加到授予集中。  该示例然后又创建了一个域，指定在此域中执行的所有代码都授予了新授予集中的权限。  该示例在新应用程序域中创建了 `Worker` 类的一个实例，并执行 `AccessPrivateMethod` 方法的两个重载。  
  
-   执行 `AccessPrivateMethod` 方法的第一个重载，跳过 JIT 可见性检查。  动态方法成功编译并执行，因为发出代码的程序集与包含私有方法的程序集相同。  因此，信任级别也是相同的。  如果包含 `Worker` 类的应用程序有若干个程序集，则对于这些程序集中的任何一个来说，同一个进程都会成功，因为它们的信任级别相同。  
  
-   执行 `AccessPrivateMethod` 方法的第二个重载，再次跳过 JIT 可见性检查。  这一次动态方法在编译时失败，因为它尝试访问 <xref:System.String> 类的 `internal` `FirstChar` 属性。  包含 <xref:System.String> 类的程序集是完全受信任的。  因此，它的信任级别比发出代码的程序集高。  
  
 此对比说明 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> 如何使部分受信任的代码跳过其他部分受信任的代码的可见性检查，而不危及受信任代码的安全。  
  
### 代码  
 [!code-csharp[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#1)]
 [!code-vb[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#1)]  
  
## 编译代码  
  
-   如果在 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 中生成此代码示例，则当您将类传递给 <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> 方法时必须更改类的名称以包含命名空间。  默认情况下，命名空间是项目的名称。  例如，如果项目为“PartialTrust”，则类名必须为“PartialTrust.Worker”。  
  
## 请参阅  
 [反射发出中的安全问题](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)   
 [如何：运行沙盒中部分受信任的代码](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)