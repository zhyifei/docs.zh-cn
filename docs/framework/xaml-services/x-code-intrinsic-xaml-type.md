---
title: "x:Code 内部 XAML 类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: "19"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d39249a5d1c0e230d21e6d889b92d0b57c98e2ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xcode-intrinsic-xaml-type"></a>x:Code 内部 XAML 类型
允许在 XAML 生产的代码的放置位置。 也可以由任何编译 XAML，也可以由运行时留在更高版本使用 如解释在 XAML 生产的 XAML 处理器实现编译此类代码。  
  
## <a name="xaml-object-element-usage"></a>XAML 对象元素用法  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>备注  
 中的代码内`x:Code`XAML 指令元素是仍然解释在常规 XML 命名空间中提供的 XAML 命名空间。 因此，它是通常需将代码用于括`x:Code`内`CDATA`段。  
  
 `x:Code`不是允许的 XAML 生成的所有可能的部署机制。 在特定框架 (如 WPF) 必须编译代码。 在其他框架，`x:Code`可能通常不允许使用情况。  
  
 对于允许托管的框架`x:Code`内容，正确的语言编译器用于`x:Code`内容由设置和用于编译应用程序的包含项目的目标。  
  
## <a name="wpf-usage-notes"></a>WPF 用法说明  
 中声明的代码`x:Code`WPF 有几个值得注意的限制：  
  
-   `x:Code`指令元素必须在 XAML 生产的根元素的直接子元素。  
  
-   [X:class 指令](../../../docs/framework/xaml-services/x-class-directive.md)必须提供父根元素上。  
  
-   代码放在`x:Code`将被视为编译已针对该 XAML 页正在创建的分部类的作用域内。 因此你定义的所有代码必须都是该分部类的成员或变量。  
  
-   不能定义其他类，而非由嵌套在分部类的类 （允许嵌套，但它并不是典型因为嵌套的类不能在 XAML 中引用）。 无法定义或添加到用于现有的分部类的命名空间之外的 CLR 命名空间。  
  
-   必须完全限定所有对代码的分部类的 CLR 命名空间之外的实体的引用。 如果所声明的成员的分部类可重写成员的替代，这必须使用特定于语言的重写关键字指定。 如果在声明成员`x:Code`作用域与从 XAML 创建的分部类的成员冲突，因此的方式，则编译器将报告冲突时，XAML 文件无法编译或加载。  
  
## <a name="see-also"></a>请参阅  
 [x:Class 指令](../../../docs/framework/xaml-services/x-class-directive.md)  
 [WPF 中的代码隐藏和 XAML](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [XAML 概述 (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
