---
title: 演练：创建可扩展的应用程序
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d2aaeaffaf3abbe1e8efcdb57d40e6ae60f89b5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43552330"
---
# <a name="walkthrough-creating-an-extensible-application"></a>演练：创建可扩展的应用程序
本演练介绍如何创建用于执行简单的计算器功能的外接程序的管道。 它并不演示实际方案中;相反，它演示了一个管道，以及如何外接程序可以提供主机服务的基本功能。  
  
 本演练介绍了以下任务：  
  
-   创建一个 Visual Studio 解决方案。  
  
-   正在创建管线目录结构。  
  
-   正在创建的协定和视图。  
  
-   创建外接程序端适配器。  
  
-   创建主机端适配器。  
  
-   创建主机。  
  
-   创建外接程序。  
  
-   部署管道。  
  
-   运行主机应用程序。  
  
 此管道传递仅可序列化类型 (<xref:System.Double>和<xref:System.String>)、 主机和外接程序之间。 有关演示如何将传递复杂数据类型的集合的示例，请参阅[演练： 将集合传递之间主机和外接程序](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)。  
  
 此管道的协定定义四个算术操作的对象模型： 添加、 减、 乘和除。 主机外接程序提供的公式来计算 2 + 2，如和外接程序将结果返回到主机。  
  
 第 2 版的计算器外接程序提供更多的计算的可能性，并演示了版本控制。 中所述[演练： 为主机所做的更改启用向后兼容性](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)。  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你需要具备以下条件：  
  
-   Visual Studio。  
  
## <a name="creating-a-visual-studio-solution"></a>创建一个 Visual Studio 解决方案  
 使用 Visual Studio 中一种解决方案来包含管线段的项目。  
  
#### <a name="to-create-the-pipeline-solution"></a>若要创建管道解决方案  
  
1.  在 Visual Studio 中，创建一个名为的新项目`Calc1Contract`。 使该项目基于**类库**模板。  
  
2.  将解决方案命名`CalculatorV1`。  
  
