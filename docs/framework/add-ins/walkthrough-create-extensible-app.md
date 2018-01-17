---
title: "演练：创建可扩展的应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [.NET Framework], add-in pipeline
- host-side adapters for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], creating
- add-in-side adapter [.NET Framework]
- contracts for add-in pipelines [.NET Framework]
ms.assetid: 694a33c5-a040-450d-aed5-ac49fc88ce61
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac4b6fc2ae36d848306178f281cceeeb0654ec03
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-extensible-application"></a>演练：创建可扩展的应用程序
本演练介绍如何创建用于执行简单的计算器功能的外接程序的管道。 它并不演示实际方案;相反，它演示了管道以及如何外接程序可以提供主机服务的基本功能。  
  
 本演练介绍了以下任务：  
  
-   创建 Visual Studio 解决方案。  
  
-   创建管线目录结构。  
  
-   创建的协定和视图。  
  
-   创建外接程序端适配器。  
  
-   创建主机端适配器。  
  
-   创建主机。  
  
-   创建外接程序。  
  
-   部署管道。  
  
-   运行主机应用程序。  
  
 此管道传递仅可序列化的类型 (<xref:System.Double>和<xref:System.String>)、 主机和外接程序之间。 有关示例，演示如何将传递复杂数据类型的集合，请参阅[演练： 将集合传递之间主机和外接程序](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)。  
  
 此管道协定定义四个算术运算的对象模型： 添加、 减、 乘和除。 主机外接程序提供的公式来计算，如 2 + 2，和外接程序将结果返回给主机。  
  
 版本 2 的计算器外接程序提供更多的计算的可能性，并演示版本控制。 中描述的那样[演练： 启用作为主机所做的更改的向后兼容性](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)。  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你需要具备以下条件：  
  
-   [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]。  
  
## <a name="creating-a-visual-studio-solution"></a>创建 Visual Studio 解决方案  
 使用一种解决方案[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]以包含的管道段的项目。  
  
#### <a name="to-create-the-pipeline-solution"></a>若要创建管道解决方案  
  
