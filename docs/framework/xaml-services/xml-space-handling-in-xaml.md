---
title: "XAML 中的 xml:space 处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b8356cdb47b6b834e8d9a6bb84b26445af6d865
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xmlspace-handling-in-xaml"></a>XAML 中的 xml:space 处理
`xml:space`属性是一个声明对象元素内的有意义的空白处理行为的 XML 定义属性。 此行为是相关的所有内容 （内部文本） 元素中包含其中`xml:space`声明，并且范围给子元素。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- 或 -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>备注  
 定义`xml:space`包括其两个可能值的 XAML 中的特性派生自`xml:space`由 W3C XML 规范定义的"特殊特性"。  
  
 默认值`xml:space`属性为文本值`"default"`。 值`"default"`，或者如果`xml:space`根本未指定，有意义的空白分析的行为是默认的处理，如主题中定义[在 XAML 中的空白处理](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)。  
  
 若要保留在对象元素内容中的空格，请指定`xml:space="preserve"`该的对象元素上。  
  
 在大多数解释下`xml:space`属性效果和属性的值的作用域为子元素。  
  
 有关 XAML 中的空白处理的完整讨论，请参阅[在 XAML 中的空白处理](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)。  
  
## <a name="see-also"></a>请参阅  
 [XAML 中的空白处理](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [XAML 概述 (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
