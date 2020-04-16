---
title: XAML 安全注意事项
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: 1864910b339c74e3033fb4d6d8baebffada1a4f8
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432916"
---
# <a name="xaml-security-considerations"></a>XAML 安全注意事项

本文介绍了在使用 XAML 和 .NET XAML 服务 API 时应用程序中安全性的最佳做法。

## <a name="untrusted-xaml-in-applications"></a>应用程序中的不受信任的 XAML

在最一般意义上，不受信任的 XAML 是应用程序未具体包含或发出的任何 XAML 源。

编译到受信任和签名程序集中的`resx`-类型资源或存储为 -类型的 XAML 本质上不受信任。 您可以像信任整个程序集一样信任 XAML。 在大多数情况下，您只关心松散的 XAML 的信任方面，这是从流或其他 I/O 加载的 XAML 源。 松散 XAML 不是具有部署和打包基础结构的应用程序模型的特定组件或功能。 但是，程序集可能实现涉及加载松散 XAML 的行为。

对于不受信任的 XAML，通常应该将其视为不受信任的代码。 使用沙盒或其他隐喻来防止可能不受信任的 XAML 访问受信任的代码。

XAML 功能的性质使 XAML 有权构造对象并设置其属性。 这些功能还包括访问类型转换器、映射和访问应用程序域中的程序集，使用标记扩展、`x:Code`块等。

除了语言级功能外，XAML 还用于许多技术的 UI 定义。 加载不受信任的 XAML 可能意味着加载恶意欺骗 UI。

## <a name="sharing-context-between-readers-and-writers"></a>读者和作者之间共享上下文

.NET XAML 服务体系结构适用于 XAML 读取器和 XAML 编写器，通常需要将 XAML 读取器共享给 XAML 编写器或共享 XAML 架构上下文。 如果要编写 XAML 节点循环逻辑或提供自定义保存路径，则可能需要共享对象或上下文。 不要在受信任的代码和不受信任的代码之间共享 XAML 读取器实例、非默认 XAML 架构上下文或 XAML 读取器/写入器类的设置。

大多数涉及基于 CLR 的类型备份的 XAML 对象写入的方案和操作都只能使用默认的 XAML 架构上下文。 默认 XAML 架构上下文没有明确包含可能危及完全信任的设置。 因此，在受信任的和不受信任的 XAML 读取器/写入器组件之间共享上下文是安全的。 但是，如果您这样做，最好还是将这些读者和作者保存在单独的<xref:System.AppDomain>作用域中，其中一个专门打算/沙盒用于部分信任。

## <a name="xaml-namespaces-and-assembly-trust"></a>XAML 命名空间和程序集信任

XAML 如何将自定义 XAML 命名空间映射解释为程序集的基本限定语法和定义不会区分加载到应用程序域中的受信任程序集和不受信任的程序集。 因此，从技术上讲，不受信任的程序集可以欺骗受信任的程序集的预期 XAML 命名空间映射并捕获 XAML 源声明的对象和属性信息。 如果您有安全要求以避免这种情况，则应使用以下技术之一进行预期的 XAML 命名空间映射：

- 在应用程序的 XAML 进行的任何 XAML 命名空间映射中使用具有强名称的完全限定程序集名称。

- 通过构造特定于 XAML 读取器和 XAML<xref:System.Xaml.XamlSchemaContext>对象编写器的程序集映射，将程序集映射限制为一组固定的引用程序集。 请参阅 <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>。

## <a name="xaml-type-mapping-and-type-system-access"></a>XAML 类型映射和类型系统访问

XAML 支持其自己的类型系统，在许多方面，该系统是 CLR 如何实现基本 CLR 类型系统的对等体。 但是，对于类型感知的某些方面，如果您根据类型信息对类型做出信任决策，则应服从 CLR 支持类型中的类型信息。 这是因为 XAML 类型系统的一些特定报告功能作为虚拟方法处于打开状态，因此并不完全受原始 .NET XAML 服务实现的控制。 存在这些扩展点是因为 XAML 类型系统是可扩展的，以匹配 XAML 本身的可扩展性及其可能的替代类型映射策略与默认 CLR 支持的实现和默认 XAML 架构上下文。 有关详细信息，请参阅 有关<xref:System.Xaml.XamlType>和<xref:System.Xaml.XamlMember>的几种属性的特定注释。

## <a name="see-also"></a>请参阅

- <xref:System.Xaml.Permissions.XamlAccessLevel>
