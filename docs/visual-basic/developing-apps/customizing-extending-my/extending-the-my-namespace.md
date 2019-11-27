---
title: 扩展 My 命名空间
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 2a7b0b84061fccd9a333a68e4a19477bd19ca4ff
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330317"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>扩展中的 `My` 命名空间 Visual Basic

Visual Basic 中的 `My` 命名空间公开了一些属性和方法，使你能够轻松利用 .NET Framework 的强大功能。 `My` 命名空间简化了常见编程问题，通常会将很难的任务减少到单个代码行。 此外，`My` 命名空间是完全可扩展的，因此您可以自定义 `My` 的行为，并向其层次结构中添加新服务以适应特定的应用程序需求。 本主题讨论如何自定义 `My` 命名空间的现有成员以及如何将您自己的自定义类添加到 `My` 命名空间。

## <a name="customizing-existing-my-namespace-members"></a>自定义现有 `My` 命名空间成员

Visual Basic 中的 `My` 命名空间公开有关您的应用程序、您的计算机等的常用信息。 有关 `My` 命名空间中的对象的完整列表，请参阅[我的参考](../../language-reference/keywords/my-reference.md)。 您可能必须自定义 `My` 命名空间的现有成员，使其更适合您的应用程序的需求。 不是只读的 `My` 命名空间中的对象的任何属性都可以设置为自定义值。

例如，假设你经常使用 `My.User` 对象来访问运行应用程序的用户的当前安全上下文。 但是，公司使用自定义用户对象为公司内的用户公开附加信息和功能。 在这种情况下，你可以将 `My.User.CurrentPrincipal` 属性的默认值替换为你自己的自定义主体对象的实例，如以下示例中所示：

[!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]

设置 `My.User` 对象的 `CurrentPrincipal` 属性将更改运行应用程序时所用的标识。 然后，`My.User` 对象将返回有关新指定用户的信息。
  
## <a name="adding-members-to-my-objects"></a>将成员添加到 `My` 对象

从 `My.Application` 和 `My.Computer` 返回的类型定义为 `Partial` 类。 因此，可以通过创建一个名为 `MyApplication` 或 `MyComputer`的 `Partial` 类来扩展 `My.Application` 和 `My.Computer` 对象。 类不能是 `Private` 类。 如果将类指定为 `My` 命名空间的一部分，则可以添加将包含在 `My.Application` 或 `My.Computer` 对象中的属性和方法。

下面的示例将名为 `DnsServerIPAddresses` 的属性添加到 `My.Computer` 对象：

[!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]

## <a name="adding-custom-objects-to-the-my-namespace"></a>将自定义对象添加到 `My` 命名空间

尽管 `My` 命名空间为许多常见编程任务提供了解决方案，但你可能会遇到 `My` 命名空间未解决的任务。 例如，你的应用程序可能会访问用户数据的自定义目录服务，或者你的应用程序可能会使用默认情况下未安装 Visual Basic 的程序集。 您可以扩展 `My` 命名空间，以包含特定于您的环境的常见任务的自定义解决方案。 可以轻松扩展 `My` 命名空间，以添加新成员以满足不断增长的应用程序需求。 此外，还可以将 `My` 命名空间扩展部署到作为 Visual Basic 模板的其他开发人员。
  
### <a name="adding-members-to-the-my-namespace"></a>将成员添加到 `My` 命名空间

由于 `My` 是像任何其他命名空间一样的命名空间，因此可以通过只添加模块并指定 `My`的 `Namespace`，将顶级属性添加到该命名空间。 用 `HideModuleName` 特性批注模块，如下面的示例中所示。 `HideModuleName` 属性可确保 IntelliSense 在显示 `My` 命名空间的成员时不显示模块名称。

[!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]

若要将成员添加到 `My` 命名空间，请根据需要将属性添加到模块。 对于添加到 `My` 命名空间的每个属性，添加类型为 `ThreadSafeObjectProvider(Of T)`的私有字段，其中类型是自定义属性返回的类型。 此字段用于创建由属性返回的线程安全对象实例，方法是调用 `GetInstance` 方法。 因此，访问扩展属性的每个线程都接收其自己的返回类型的实例。 下面的示例将名为 `SampleExtension` `SampleExtension` 的属性添加到 `My` 命名空间的类型：

[!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]

## <a name="adding-events-to-custom-my-objects"></a>向自定义 `My` 对象添加事件

您可以使用 `My.Application` 对象通过在 `My` 命名空间中扩展 `MyApplication` 分部类来公开您的自定义 `My` 对象的事件。 对于基于 Windows 的项目，您可以在**解决方案资源管理器**中双击项目的 "**我的项目**" 节点。 在 Visual Basic**项目设计器**中，单击 "**应用程序**" 选项卡，然后单击 "**查看应用程序事件**" 按钮。 将创建一个名为*applicationevents.vb*的新文件。 它包含以下用于扩展 `MyApplication` 类的代码：

[!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]

