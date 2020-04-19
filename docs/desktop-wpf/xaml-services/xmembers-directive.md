---
title: x:Members 指令
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: c751a4f1cdea8dce7ef5165f5225ab3a825c7344
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432724"
---
# <a name="xmembers-directive"></a>x:Members 指令
保存在标记中定义的一组成员，该成员适用于父元素的 x：类。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object x:Class="className">
<x:Members>
  oneOrMoreMembers
</x:Members
</object>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|`className`|XAML 生产的备用类或分部类的名称。 请参阅“备注”。|
|`oneOrMoreMembers`|表示成员定义的一个或多个对象元素。 通常，这些是`x:Property`对象元素。 请参阅“备注”。|

## <a name="remarks"></a>备注

在 .NET XAML 服务实现中，没有 支持`x:Members`类或基础成员实现。 `x:Members`是可作为任何类型的成员存在的特殊 XAML 成员。 在 XAML 节点流`x:Members`中，从 XAML 语言 XAML 命名空间中表示为名为`Members`的成员。 该成员`Members`包含`Member`对象的只读泛型列表。 在典型的标记中，单个成员被指定为`x:Property`属性元素。 `x:Property`是专门针对类型属性的更精确的类型，可分配给`x:Member`。 有关详细信息，请参阅[x：属性指令](xproperty-directive.md)。

若要支持将 `x:Members` 实际用作一种在标记中指定成员定义的方法，成员必须与可修改的类相关联。 预期模型是 `x:Members` 作为指定 `x:Class` 的类型的成员存在。 但是，在 .NET XAML 服务级别不支持关联类型和成员或生成动态成员定义的机制。 此功能由具有支持 XAML 的成员定义的应用程序模型的单个框架实现。 通常，需要 MSBUILD 生成操来支持此功能，这些操作以标记编译 XAML 并将其与隐藏代码相集成或者从 XMAL 生成纯程序集。

## <a name="xmembers-for-windows-workflow-foundation"></a>x：Windows 工作流基础的成员

对于 Windows 工作流`x:Members`基础，包含完全以 XAML 或 XAML — 定义具有代码后面的活动设计器的动态成员组成的自定义活动的成员。 此外，必须在 XAML 生产的根元素上指定 `x:Class`。 这不是 .NET XAML 服务级别的要求，但当支持自定义活动和 Windows 工作流基础 XAML 的 MSBUILD 生成操作加载 XAML 生产时，这将成为一项要求。 `x:Members`必须是声明 的对象元素标记中的第一个子元素`x:Class`。