## <a name="creating-the-pipeline-directory-structure"></a>创建管线目录结构  
 外接程序模型要求要置于指定的目录结构中的管道段程序集。 管道结构的详细信息，请参阅[管线开发要求](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。  
  
#### <a name="to-create-the-pipeline-directory-structure"></a>若要创建管线目录结构  
  
1.  在您的计算机上的任意位置创建一个应用程序文件夹。  
  
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
  
     不需要将管道文件夹结构放在你的应用程序文件夹;此处这样做是仅为方便起见。 在相应的步骤，本演练介绍如何更改代码，如果管道文件夹结构是在不同的位置。 请参阅中的管道目录要求的讨论[管线开发要求](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。  
  
    > [!NOTE]
    >  `CalcV2`不在本演练中使用文件夹; 它是占位符[演练： 为主机所做的更改启用向后兼容性](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)。  
  
## <a name="creating-the-contract-and-views"></a>创建的协定和视图  
 此管道的协定段定义`ICalc1Contract`接口，它定义了四个方法： `add`， `subtract`， `multiply`，和`divide`。  
  
#### <a name="to-create-the-contract"></a>若要创建协定  
  
1.  在 Visual Studio 解决方案中名为`CalculatorV1`，打开`Calc1Contract`项目。  
  
2.  在中**解决方案资源管理器**，将引用添加到以下程序集到`Calc1Contract`项目：  
  
     System.AddIn.Contract.dll  
  
     System.AddIn.dll  
  
3.  在中**解决方案资源管理器**，排除添加到新的默认类**类库**项目。  
  
4.  在中**解决方案资源管理器**，将新项添加到项目中，使用**接口**模板。 在中**添加新项**对话框中，名称接口`ICalc1Contract`。  
  
5.  在接口文件中，添加对命名空间引用<xref:System.AddIn.Contract>和<xref:System.AddIn.Pipeline>。  
  
6.  使用以下代码来完成此协定段。 请注意，此接口必须具有<xref:System.AddIn.Pipeline.AddInContractAttribute>属性。  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  （可选） 构建的 Visual Studio 解决方案。 无法运行该解决方案，直到最后的过程，但之后的每个过程可确保每个项目都进行生成更正。  
  
 由于外接程序视图和主机视图的外接程序通常具有相同的代码，尤其是在外接程序的第一个版本，可以轻松地在同一时间创建视图。 它们只有一个方面不同： 外接程序视图需要<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性，而宿主视图的外接程序不需要任何属性。  
  
#### <a name="to-create-the-add-in-view"></a>若要创建外接程序视图  
  
1.  添加一个名为的新项目`Calc1AddInView`到`CalculatorV1`解决方案。 使该项目基于**类库**模板。  
  
2.  在中**解决方案资源管理器**，添加对到 System.AddIn.dll`Calc1AddInView`项目。  
  
3.  在中**解决方案资源管理器**，排除添加到新的默认类**类库**项目，并将新项添加到项目中，使用**接口**模板。 在中**添加新项**对话框中，名称接口`ICalculator`。  
  
4.  在接口文件中，添加对的命名空间引用<xref:System.AddIn.Pipeline>。  
  
5.  使用以下代码来完成该外接程序视图。 请注意，此接口必须具有<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性。  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  （可选） 构建的 Visual Studio 解决方案。  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a>若要创建的外接程序的宿主视图  
  
1.  添加一个名为的新项目`Calc1HVA`到`CalculatorV1`解决方案。 使该项目基于**类库**模板。  
  
2.  在中**解决方案资源管理器**，排除添加到新的默认类**类库**项目，并将新项添加到项目中，使用**接口**模板。 在中**添加新项**对话框中，名称接口`ICalculator`。  
  
3.  在接口文件中，使用以下代码以完成外接程序的宿主视图。  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  （可选） 构建的 Visual Studio 解决方案。  
  
## <a name="creating-the-add-in-side-adapter"></a>创建接程序端适配器  
 此接程序端适配器由一个视图到约定适配器组成。 此管道段将类型从外接程序视图转换为约定。  
  
 在此管道中外, 接程序提供一个服务到主机，和类型从外接程序流到主机。 由于没有类型流向从宿主向外接程序，您无需包括此管道的外接程序端上的约定到视图适配器。  
  
#### <a name="to-create-the-add-in-side-adapter"></a>若要创建外接程序端适配器  
  
1.  添加一个名为的新项目`Calc1AddInSideAdapter`到`CalculatorV1`解决方案。 使该项目基于**类库**模板。  
  
2.  在中**解决方案资源管理器**，将引用添加到以下程序集到`Calc1AddInSideAdapter`项目：  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  添加相邻的管线段的项目到项目引用：  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  选择每个项目引用，然后在**属性**设置**Copy Local**到**False**。 在 Visual Basic 中，使用**引用**选项卡**项目属性**若要设置**复制本地**到**False**为两个项目的引用。  
  
5.  重命名项目的默认类`CalculatorViewToContractAddInSideAdapter`。  
  
6.  在类文件中，添加对命名空间引用<xref:System.AddIn.Pipeline>。  
  
7.  在类文件中，添加相邻的段的命名空间引用：`CalcAddInViews`和`CalculatorContracts`。 (在 Visual Basic 中的这些命名空间引用`Calc1AddInView.CalcAddInViews`和`Calc1Contract.CalculatorContracts`，除非是关闭 Visual Basic 项目中的默认命名空间。)  
  
8.  将应用<xref:System.AddIn.Pipeline.AddInAdapterAttribute>属性为`CalculatorViewToContractAddInSideAdapter`类，它标识为外接程序端适配器。  
  
9. 请`CalculatorViewToContractAddInSideAdapter`类继承<xref:System.AddIn.Pipeline.ContractBase>，它提供的默认实现<xref:System.AddIn.Contract.IContract>接口，并实现协定接口，将管道`ICalc1Contract`。  
  
10. 添加公共构造函数接受`ICalculator`，将其缓存在私有字段中，并调用基类构造函数。  
  
11. 若要实现的成员`ICalc1Contract`，只需调用的对应成员`ICalculator`实例传递给构造函数中，并返回结果。 这可适应视图 (`ICalculator`) 到协定 (`ICalc1Contract`)。  
  
     下面的代码显示了已完成-的外接程序端适配器。  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. （可选） 构建的 Visual Studio 解决方案。  
  
## <a name="creating-the-host-side-adapter"></a>创建主机端适配器  
 此宿主端适配器由一个约定到视图适配器组成。 此段调整到外接程序的宿主视图的约定。  
  
 在此管道中外, 接程序提供了一项服务对主机和类型流从外接程序向主机。 由于没有类型流向从宿主向外接程序，您无需包括视图到约定适配器。  
  
 若要实现生存期管理，请使用<xref:System.AddIn.Pipeline.ContractHandle>要附加到该协定的生存期标记对象。 为了使生命期管理工作，必须保留对此句柄的引用。 应用令牌后，无需任何其他编程需要，因为它们不再使用，并使它们可用于垃圾回收时外, 接程序系统可以释放的对象。 有关详细信息，请参阅[生存期管理](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5)。  
  
#### <a name="to-create-the-host-side-adapter"></a>若要创建的主机端适配器  
  
1.  添加一个名为的新项目`Calc1HostSideAdapter`到`CalculatorV1`解决方案。 使该项目基于**类库**模板。  
  
2.  在中**解决方案资源管理器**，将引用添加到以下程序集到`Calc1HostSideAdapter`项目：  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  添加相邻的段的项目到项目引用：  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  选择每个项目引用，然后在**属性**设置**Copy Local**到**False**。 在 Visual Basic 中，使用**引用**选项卡**项目属性**若要设置**复制本地**到**False**为两个项目的引用。  
  
5.  重命名项目的默认类`CalculatorContractToViewHostSideAdapter`。  
  
6.  在类文件中，添加对命名空间引用<xref:System.AddIn.Pipeline>。  
  
7.  在类文件中，添加相邻的段的命名空间引用：`CalcHVAs`和`CalculatorContracts`。 (在 Visual Basic 中的这些命名空间引用`Calc1HVA.CalcHVAs`和`Calc1Contract.CalculatorContracts`，除非是关闭 Visual Basic 项目中的默认命名空间。)  
  
8.  将应用<xref:System.AddIn.Pipeline.HostAdapterAttribute>属性为`CalculatorContractToViewHostSideAdapter`类，以将标识为主机端适配器段。  
  
9. 请`CalculatorContractToViewHostSideAdapter`类实现表示外接程序的宿主视图的接口： `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator`在 Visual Basic 中)。  
  
10. 添加公共构造函数接受管道协定类型， `ICalc1Contract`。 构造函数必须缓存对该协定的引用。 它还必须创建并缓存新<xref:System.AddIn.Pipeline.ContractHandle>对于协定，若要管理的外接程序的生存期。  
  
    > [!IMPORTANT]
    >  <xref:System.AddIn.Pipeline.ContractHandle>生命期管理至关重要。 如果您不能保持对引用<xref:System.AddIn.Pipeline.ContractHandle>对象，垃圾回收将回收，且当您的程序不需要管道将关闭。 这可能会导致难以进行诊断，如错误<xref:System.AppDomainUnloadedException>。 关闭是管道的生活中，一个正常阶段，因此没有生存期管理代码来检测这种情况是管道的错误的方法。  
  
11. 若要实现的成员`ICalculator`，只需调用的对应成员`ICalc1Contract`实例传递给构造函数中，并返回结果。 这可适应协定 (`ICalc1Contract`) 到视图 (`ICalculator`)。  
  
     下面的代码显示了已完成的宿主端适配器。  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. （可选） 构建的 Visual Studio 解决方案。  
  
## <a name="creating-the-host"></a>创建主机  
 主机应用程序与外接程序通过外接程序的宿主视图进行交互。 它使用外接程序发现和激活方法提供<xref:System.AddIn.Hosting.AddInStore>和<xref:System.AddIn.Hosting.AddInToken>类来执行以下操作：  
  
-   更新管道和外接程序信息的缓存。  
  
-   查找宿主视图类型的加载项`ICalculator`，指定的管道根目录下。  
  
-   提示用户指定的外接程序才能使用。  
  
-   激活的所选外接程序中具有指定的安全信任级别的新应用程序域。  
  
-   运行自定义`RunCalculator`方法，其调用指定的外接程序的宿主视图的外接程序的方法。  
  
#### <a name="to-create-the-host"></a>若要创建的主机  
  
1.  添加一个名为的新项目`Calc1Host`到`CalculatorV1`解决方案。 使该项目基于**控制台应用程序**模板。  
  
2.  在中**解决方案资源管理器**，添加到 System.AddIn.dll 程序集的引用`Calc1Host`项目。  
  
3.  添加到项目引用`Calc1HVA`项目。 选择该项目引用，然后在**属性**设置**Copy Local**到**False**。 在 Visual Basic 中，使用**引用**选项卡**项目属性**若要设置**复制本地**到**False**。  
  
4.  重命名类文件 （在 Visual Basic 中的模块） `MathHost1`。  
  
5.  在 Visual Basic 中，使用**应用程序**选项卡**项目属性**对话框来设置**启动对象**到**Sub Main**。  
  
6.  在类或模块文件中，添加对的命名空间引用<xref:System.AddIn.Hosting>。  
  
7.  在类或模块文件中，添加外接程序的宿主视图的命名空间引用： `CalcHVAs`。 (在 Visual Basic 中为此命名空间引用`Calc1HVA.CalcHVAs`，除非是关闭 Visual Basic 项目中的默认命名空间。)  
  
8.  在中**解决方案资源管理器**，选择的解决方案和从**项目**菜单中，选择**属性**。 在中**解决方案属性页**对话框中，将**单启动项目**为此主机应用程序项目。  
  
9. 在类或模块文件中，使用<xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType>方法来更新缓存。 使用<xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType>方法以获取一系列令牌，并使用<xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType>方法，以激活外接程序。  
  
     下面的代码显示了完整的宿主应用程序。  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  此代码假定管道文件夹结构位于应用程序文件夹。 如果它位于其他位置，更改的设置的代码行`addInRoot`变量，以使该变量包含管线目录结构的路径。  
  
     该代码使用`ChooseCalculator`方法来列出标记，并提示用户选择外接程序。 `RunCalculator`方法提示用户提供简单的数学表达式中，将使用的表达式分析`Parser`类，并显示返回的结果外接程序。  
  
10. （可选） 构建的 Visual Studio 解决方案。  
  
## <a name="creating-the-add-in"></a>创建的外接程序  
 外接程序实现外接程序视图所指定的方法。 该外接程序实现`Add`， `Subtract`， `Multiply`，和`Divide`操作并将结果返回到主机。  
  
#### <a name="to-create-the-add-in"></a>若要创建外接程序  
  
1.  添加一个名为的新项目`AddInCalcV1`到`CalculatorV1`解决方案。 使该项目基于**类库**模板。  
  
2.  在中**解决方案资源管理器**，向项目添加 System.AddIn.dll 程序集的引用。  
  
3.  添加到项目引用`Calc1AddInView`项目。 选择该项目引用，然后在**属性**，请设置**Copy Local**到**False**。 在 Visual Basic 中，使用**引用**选项卡**项目属性**若要设置**复制本地**到**False**项目引用。  
  
4.  将类重命名`AddInCalcV1`。  
  
5.  在类文件添加到的命名空间引用<xref:System.AddIn>和外接程序视图段： `CalcAddInViews` (`Calc1AddInView.CalcAddInViews`在 Visual Basic 中)。  
  
6.  将应用<xref:System.AddIn.AddInAttribute>属性为`AddInCalcV1`类中，以将类标识为外接程序。  
  
7.  请`AddInCalcV1`类实现该接口表示外接程序视图： `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator`在 Visual Basic 中)。  
  