通过向 `MyApplication` 类添加自定义事件处理程序，可以为自定义 `My` 对象添加事件处理程序。 自定义事件使你可以添加将在添加、删除事件处理程序或引发事件时执行的代码。 请注意，仅当用户添加代码以处理事件时，才会运行自定义事件的 `AddHandler` 代码。 例如，请考虑上一节中的 `SampleExtension` 对象具有要为其添加自定义事件处理程序的 `Load` 事件。 下面的代码示例演示一个名为 `SampleExtensionLoad` 的自定义事件处理程序，该处理程序在 `My.SampleExtension.Load` 事件发生时调用。 添加代码以处理新的 `My.SampleExtensionLoad` 事件时，将执行此自定义事件代码的 `AddHandler` 部分。 代码示例中包含 `MyApplication_SampleExtensionLoad` 方法，以显示处理 `My.SampleExtensionLoad` 事件的事件处理程序的示例。 请注意，在编辑*applicationevents.vb*文件时，如果在代码编辑器上方的左侧下拉列表中选择 "**我的应用程序事件**" 选项，则 `SampleExtensionLoad` 事件将可用。

[!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]

## <a name="design-guidelines"></a>设计准则

开发 `My` 命名空间的扩展时，请使用以下准则来帮助最大程度地减少扩展组件的维护成本：

- **仅包含扩展逻辑。** `My` 命名空间扩展中包含的逻辑只应包含在 `My` 命名空间中公开所需功能所需的代码。 由于你的扩展将作为源代码驻留在用户项目中，因此更新扩展组件会产生较高的维护成本，应尽可能避免使用。
- **最小化项目假设。** 当你创建 `My` 命名空间的扩展时，请不要采用一组引用、项目级别导入或特定编译器设置（例如，`Option Strict` off）。 相反，请使用 `Global` 关键字来最大程度地降低依赖关系，并完全限定所有类型引用。 此外，请确保该扩展与 `Option Strict` 一起编译，以最大程度地减少扩展中的错误。
- **隔离扩展代码。** 将代码放在一个单独的文件中，可以轻松地将扩展部署为 Visual Studio 项模板。 有关详细信息，请参阅本主题后面的 "打包和部署扩展"。 将所有 `My` 命名空间扩展代码置于项目中的单个文件或单独的文件夹中时，还将帮助用户找到 `My` 命名空间扩展。

## <a name="designing-class-libraries-for-my"></a>为 `My` 设计类库

与大多数对象模型一样，某些设计模式适用于 `My` 命名空间，而其他设计模式则不适用。 设计 `My` 命名空间的扩展时，请考虑以下原则：

- **无状态方法。** `My` 命名空间中的方法应为特定的任务提供完整的解决方案。 确保传递给方法的参数值提供完成特定任务所需的所有输入。 避免创建依赖于先前状态的方法，例如打开与资源的连接。
- **全局实例。** `My` 命名空间中维护的唯一状态是项目的全局状态。 例如，`My.Application.Info` 封装在整个应用程序中共享的状态。
- **简单参数类型。** 避免使用复杂的参数类型，使其保持简单。 而是创建不采用参数输入或采用简单输入类型（如字符串、基元类型等）的方法。
- **工厂方法。** 某些类型一定要实例化。 提供工厂方法作为 `My` 命名空间的扩展，使你能够更轻松地发现和使用属于此类别的类型。 `My.Computer.FileSystem.OpenTextFileReader`的工厂方法的示例。 .NET Framework 中有几种可用的流类型。 通过具体指定文本文件，`OpenTextFileReader` 可帮助用户了解要使用的流。

这些准则不排除类库的一般设计原则。 相反，它们是针对使用 Visual Basic 和 `My` 命名空间的开发人员进行了优化的建议。 有关创建类库的一般设计原则，请参阅[框架设计准则](../../../standard/design-guidelines/index.md)。

## <a name="packaging-and-deploying-extensions"></a>打包和部署扩展

你可以在 Visual Studio 项目模板中包含 `My` 命名空间扩展，也可以打包扩展并将其部署为 Visual Studio 项模板。 将 `My` 命名空间扩展打包为 Visual Studio 项模板时，可以利用 Visual Basic 提供的其他功能。 通过这些功能，您可以在项目引用特定程序集时包含扩展，或使用户能够通过使用 Visual Basic 项目设计器的 "**我的扩展**" 页显式添加您的 `My` 命名空间扩展。

有关如何部署 `My` 命名空间扩展的详细信息，请参阅[打包和部署自定义 My 扩展](packaging-and-deploying-custom-my-extensions.md)。

## <a name="see-also"></a>另请参阅

- [打包和部署自定义 My 扩展](packaging-and-deploying-custom-my-extensions.md)
- [扩展 Visual Basic 应用程序模型](extending-the-visual-basic-application-model.md)
- [自定义 My 中可用的对象](customizing-which-objects-are-available-in-my.md)
- [“项目设计器”->“My 扩展”页](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [“项目设计器”->“应用程序”页 (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Partial](../../language-reference/modifiers/partial.md)
