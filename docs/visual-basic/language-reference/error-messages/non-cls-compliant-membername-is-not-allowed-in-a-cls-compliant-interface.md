---
title: "不符合 CLS 符合&lt;membername&gt;符合 cls 的接口中不允许"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords: BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74744b89ad72b6fd051f83ba38354d0a277555c8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>不符合 CLS 符合&lt;membername&gt;符合 cls 的接口中不允许
属性、 过程或接口中的事件被标记为`<CLSCompliant(True)>`接口本身时被标记为`<CLSCompliant(False)>`或未标记。  
  
 接口不能符合[语言独立性和独立于语言的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)，其所有成员必须都是合规的。  
  
 当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。 此参数没有默认值，必须为其提供一个值。  
  
 如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC40033  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果你需要 CLS 遵从性，并且可以控制接口源代码，将标记为接口`<CLSCompliant(True)>`是否符合其所有成员。  
  
-   如果你需要 CLS 符合性而不能控制接口源代码，或者不将其限制为符合，定义此成员在不同的接口。  
  
-   如果你需要此成员保留在其当前的接口，删除<xref:System.CLSCompliantAttribute>从其定义或将其标记为`<CLSCompliant(False)>`。  
  
## <a name="see-also"></a>请参阅  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
 
