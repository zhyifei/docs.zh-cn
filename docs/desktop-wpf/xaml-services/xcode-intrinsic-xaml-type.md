---
title: x:Code 内部 XAML 类型
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 4da72ed630c1df001e3fd6c7e55f866b94c4d9b1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432802"
---
# <a name="xcode-intrinsic-xaml-type"></a>x:Code 内部 XAML 类型
允许在 XAML 生产中放置代码。 此类代码可以由编译 XAML 的任何 XAML 处理器实现编译，也可以保留在 XAML 生产中供以后使用，例如运行时的解释。

## <a name="xaml-object-element-usage"></a>XAML 对象元素用法

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a>备注

`x:Code` XAML 指令元素中的代码仍在常规 XML 命名空间和提供的 XAML 命名空间中解释。 因此，通常需要将用于段`x:Code`内的代码封闭。 `CDATA`

`x:Code`不允许 XAML 生产的所有可能部署机制。 在特定框架（例如 WPF）中，必须编译代码。 在其他框架中，`x:Code`通常可能不允许使用。

对于允许托管`x:Code`内容的框架，用于`x:Code`内容的正确语言编译器由用于编译应用程序的包含项目的设置和目标确定。

## <a name="wpf-usage-notes"></a>WPF 用法说明

`x:Code`为 WPF 声明的代码有几个值得注意的限制：

- 指令`x:Code`元素必须是 XAML 生产根元素的即时子元素。

- [x：类指令](xclass-directive.md)必须在父根元素上提供。

- 将位于其中`x:Code`的代码通过编译处理为已为该 XAML 页创建的部分类的范围。 因此，您定义的所有代码都必须是该部分类的成员或变量。

- 除了在部分类中嵌套类（允许嵌套，但它不是典型的，因为嵌套类无法在 XAML 中引用），因此无法定义其他类。 不能定义或添加到现有部分类的命名空间以外的 CLR 命名空间。

- 对部分类 CLR 命名空间外的代码实体的引用都必须完全限定。 如果声明的成员是覆盖到部分类重写成员，则必须使用特定于语言的重写关键字指定此参数。 如果在作用域中`x:Code`声明的成员与从 XAML 创建的部分类的成员发生冲突，编译器报告冲突的方式，XAML 文件无法编译或加载。

## <a name="see-also"></a>请参阅

- [x:Class 指令](xclass-directive.md)
- [WPF 中的代码隐藏和 XAML](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [XAML 概述 (WPF)](../fundamentals/xaml.md)
