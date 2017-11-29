---
title: "XAML 的集合类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
caps.latest.revision: "2"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 991360433b5fb09c13e59f63be94e0fa0ec94b61
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="collections-and-collection-types-for-xaml"></a>XAML 的集合类型
本主题介绍如何定义旨在支持一个集合，并以用于实例化作为元素的父对象元素或属性元素的子级的收集项的支持 XAML 语法的类型的属性。  
  
## <a name="xaml-collection-concepts"></a>XAML 集合概念  
 从概念上讲，任何在 XAML 中有多个范围中的 XAML 对象元素的子项或 XAML 属性元素必须以集合形式实现关系。 该集合必须与为该关系中的父级的 XAML 类型的特定 XAML 属性相关联。 属性必须是一个集合，因为 XAML 处理器需要分配标记为新添加的项的支持集合属性中的每个项。  
  
 在 XAML 语言级别，集合支持的精确要求未完全定义。 在 XAML 语言级别，定义一个集合可以是要么列表或字典 （但不是两者） 的概念，但后备类型表示任一列表或字典不由 XAML 语言定义。  
  
 在.NET Framework XAML 服务中，根据后备类型的.NET Framework 更清楚地定义 XAML 集合支持的概念。 具体而言，对集合的 XAML 支持基于多个.NET Framework 概念和对于列表和字典常规.NET Framework 编程中的使用的 Api。  
  
1.  <xref:System.Collections.IList>接口指示列表集合。  
  
2.  <xref:System.Collections.IDictionary>接口指示 dicionary 集合。  
  
3.  <xref:System.Array>表示一个数组，以及数组支持<xref:System.Collections.IList>方法。  
  
 在每个这些集合概念，.NET Framework XAML 服务 XAML 处理器需要调用`Add`集合属性的类型的特定实例上的方法。 或者，在序列化方案中，XAML 处理器生成的每个项列表、 字典或基于每个集合的特定概念"项"数组中找到的离散 XAML 类型实例。 这些是： <xref:System.Collections.IList.Item%2A>;<xref:System.Collections.IDictionary.Item%2A>; 显式<xref:System.Array.System%23Collections%23IList%23Item%2A>为<xref:System.Array>。  
  
## <a name="generic-collections"></a>泛型集合  
 泛型集合可用于常规.NET Framework 编程，并还可以用于 XAML 集合属性。 但是，泛型接口<xref:System.Collections.Generic.IList%601>和<xref:System.Collections.Generic.IDictionary%602>不识别的视为等效于非泛型的.NET Framework XAML 服务 XAML 处理器<xref:System.Collections.IList>或<xref:System.Collections.IDictionary>。 建议的泛型集合属性类型的方法是派生自类而不是实现接口，<xref:System.Collections.Generic.List%601>或<xref:System.Collections.Generic.Dictionary%602>。 这些类实现非泛型接口，并因此在基实现中包括 XAML 集合的预期的支持。  
  
## <a name="read-only-collections-and-initialization-logic"></a>只读集合和初始化逻辑  
 在.NET Framework 编程中，很常见的设计模式，以使保存集合为只读集合的值的任何属性。 此模式允许拥有实例的集合会发生什么情况的更好地控制的集合属性... 具体而言，模式通过将属性设置阻止意外替换整个预先存在的收集。 在此模式中，对由调用方集合的任何访问而是应将通过调用方法或属性，如支持的集合类型和/或相关的集合接口<xref:System.Collections.IList>。  
  
 使用此模式意味着任何公开的只读集合属性的类必须先初始化该属性以存放空集合。 通常初始化类的构造行为的一部分执行。 对 XAML 人员很有用，很重要，这种逻辑始终引用默认构造函数，因为 XAML 通常调用默认构造函数之前处理属性 (集合属性或其他)。  
  
## <a name="xaml-type-system-support-and-collections"></a>XAML 类型系统支持和集合  
 超出的分析 XAML 和填充或序列化集合的属性的基本机制，在.NET Framework XAML 服务中实现的 XAML 类型系统包括了一些设计功能，适用于 XAML 中的集合。  
  
1.  <xref:System.Xaml.XamlType.IsCollection%2A>如果 XAML 类型由提供 XAML 集合支持的类型，，返回 true。  
  
2.  <xref:System.Xaml.XamlType.IsDictionary%2A>和<xref:System.Xaml.XamlType.IsArray%2A>进一步可以识别的 XAML 类型支持哪些集合模式。 自定义 xaml 处理器基于.NET Framework XAML 服务和 XAML 类型系统，但不是基于现有<xref:System.Xaml.XamlWriter>实现中，了解所使用的集合模式可能有必要才能知道要为调用的方法集合处理。  
  
3.  每个以前的属性值可能受的重写<xref:System.Xaml.XamlType.LookupCollectionKind%2A>XAML 类型上。
