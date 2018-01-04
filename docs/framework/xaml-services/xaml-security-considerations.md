---
title: "XAML 安全注意事项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
caps.latest.revision: "7"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b58719f36cd911497c5cd892610330688221e7ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-security-considerations"></a>XAML 安全注意事项
本主题介绍在应用程序中的安全性的最佳做法，当你使用 XAML 和.NET Framework XAML 服务 API。  
  
## <a name="untrusted-xaml-in-applications"></a>在应用程序中不受信任的 XAML  
 在最常规的意义上，不受信任的 XAML 是你的应用程序不是专门未包括或发出的任何 XAML 源。  
  
 XAML 是编译为或存储为`resx`-在受信任和签名的程序集内的类型资源不是本质上是不受信任。 根据你信任的程序集作为一个整体，可以信任 XAML。 在大多数情况下，你是仅关心宽松 XAML，即从流或其他 IO 加载的 XAML 源的信任方面。 宽松型 XAML 不是特定的组件或功能的应用程序模型进行部署和打包基础结构。 但是，程序集可能会实施涉及加载松散的 XAML 的行为。  
  
 对于不受信任的 XAML，应将其通常相同就像它是不受信任的代码。 使用沙盒或其他形式以防止可能不受信任的 XAML 访问受信任的代码。  
  
 XAML 功能的性质提供 XAML 构造对象并设置其属性的权限。 这些功能还包括访问映射和访问应用程序域中中的程序集使用标记扩展的类型转换器`x:Code`块，依次类推。  
  
 除其语言级别功能，XAML 用于在许多技术的用户界面定义。 加载不受信任的 XAML 可能意味着加载恶意的欺骗 UI。  
  
## <a name="sharing-context-between-readers-and-writers"></a>读取器和编写器之间共享上下文  
 XAML 读取器和 XAML 编写器的.NET Framework XAML 服务体系结构通常需要共享到 XAML 编写器或共享的 XAML 架构上下文的 XAML 读取器。 如果你正在编写 XAML 节点循环逻辑，或提供自定义保存路径可能需要共享的对象或上下文。 不应共享 XAML 读取器实例、 默认 XAML 架构上下文或设置受信任和不受信任的代码之间的 XAML 读取器/编写器类。  
  
 大多数方案和涉及 XAML 对象编写的基于 CLR 的类型支持的操作可以只使用默认 XAML 架构上下文。 默认 XAML 架构上下文不显式包括可能会危害完全信任的设置。 因此，它可安全地共享受信任和不受信任的 XAML 读取器/编写器组件之间的上下文。 但是，如果执行此操作时，它仍是最佳做法要保留在单独的此类的读取器和编写<xref:System.AppDomain>范围，其中一个专用于/进行沙盒处理以部分信任。  
  
## <a name="xaml-namespaces-and-assembly-trust"></a>XAML 命名空间和程序集信任  
 基本的非限定的语法和有关 XAML 如何解释程序集的自定义 XAML 命名空间映射的定义不区分作为加载到应用程序域的受信任和不受信任程序集。 因此，它是从技术上讲可能的不受信任的程序集，以欺骗受信任的程序集的预期的 XAML 命名空间映射和捕获的 XAML 源的声明的对象和属性信息。 如果你有安全需求，从而避免这种情况下，应使用以下方法之一进行你预期的 XAML 命名空间映射：  
  
-   具有强名称由应用程序的 XAML 任何 XAML 命名空间映射中使用完全限定程序集的名称。  
  
-   限制将映射到一组固定的引用程序集，通过构造特定的程序集<xref:System.Xaml.XamlSchemaContext>XAML 读取器和 XAML 对象编写器。 请参阅 <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>。  
  
## <a name="xaml-type-mapping-and-type-system-access"></a>XAML 类型映射和类型系统访问  
 XAML 支持其自己的类型系统，即在许多方面与 CLR 如何实现基本的 CLR 类型系统对等。 但是，做出信任决定有关基于其类型信息的类型的类型识别的某些方面，你应延迟到 CLR 后备类型中的类型信息。 这是因为某些 XAML 类型系统的特定报表功能保持打开状态作为虚拟方法，因此，不完全受控制的原始的.NET Framework XAML 服务实现。 这些扩展点存在，因为 XAML 类型系统是可扩展的以便与 XAML 本身的扩展性与默认 CLR 支持实现与默认 XAML 架构上下文其可能备用类型映射策略相匹配。 有关详细信息，请参阅 》 上几个属性的特定注释<xref:System.Xaml.XamlType>和<xref:System.Xaml.XamlMember>。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Xaml.Permissions.XamlAccessLevel>