8.  实现的成员`ICalculator`通过返回相应的计算结果。  
  
     下面的代码显示了已完成加载项。  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. （可选） 构建的 Visual Studio 解决方案。  
  
## <a name="deploying-the-pipeline"></a>部署管道  
 现在您就可以构建并部署到所需的管线目录结构的外接程序段。  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a>若要将段部署到管道  
  
1.  对于解决方案中每个项目，使用**构建**选项卡**项目属性**(**编译**选项卡，在 Visual Basic 中的) 设置的值**输出路径** (**生成输出路径**在 Visual Basic 中)。 如果名为你的应用程序文件夹`MyApp`，例如，你的项目将生成到以下文件夹：  
  
    |项目|路径|  
    |-------------|----------|  
    |AddInCalcV1|MyApp\Pipeline\AddIns\CalcV1|  
    |Calc1AddInSideAdapter|MyApp\Pipeline\AddInSideAdapters|  
    |Calc1AddInView|MyApp\Pipeline\AddInViews|  
    |Calc1Contract|MyApp\Pipeline\Contracts|  
    |Calc1Host|MyApp|  
    |Calc1HostSideAdapter|MyApp\Pipeline\HostSideAdapters|  
    |Calc1HVA|MyApp|  
  
    > [!NOTE]
    >  如果您决定将您的管道文件夹结构中应用程序文件夹之外的位置，则必须修改相应地在表中所示的路径。 请参阅中的管道目录要求的讨论[管线开发要求](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。  
  
2.  生成 Visual Studio 解决方案。  
  
3.  检查应用程序和管道目录，以确保程序集已复制到正确的目录，并在错误的文件夹已安装的程序集没有额外的副本。  
  
    > [!NOTE]
    >  如果未更改**Copy Local**到**False**有关`Calc1AddInView`项目中的引用`AddInCalcV1`项目中，加载程序上下文的问题将使外接程序无法位于。  
  
     有关如何部署到管道的信息，请参阅[管线开发要求](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。  
  
## <a name="running-the-host-application"></a>运行主机应用程序  
 现在您就可以运行宿主和外接程序与之交互。  
  
#### <a name="to-run-the-host-application"></a>若要运行主机应用程序  
  
1.  在命令提示符处，转到应用程序目录并运行主机应用程序， `Calc1Host.exe`。  
  
2.  主机查找所有可用的插件的其类型，并提示您选择外接程序。 输入**1** for 仅可用外接程序。  
  
3.  为计算器，如输入等式**2 + 2**。 必须有数字和运算符之间的空格。  
  
4.  类型**退出**然后按**Enter**键关闭该应用程序。  
  
## <a name="see-also"></a>请参阅  
 [演练： 启用向后的兼容性作为在宿主发生变化](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [演练： 在宿主和外接程序之间传递集合](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [管线开发要求](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [协定、 视图和适配器](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [管道开发](../../../docs/framework/add-ins/pipeline-development.md)
