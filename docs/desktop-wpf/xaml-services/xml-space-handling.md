---
title: XAML 中的 xml:space 处理
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432700"
---
# <a name="xmlspace-handling-in-xaml"></a>XAML 中的 xml:space 处理

该`xml:space`属性是一个 XML 定义的属性，用于声明对象元素中的重要空白处理行为。 此行为与声明元素`xml:space`中包含的所有内容（内部文本）以及子元素的范围相关。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object xml:space="preserve" />
```

 \- 或 -

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a>备注

XAML`xml:space`中属性的定义包括其两个可能的值，由`xml:space`W3C XML 规范定义为"特殊属性"。

属性的`xml:space`默认值是文本值`"default"`。 对于值`"default"`，或者如果`xml:space`根本不指示，则重要的空白分析行为是默认处理，如[XAML 中的主题白空间处理中](white-space-processing.md)定义的默认处理。

要在对象元素内容中保留空白，请在`xml:space="preserve"`该对象元素上指定。

在大多数解释下，`xml:space`属性效果和属性的值范围限定为子元素。

有关 XAML 中空白处理的完整讨论，请参阅[XAML 中的空白处理](white-space-processing.md)。

## <a name="see-also"></a>请参阅

- [XAML 中的空白处理](white-space-processing.md)
- [XAML 概述 (WPF)](../fundamentals/xaml.md)
