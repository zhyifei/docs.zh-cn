---
title: XAML 的集合类型
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 63f6346837f77dbdbdcb4a90ec5af725be69ee02
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364336"
---
# <a name="collections-and-collection-types-for-xaml"></a>XAML 的集合类型

本主题介绍如何定义用于支持集合的类型的属性, 以及如何支持 XAML 语法, 以便将收集项作为父对象元素或属性元素的子元素进行实例化。

## <a name="xaml-collection-concepts"></a>XAML 集合概念

从概念上讲, XAML 中有多个子项在 XAML 对象元素或 XAML 属性元素范围内的任何关系必须作为集合实现。 该集合必须与作为该关系中的父级的 XAML 类型的特定 XAML 属性相关联。 属性必须是集合, 因为 XAML 处理器需要将标记中的每个项分配为支持集合属性的新添加项。

在 XAML 语言级别, 未完全定义集合支持的确切要求。 集合可以是列表或字典 (但不是两者) 的概念是在 XAML 语言级别定义的, 但哪些后备类型表示列表或字典不是由 XAML 语言定义的。

在 .NET Framework XAML 服务中, XAML 集合支持的概念在 .NET Framework 支持类型方面更清晰地定义。 具体而言, 对集合的 XAML 支持基于多个 .NET Framework 概念和 Api, 这些概念和 Api 一般 .NET Framework 编程中用于列表和字典。

1. <xref:System.Collections.IList>接口指示列表集合。

2. <xref:System.Collections.IDictionary>接口指示字典集合。

3. <xref:System.Array>表示一个数组, 数组支持<xref:System.Collections.IList>方法。

在上述每个集合概念中, .NET Framework xaml 服务 xaml 处理器都需要对集合`Add`属性的类型的特定实例调用方法。 或者, 在序列化方案中, XAML 处理器会根据 "Items" 的每个集合的特定概念, 为列表、字典或数组中找到的每个项生成离散的 XAML 类型实例。 这些是: <xref:System.Collections.IList.Item%2A>;<xref:System.Array.System%23Collections%23IList%23Item%2A> ;的<xref:System.Array>显式。 <xref:System.Collections.IDictionary.Item%2A>

## <a name="generic-collections"></a>泛型集合

泛型集合可用于常规 .NET Framework 编程, 还可用于 XAML 集合属性。 但 .NET Framework XAML 服务 xaml <xref:System.Collections.Generic.IList%601>处理器<xref:System.Collections.Generic.IDictionary%602>不会将泛型接口和视为等效于非泛型<xref:System.Collections.IList>或<xref:System.Collections.IDictionary>。 对于泛型集合属性类型, 建议的方法是从类<xref:System.Collections.Generic.List%601>或<xref:System.Collections.Generic.Dictionary%602>派生, 而不是实现接口。 这些类实现非泛型接口, 因此在基实现中包含 XAML 集合的预期支持。

## <a name="read-only-collections-and-initialization-logic"></a>只读集合和初始化逻辑

在 .NET Framework 编程中, 它是一种常见的设计模式, 用于将集合的值保存为只读集合。 此模式允许拥有集合属性的实例更好地控制对集合执行的操作。 具体而言, 该模式通过设置属性来防止意外替换现有的全部集合。 在此模式中, 调用方对集合的任何访问都应该通过调用集合类型和/或相关集合接口 (如) <xref:System.Collections.IList>所支持的方法或属性来进行。

使用此模式意味着公开只读集合属性的任何类必须首先初始化该属性以保存空集合。 通常, 在类的构造行为中执行初始化。 若要对 XAML 有用, 这一点很重要, 无参数的构造函数始终引用此类逻辑, 因为 XAML 通常在处理属性 (集合属性或其他) 之前调用无参数的构造函数。

## <a name="xaml-type-system-support-and-collections"></a>XAML 类型系统支持和集合

除了分析 XAML 和填充或序列化集合属性的基本机制外, XAML 类型系统在 .NET Framework XAML 服务中实现的功能包括多个与 XAML 中的集合相关的设计功能。

1. <xref:System.Xaml.XamlType.IsCollection%2A>如果 XAML 类型受提供 XAML 集合支持的类型的支持, 则返回 true。

2. <xref:System.Xaml.XamlType.IsDictionary%2A>和<xref:System.Xaml.XamlType.IsArray%2A>可以进一步确定 XAML 类型支持的收集模式。 对于基于 .NET Framework xaml 服务和 XAML 类型系统, 但不基于现有<xref:System.Xaml.XamlWriter>实现的自定义 XAML 处理器, 知道使用哪种收集模式可能是必需的, 以便知道要调用哪个方法。集合处理。

3. 前面的每个属性值都可能会受到 XAML 类型<xref:System.Xaml.XamlType.LookupCollectionKind%2A>上的重写影响。
