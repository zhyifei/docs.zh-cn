---
title: 扩展 Visual Basic 中的 My 命名空间
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 25fff04b19cce299a2d437e662fb7481153d29da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>扩展 Visual Basic 中的 My 命名空间
`My`在 Visual Basic 中的命名空间公开属性和方法，您可以轻松地利用.NET Framework 的功能。 `My`命名空间简化了常见的编程问题，通常可一行代码将一个困难的任务。 此外， `My` ，以便你可以自定义的行为，命名空间是完全可扩展`My`并将新的服务添加到其层次结构，从而满足特定应用程序需求。 本主题将讨论如何自定义的现有成员`My`命名空间以及如何将添加到你自己自定义类`My`命名空间。  
  
 **主题内容**  
  
-   [自定义现有我 Namespace 成员](#customizing)  
  
-   [将成员添加到 My 对象](#addingtoobjects)  
  
-   [自定义将对象添加到我 Namespace](#addingcustom)  
  
-   [将成员添加到我 Namespace](#addingtonamespace)  
  
-   [将事件添加到自定义 My 对象](#addingevents)  
  
-   [设计准则](#design)  
  
-   [设计的类库我](#designing)  
  
-   [打包和部署扩展](#packaging)  
  
##  <a name="customizing"></a>自定义现有我 Namespace 成员  
 `My`命名空间中 Visual Basic 公开经常使用你的应用程序、 你的计算机，和的详细信息。 有关中的对象的完整列表`My`命名空间，请参阅[我引用](../../../visual-basic/language-reference/keywords/my-reference.md)。 你可能需要自定义的现有成员`My`命名空间，以便它们更好地匹配你的应用程序的需求。 中的某个对象的任何属性`My`命名空间不是只读的可以将设置为自定义值。  
  
 例如，假定您经常使用`My.User`对象来访问运行你的应用程序的用户的当前安全上下文。 但是，你的公司使用自定义用户对象公开的其他信息和公司中的用户的功能。 在此方案中，你可以将默认值的`My.User.CurrentPrincipal`与你自己自定义的主体对象，如下面的示例中所示的实例的属性。  
  
 [!code-vb[VbVbcnExtendingMy#1](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_1.vb)]  
  
 设置`CurrentPrincipal`属性`My.User`对象更改在其下运行应用程序的标识。 `My.User`对象，反过来，返回有关新指定的用户的信息。  
  
##  <a name="addingtoobjects"></a>将成员添加到 My 对象  
 从返回的类型`My.Application`和`My.Computer`定义为`Partial`类。 因此，你可以扩展`My.Application`和`My.Computer`对象通过创建`Partial`类名为`MyApplication`或`MyComputer`。 类不能为`Private`类。 如果您指定类的一部分`My`命名空间，你可以添加属性和方法将附带`My.Application`或`My.Computer`对象。  
  
 例如，下面的示例添加名为的属性`DnsServerIPAddresses`到`My.Computer`对象。  
  
 [!code-vb[VbVbcnExtendingMy#2](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_2.vb)]  
  
##  <a name="addingcustom"></a>自定义将对象添加到我 Namespace  
 尽管`My`命名空间提供对于许多常见编程任务的解决方案，你可能会遇到任务，`My`命名空间不能解决。 例如，你的应用程序可能会访问用户数据的自定义目录服务或应用程序可能会使用未安装默认情况下，使用 Visual Basic 的程序集。 你可以扩展`My`命名空间以包含自定义解决方案的常见任务的特定于你的环境。 `My`命名空间可以轻松地进行扩展以添加新成员，以满足不断增长的应用程序需求。 此外，你可以部署你`My`给其他开发人员为 Visual Basic 模板的命名空间扩展。  
  
###  <a name="addingtonamespace"></a>将成员添加到我 Namespace  
 因为`My`是命名空间像任何其他命名空间，你可以顶级属性向其添加只需添加一个模块，并指定`Namespace`的`My`。 批注的模块`HideModuleName`特性，如以下示例所示。 `HideModuleName`特性可确保显示的成员时，IntelliSense 将不显示模块名称`My`命名空间。  
  
 [!code-vb[VbVbcnExtendingMy#3](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_3.vb)]  
  
 将成员添加到`My`命名空间，根据需要向模块添加属性。 每个属性添加到`My`命名空间中，添加类型的私有字段`ThreadSafeObjectProvider(Of T)`，其中的类型是返回自定义属性的类型。 使用此字段来创建线程安全对象实例返回的属性，通过调用`GetInstance`方法。 因此，每个线程访问扩展的属性接收自己的返回类型的实例。 下面的示例添加名为的属性`SampleExtension`类型`SampleExtension`到`My`命名空间：  
  
 [!code-vb[VbVbcnExtendingMy#4](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_4.vb)]  
  
##  <a name="addingevents"></a>将事件添加到自定义 My 对象  
 你可以使用`My.Application`对象来公开您的自定义事件`My`通过扩展的对象`MyApplication`中的分部类`My`命名空间。 对于基于 Windows 的项目，你可以双击**我的项目**中为你的项目中的节点**解决方案资源管理器**。 在 Visual Basic 中**项目设计器**，单击`Application`选项卡，然后单击`View Application Events`按钮。 将创建名为 ApplicationEvents.vb 一个新文件。 它包含以下代码用于扩展`MyApplication`类。  
  
 [!code-vb[VbVbcnExtendingMy#5](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_5.vb)]  
  
 你可以为您的自定义添加事件处理程序`My`对象添加到的自定义事件处理程序`MyApplication`类。 自定义事件，可以添加将在事件处理程序添加、 删除或引发该事件时执行的代码。 请注意，`AddHandler`代码用于自定义事件而添加了对事件进行处理的用户代码的情况下，才会运行。 例如，考虑，`SampleExtension`前一部分中的对象具有`Load`你想要添加的自定义事件处理程序的事件。 下面的代码示例演示一个名为的自定义事件处理程序`SampleExtensionLoad`将时调用`My.SampleExtension.Load`事件发生。 当添加代码以处理新`My.SampleExtensionLoad`事件，`AddHandler`执行此自定义事件代码的一部分。 `MyApplication_SampleExtensionLoad`方法包含在代码示例中显示的事件处理程序处理的示例`My.SampleExtensionLoad`事件。 请注意，`SampleExtensionLoad`选择时，将可事件**我的应用程序事件**在左侧的下拉列表在代码编辑器上方时编辑 ApplicationEvents.vb 文件的选项。  
  
 [!code-vb[VbVbcnExtendingMy#6](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_6.vb)]  
  
##  <a name="design"></a>设计准则  
 当你开发扩展`My`命名空间，使用以下准则来帮助你扩展组件的维护成本降到最低。  
  
-   **包括仅扩展逻辑。** 中包含的逻辑`My`命名空间扩展应包括仅公开中所需的功能所需的代码`My`命名空间。 因为你的扩展将驻留在用户项目中以源代码的形式，更新扩展组件会产生高昂的维护成本，并且应尽可能避免。  
  
-   **最小化项目假设。** 当你创建你的扩展的`My`命名空间，不会假定一组引用，项目级导入或特定的编译器设置 (例如，`Option Strict`关闭)。 相反，最小化依赖项和完全限定使用的所有类型引用`Global`关键字。 此外，请确保使用编译扩展`Option Strict`在为了尽量减少在扩展中的错误。  
  
-   **隔离的扩展代码。** 将代码放置在单个文件可以与 Visual Studio 项模板可以方便地部署你的扩展。 有关详细信息，请参阅本主题后面的"打包和部署扩展"。 放置所有`My`单个文件中的命名空间扩展代码或单独的文件夹在项目中还有助于用户查找`My`命名空间扩展。  
  
##  <a name="designing"></a>设计的类库我  
 对于大多数对象模型的情况一样，一些设计模式适用于`My`命名空间和其他不这样做。 设计的扩展时`My`命名空间，请考虑以下原则：  
  
-   **无状态方法。** 中的方法`My`命名空间应提供特定任务的完整解决方案。 确保传递给方法的参数值提供完成特定任务所需的所有输入。 避免创建依赖于以前的状态，如对资源的打开连接的方法。  
  
-   **全局实例。** 在中维护的唯一状态`My`命名空间是全局性的项目。 例如，`My.Application.Info`封装在整个应用程序共享的状态。  
  
-   **简单的参数类型。** 为简单起见通过避免复杂的参数类型。 相反，创建不采用输入任何参数的方法或它们采用简单的输入的类型，如字符串、 基元类型和等等。  
  
-   **工厂方法。** 某些类型会实例化一定困难。 提供工厂方法为扩展`My`命名空间，可更轻松地发现并使用属于此类别的类型。 可以有效地工作的工厂方法的一个示例是`My.Computer.FileSystem.OpenTextFileReader`。 有几种流类型在.NET Framework 中可用。 通过指定文本文件，具体而言，`OpenTextFileReader`可帮助用户了解要使用的流。  
  
 这些指南不会阻止类库的常规设计原则。 相反，它们是针对开发人员正在使用 Visual Basic 进行了优化的建议和`My`命名空间。 有关用于创建类库的常规设计原则，请参阅[Framework 设计准则](../../../standard/design-guidelines/index.md)。  
  
##  <a name="packaging"></a>打包和部署扩展  
 可以包括`My`在 Visual Studio 项目模板，或你的命名空间扩展可以打包你的扩展，并将它们部署为 Visual Studio 项模板。 当包你`My`与 Visual Studio 项模板的命名空间扩展，你可以充分利用所提供的 Visual Basic 的其他功能。 这些功能使您能够时项目引用特定程序集，包含扩展或启用用户显式添加你`My`使用的命名空间扩展**My 扩展**Visual Basic 的页项目设计器。  
  
 有关如何部署的详细信息`My`命名空间的扩展，请参阅[打包和部署自定义 My 扩展](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)。  
  
## <a name="see-also"></a>另请参阅  
 [打包和部署自定义 My 扩展](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)  
 [扩展 Visual Basic 应用程序模型](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 [自定义 My 中可用的对象](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [My 扩展页，项目设计器](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)  
 [“项目设计器”->“应用程序”页 (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [Partial](../../../visual-basic/language-reference/modifiers/partial.md)