1.  在[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，创建一个名为的新项目`Calc1Contract`。 使该项目基于**类库**模板。  
  
2.  将解决方案命名`CalculatorV1`。  
  
## <a name="creating-the-pipeline-directory-structure"></a>创建管线目录结构  
 外接程序模型需要置于指定的目录结构中的管道段程序集。 有关管道结构的详细信息，请参阅[管线开发要求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。  
  
#### <a name="to-create-the-pipeline-directory-structure"></a>若要创建管线目录结构  
  
1.  在你的计算机上的任何位置创建应用程序文件夹。  
  
2.  在该文件夹中，创建以下结构：  
  
    ```  
    Pipeline  
      AddIns  
        CalcV1  
        CalcV2  
      AddInSideAdapters  
      AddInViews  
      Contracts  
      HostSideAdapters  
    ```  
  
     不需要将管道文件夹结构放在应用程序文件夹中;它仅为方便起见在此处完成。 在相应的步骤，本演练说明如何更改代码，如果管道文件夹结构是在不同的位置。 请参阅中的管道 directory 要求讨论[管线开发要求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。  
  
    > [!NOTE]
    >  `CalcV2`文件夹不会使用在本演练中; 它是一个占位符，供[演练： 启用作为主机所做的更改的向后兼容性](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)。  
  
## <a name="creating-the-contract-and-views"></a>正在创建协定和视图  
 此管道的合约段定义`ICalc1Contract`接口，定义四个方法： `add`， `subtract`， `multiply`，和`divide`。  
  
#### <a name="to-create-the-contract"></a>若要创建协定  
  
1.  在 Visual Studio 解决方案中名为`CalculatorV1`，打开`Calc1Contract`项目。  
  
2.  在**解决方案资源管理器**，添加到了下列程序集的引用`Calc1Contract`项目：  
  
     System.AddIn.Contract.dll  
  
     System.AddIn.dll  
  
3.  在**解决方案资源管理器**，排除添加到新的默认类**类库**项目。  
  
4.  在**解决方案资源管理器**，将新项添加到项目中，使用**接口**模板。 在**添加新项**对话框中，名称接口`ICalc1Contract`。  
  
5.  在接口文件中，添加到的命名空间引用<xref:System.AddIn.Contract>和<xref:System.AddIn.Pipeline>。  
  
6.  使用下面的代码来完成此合约段。 请注意，此接口必须具有<xref:System.AddIn.Pipeline.AddInContractAttribute>属性。  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  （可选） 生成的 Visual Studio 解决方案。 无法运行该解决方案，直到最后的过程中，但之后的每个过程可确保每个项目都进行生成更正。  
  
 由于外接程序视图和主机查看的外接程序通常具有相同的代码，尤其是在外接程序中的第一个版本，你可以轻松地在同一时间创建视图。 它们只能有一个方面不同： 外接程序中查看要求<xref:System.AddIn.Pipeline.AddInBaseAttribute>特性，尽管外接程序的主机视图不要求任何属性。  
  
#### <a name="to-create-the-add-in-view"></a>若要创建外接程序视图  
  
1.  添加一个名为的新项目`Calc1AddInView`到`CalculatorV1`解决方案。 使该项目基于**类库**模板。  
  
2.  在**解决方案资源管理器**，添加引用到 System.AddIn.dll`Calc1AddInView`项目。  
  
3.  在**解决方案资源管理器**，排除添加到新的默认类**类库**项目，并将新项添加到项目中，使用**接口**模板。 在**添加新项**对话框中，名称接口`ICalculator`。  
  
4.  在接口文件中，添加对的命名空间引用<xref:System.AddIn.Pipeline>。  
  
5.  使用下面的代码来完成此外接程序视图。 请注意，此接口必须具有<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性。  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  （可选） 生成的 Visual Studio 解决方案。  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a>若要创建的外接程序的主机视图  
  
1.  添加一个名为的新项目`Calc1HVA`到`CalculatorV1`解决方案。 使该项目基于**类库**模板。  
  
2.  在**解决方案资源管理器**，排除添加到新的默认类**类库**项目，并将新项添加到项目中，使用**接口**模板。 在**添加新项**对话框中，名称接口`ICalculator`。  
  
3.  在接口文件中，使用下面的代码完成的外接程序的主机视图。  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  （可选） 生成的 Visual Studio 解决方案。  
  
## <a name="creating-the-add-in-side-adapter"></a>创建接程序端适配器  
 此接程序端适配器包含一个视图协定适配器。 此管道段将从外接程序视图的类型转换为协定中。  
  
 此管道中外接程序提供到主机，和服务类型从外接程序流到主机。 由于没有类型流向从主机到外接程序，你无需包含协定视图适配器一侧外接程序中的此管道。  
  
#### <a name="to-create-the-add-in-side-adapter"></a>若要创建的外接程序端适配器  
  
1.  添加一个名为的新项目`Calc1AddInSideAdapter`到`CalculatorV1`解决方案。 使该项目基于**类库**模板。  
  
2.  在**解决方案资源管理器**，添加到了下列程序集的引用`Calc1AddInSideAdapter`项目：  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  添加对相邻的管道段的项目的项目引用：  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  选择每个项目引用，然后在**属性**设置**Copy Local**到**False**。 在 Visual Basic 中，使用**引用**选项卡**项目属性**设置**Copy Local**到**False**的两个项目的引用。  
  
5.  重命名项目的默认类`CalculatorViewToContractAddInSideAdapter`。  
  
6.  在类文件中，添加到的命名空间引用<xref:System.AddIn.Pipeline>。  
  
7.  在类文件中，添加相邻的段的命名空间引用：`CalcAddInViews`和`CalculatorContracts`。 (在 Visual Basic 中，可以这些命名空间引用`Calc1AddInView.CalcAddInViews`和`Calc1Contract.CalculatorContracts`，除非是关闭 Visual Basic 项目中的默认命名空间。)  
  
8.  应用<xref:System.AddIn.Pipeline.AddInAdapterAttribute>属性设为`CalculatorViewToContractAddInSideAdapter`类中，以标识为外接程序端适配器。  
  
9. 请`CalculatorViewToContractAddInSideAdapter`类继承<xref:System.AddIn.Pipeline.ContractBase>，该属性提供的默认实现<xref:System.AddIn.Contract.IContract>接口，并实现管道，协定接口`ICalc1Contract`。  
  
10. 添加一个公共构造函数接受的`ICalculator`，在私有字段中，对其进行缓存并调用基类构造函数。  
  
11. 若要实现的成员`ICalc1Contract`，只需调用的对应成员`ICalculator`传递给构造函数中，并返回结果的实例。 这使视图 (`ICalculator`) 到协定 (`ICalc1Contract`)。  
  
     下面的代码显示已完成的接程序端适配器。  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. （可选） 生成的 Visual Studio 解决方案。  
  
## <a name="creating-the-host-side-adapter"></a>创建主机端适配器  
 此主机端适配器包含一个协定视图适配器。 此段采用的外接程序的主机视图的协定。  
  
 此管道中外接程序提供服务对主机和类型流从外接程序到主机。 由于没有类型流向从主机到外接程序，你无需包括视图协定适配器。  
  
 若要实现生存期管理，使用<xref:System.AddIn.Pipeline.ContractHandle>对象以将生存期令牌附加到的协定。 按顺序生存期管理工作，必须保持对此句柄的引用。 应用令牌后，无需任何其他编程是必需的因为外接程序系统可以的对象时释放它们不再使用，并使它们可供垃圾回收。 有关详细信息，请参阅 [生存期管理](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5)。  
  
#### <a name="to-create-the-host-side-adapter"></a>若要创建的主机端适配器  
  
1.  添加一个名为的新项目`Calc1HostSideAdapter`到`CalculatorV1`解决方案。 使该项目基于**类库**模板。  
  
2.  在**解决方案资源管理器**，添加到了下列程序集的引用`Calc1HostSideAdapter`项目：  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  添加对相邻的段的项目的项目引用：  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  选择每个项目引用，然后在**属性**设置**Copy Local**到**False**。 在 Visual Basic 中，使用**引用**选项卡**项目属性**设置**Copy Local**到**False**的两个项目的引用。  
  
5.  重命名项目的默认类`CalculatorContractToViewHostSideAdapter`。  
  
6.  在类文件中，添加到的命名空间引用<xref:System.AddIn.Pipeline>。  
  
7.  在类文件中，添加相邻的段的命名空间引用：`CalcHVAs`和`CalculatorContracts`。 (在 Visual Basic 中，可以这些命名空间引用`Calc1HVA.CalcHVAs`和`Calc1Contract.CalculatorContracts`，除非是关闭 Visual Basic 项目中的默认命名空间。)  
  
8.  应用<xref:System.AddIn.Pipeline.HostAdapterAttribute>属性设为`CalculatorContractToViewHostSideAdapter`类中，以标识为宿主端适配器段。  
  
9. 请`CalculatorContractToViewHostSideAdapter`类实现接口表示外接程序的主机视图： `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator`在 Visual Basic 中)。  
  
10. 添加一个公共构造函数，以接受管道协定类型， `ICalc1Contract`。 构造函数必须缓存对协定的引用。 它还必须创建并缓存新<xref:System.AddIn.Pipeline.ContractHandle>对于协定，若要管理的外接程序的生存期。  
  
    > [!IMPORTANT]
    >  <xref:System.AddIn.Pipeline.ContractHandle>至关重要生命期管理。 如果您不能保持对引用<xref:System.AddIn.Pipeline.ContractHandle>对象，垃圾回收将回收，以及当你的程序不需要其管道将关闭。 这可能导致的错误很难诊断，如<xref:System.AppDomainUnloadedException>。 关闭是管道的生活中，正常阶段，因此没有检测到这种情况是管道的错误的生存期管理代码的方法。  
  
11. 若要实现的成员`ICalculator`，只需调用的对应成员`ICalc1Contract`传递给构造函数中，并返回结果的实例。 这使协定 (`ICalc1Contract`) 到视图 (`ICalculator`)。  
  
     下面的代码显示已完成的主机端适配器。  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. （可选） 生成的 Visual Studio 解决方案。  
  
## <a name="creating-the-host"></a>创建主机  
 将主机应用程序交互与外接程序通过外接程序的主机视图。 它使用外接程序发现和激活方法提供的<xref:System.AddIn.Hosting.AddInStore>和<xref:System.AddIn.Hosting.AddInToken>类来执行以下操作：  
  
-   更新管道和外接程序信息的缓存。  
  
-   查找宿主视图类型的加载项`ICalculator`，指定的管道根目录下。  
  
-   提示用户指定的外接程序使用。  
  
-   激活的所选外接程序中具有指定的安全信任级别的新应用程序域。  
  
-   运行自定义`RunCalculator`方法，调用指定的外接程序的主机视图的外接程序的方法。  
  
#### <a name="to-create-the-host"></a>若要创建的主机  
  
1.  添加一个名为的新项目`Calc1Host`到`CalculatorV1`解决方案。 使该项目基于**控制台应用程序**模板。  
  
2.  在**解决方案资源管理器**，添加到 System.AddIn.dll 程序集的引用`Calc1Host`项目。  
  
3.  添加到项目引用`Calc1HVA`项目。 选择该项目引用，然后在**属性**设置**Copy Local**到**False**。 在 Visual Basic 中，使用**引用**选项卡**项目属性**设置**Copy Local**到**False**。  
  
4.  重命名类文件 （在 Visual Basic 中的模块） `MathHost1`。  
  
5.  在 Visual Basic 中，使用**应用程序**选项卡**项目属性**对话框可设置**启动对象**到**Sub Main**。  
  
6.  在类或模块文件中，添加对的命名空间引用<xref:System.AddIn.Hosting>。  
  
7.  在类或模块文件中，添加的外接程序的主机视图的命名空间引用： `CalcHVAs`。 (在 Visual Basic 中，此命名空间引用是`Calc1HVA.CalcHVAs`，除非是关闭 Visual Basic 项目中的默认命名空间。)  
  
8.  在**解决方案资源管理器**，选择解决方案并从**项目**菜单中，选择**属性**。 在**解决方案属性页**对话框中，设置**单启动项目**为此主机应用程序项目。  
  
9. 在类或模块文件中，使用<xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType>方法来更新缓存。 使用<xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType>方法以获取令牌的集合，并使用<xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType>方法以激活外接程序。  
  
     下面的代码显示已完成的宿主应用程序。  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  此代码假定管道文件夹结构位于应用程序文件夹。 如果在其他位置位于，更改的设置的代码行`addInRoot`变量，以便该变量包含管线目录结构的路径。  
  
     该代码使用`ChooseCalculator`方法来列出标记，并提示用户选择外接程序。 `RunCalculator`方法提示用户提供简单的数学表达式、 分析使用的表达式`Parser`类，并显示返回的结果外接程序。  
  
10. （可选） 生成的 Visual Studio 解决方案。  
  
## <a name="creating-the-add-in"></a>创建的外接程序  
 外接程序中实现指定的外接程序视图的方法。 此外接程序实现`Add`， `Subtract`， `Multiply`，和`Divide`操作并将结果返回给主机。  
  
#### <a name="to-create-the-add-in"></a>若要创建外接程序  
  
1.  添加一个名为的新项目`AddInCalcV1`到`CalculatorV1`解决方案。 使该项目基于**类库**模板。  
  
2.  在**解决方案资源管理器**，向项目添加 System.AddIn.dll 程序集的引用。  
  
3.  添加到项目引用`Calc1AddInView`项目。 选择该项目引用，然后在**属性**，将其设置**Copy Local**到**False**。 在 Visual Basic 中，使用**引用**选项卡**项目属性**设置**Copy Local**到**False**项目引用。  
  
4.  重命名类`AddInCalcV1`。  
  
5.  在类文件中，添加对的命名空间引用<xref:System.AddIn>和外接程序视图分段： `CalcAddInViews` (`Calc1AddInView.CalcAddInViews`在 Visual Basic 中)。  
  
6.  应用<xref:System.AddIn.AddInAttribute>属性设为`AddInCalcV1`类中，以将类标识为外接程序。  
  
7.  请`AddInCalcV1`类实现接口表示外接程序视图： `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator`在 Visual Basic 中)。  
  
8.  实现的成员`ICalculator`通过返回相应的计算的结果。  
  
     下面的代码演示的已完成外接程序。  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. （可选） 生成的 Visual Studio 解决方案。  
  
## <a name="deploying-the-pipeline"></a>部署管道  
 现在你就可以生成并部署到所需的管线目录结构的外接程序段。  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a>若要将段部署到管道  
  
1.  对于每个项目解决方案中，使用**生成**选项卡**项目属性**(**编译**在 Visual Basic 中的选项卡) 若要设置的值**输出路径** (**生成输出路径**在 Visual Basic 中)。 如果名为应用程序文件夹`MyApp`，例如，你的项目将生成到以下文件夹：  
  
    |Project|路径|  
    |-------------|----------|  
    |AddInCalcV1|MyApp\Pipeline\AddIns\CalcV1|  
    |Calc1AddInSideAdapter|MyApp\Pipeline\AddInSideAdapters|  
    |Calc1AddInView|MyApp\Pipeline\AddInViews|  
    |Calc1Contract|MyApp\Pipeline\Contracts|  
    |Calc1Host|MyApp|  
    |Calc1HostSideAdapter|MyApp\Pipeline\HostSideAdapters|  
    |Calc1HVA|MyApp|  
  
    > [!NOTE]
    >  如果你决定将管道文件夹结构放在应用程序文件夹以外的位置，则必须修改相应的表所示的路径。 请参阅中的管道 directory 要求讨论[管线开发要求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。  
  
2.  生成 Visual Studio 解决方案。  
  
3.  检查应用程序和管线目录，以确保程序集已复制到正确的目录，并在错误的文件夹已安装的程序集的任何额外副本。  
  
    > [!NOTE]
    >  如果你并未更改**Copy Local**到**False**为`Calc1AddInView`项目中的引用`AddInCalcV1`项目中，加载程序上下文问题将阻止外接程序位于。  
  
     有关将部署到管道的信息，请参阅[管线开发要求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。  
  
## <a name="running-the-host-application"></a>运行主机应用程序  
 现在你就可以运行主机并与外接程序进行交互。  
  
#### <a name="to-run-the-host-application"></a>若要运行主机应用程序  
  
1.  在命令提示符处，转到应用程序目录并运行主机应用程序， `Calc1Host.exe`。  
  
2.  主机查找所有可用外接其类型，并提示您选择外接程序。 输入**1**的唯一可用外接程序。  
  
3.  输入的公式为计算器，如**2 + 2**。 必须有数字和运算符之间的空格。  
  
4.  类型**退出**按**Enter**键关闭应用程序。  
  
## <a name="see-also"></a>请参阅  
 [演练： 启用主机更改为向后的兼容性](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [主机和外接程序之间的演练： 传递集合](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [管线开发要求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [协定、 视图和适配器](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [管道开发](../../../docs/framework/add-ins/pipeline-development.md)
