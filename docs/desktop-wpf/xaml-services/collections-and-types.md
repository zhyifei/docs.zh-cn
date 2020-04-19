---
title: XAML 的集合类型
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 2ec58026c605df31489c8aab4c4cc714dab11474
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "81432580"
---
# <a name="collections-and-collection-types-for-xaml"></a>XAML 的收集类型

本文介绍如何定义旨在支持集合的类型的属性，并支持 XAML 语法，以便将集合项实例化为父对象元素或属性元素的元素子级。

## <a name="xaml-collection-concepts"></a>XAML 收集概念

从概念上讲，XAML 中任何在 XAML 对象元素或 XAML 属性元素范围内有多个子项的关系都必须作为集合实现。 该集合必须与 XAML 类型的特定 XAML 属性相关联，该属性是该关系中的父级。 属性必须是集合，因为 XAML 处理器希望将标记中的每个项分配为备份集合属性的新添加项。

在 XAML 语言级别，收集支持的确切要求尚未完全定义。 集合可以是列表或字典（但不能同时两者）的概念在 XAML 语言级别定义，但哪些支持类型表示列表或字典不是由 XAML 语言定义的。

在 .NET XAML 服务中，XAML 集合支持的概念在 .NET 支持类型方面定义得更清晰。 具体来说，XAML 对集合的支持基于几个 .NET 概念和 API，这些概念和 API 用于一般列表和字典 .NET 编程。

1. 接口<xref:System.Collections.IList>指示列表集合。

2. 接口<xref:System.Collections.IDictionary>指示字典集合。

3. <xref:System.Array>表示数组，数组支持<xref:System.Collections.IList>方法。

在这些集合概念中，.NET XAML 服务 XAML 处理器期望在`Add`集合属性类型的特定实例上调用 该方法。 或者，在序列化方案中，XAML 处理器根据每个集合的特定概念"Item"为每个在列表、字典或数组中找到的每个项生成离散的 XAML 类型实例。 这些项目是： <xref:System.Collections.IList.Item%2A?displayProperty=nameWithType><xref:System.Collections.IDictionary.Item%2A?displayProperty=nameWithType>;的显式<xref:System.Array.System%23Collections%23IList%23Item%2A?displayProperty=nameWithType>。 <xref:System.Array>

## <a name="generic-collections"></a>通用集合

泛型集合可用于常规 .NET 编程，也可用于 XAML 集合属性。 但是，泛型接口<xref:System.Collections.Generic.IList%601>和<xref:System.Collections.Generic.IDictionary%602>.NET XAML 服务 XAML 处理器未标识为等效于非泛<xref:System.Collections.IList>型<xref:System.Collections.IDictionary>或 。 泛型集合属性类型的推荐方法是从类<xref:System.Collections.Generic.List%601>或<xref:System.Collections.Generic.Dictionary%602>派生，而不是实现接口。 这些类实现非泛型接口，从而在基本实现中包括对 XAML 集合的预期支持。

## <a name="read-only-collections-and-initialization-logic"></a>只读集合和初始化逻辑

在 .NET 编程中，将保存集合值的任何属性作为只读集合，是一种常见的设计模式。 此模式允许拥有集合属性的实例更好地控制集合发生的情况。 具体而言，该模式通过设置属性防止意外替换整个预先存在的集合。 在此模式中，调用方对集合的任何访问都应该通过调用集合类型和/或相关集合接口（如<xref:System.Collections.IList>） 支持的方法或属性进行。

使用此模式意味着公开只读集合属性的任何类必须首先初始化该属性以容纳空集合。 通常，初始化是作为类构造行为的一部分执行的。 为了对 XAML 有用，无参数构造函数始终引用此类逻辑非常重要，因为 XAML 在处理属性（集合属性或其他）之前通常调用无参数构造函数。

## <a name="xaml-type-system-support-and-collections"></a>XAML 类型系统支持和集合

除了解析 XAML 和填充或序列化集合属性的基本机制外，.NET XAML 服务中实现的 XAML 类型系统还包括与 XAML 中的集合相关的多个设计功能。

1. <xref:System.Xaml.XamlType.IsCollection%2A>如果 XAML 类型由提供 XAML 集合支持的类型支持，则返回 true。

2. <xref:System.Xaml.XamlType.IsDictionary%2A>并<xref:System.Xaml.XamlType.IsArray%2A>可以进一步识别 XAML 类型支持的集合模式。 对于基于 .NET XAML 服务和 XAML 类型系统但不基于现有<xref:System.Xaml.XamlWriter>实现的自定义 XAML 处理器，可能需要了解使用哪种收集模式，以便知道要调用哪种方法来进行收集处理。

3. 以前的每个属性值都可能受 XAML 类型的<xref:System.Xaml.XamlType.LookupCollectionKind%2A>重写的影响。
