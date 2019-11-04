---
title: XAML 中的 xml:space 处理
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458803"
---
# <a name="xmlspace-handling-in-xaml"></a>XAML 中的 xml:space 处理
`xml:space` 特性是一个 XML 定义的特性，用于声明对象元素内的有效空白处理行为。 此行为与在其中声明了 `xml:space` 的元素中包含的所有内容（内部文本）有关，并且还适用于子元素。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- 或 -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>备注  
 XAML 中的 `xml:space` 属性（包括其两个可能的值）的定义是从定义为 "特殊特性" 的 `xml:space` 派生的，由 W3C for XML 规范定义。  
  
 `xml:space` 属性的默认值为 `"default"`的文本值。 对于 `"default"`的值，或者，如果根本没有指示 `xml:space`，则有效的空白分析的行为是默认处理，如在[XAML 中的空白处理](whitespace-processing-in-xaml.md)中定义的那样。  
  
 若要保留对象元素内容中的空格，请在该对象元素上指定 `xml:space="preserve"`。  
  
 在大多数解释下，属性的 `xml:space` 属性效果和属性值的作用域为子元素。  
  
 有关 XAML 中的空白处理的完整讨论，请参阅[xaml 中的空白处理](whitespace-processing-in-xaml.md)。  
  
## <a name="see-also"></a>请参阅

- [XAML 中的空白处理](whitespace-processing-in-xaml.md)
- [XAML 概述 (WPF)](../../desktop-wpf/fundamentals/xaml.md)
