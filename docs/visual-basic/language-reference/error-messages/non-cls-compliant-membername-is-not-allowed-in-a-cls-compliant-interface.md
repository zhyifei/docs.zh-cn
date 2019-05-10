---
title: 在符合 CLS 的接口中不允许出现不符合 CLS 的 <membername>
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: 68e1fb4f55d9f9b140f1b54cfde2bc5f60952dd2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592128"
---
# <a name="non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a>不符合 CLS 符合\<成员名称 > 符合 cls 的接口中不允许出现
属性、 过程或接口中的事件标记为`<CLSCompliant(True)>`时是接口本身标记为`<CLSCompliant(False)>`或未标记。  
  
 接口不能符合[语言独立性和与语言无关的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)，其所有成员都必须合规。  
  
 当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。 此参数没有默认值，必须为其提供一个值。  
  
 如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC40033  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 如果你需要 CLS 符合性以及对接口的源代码控制，将标记该接口作为`<CLSCompliant(True)>`如果是符合的所有成员。  
  
- 如果你需要 CLS 符合性，并且不能控制接口源代码，或者它不会不限制为符合规范，定义此成员内使用不同的接口。  
  
- 如果你需要此成员保持其当前的界面中，删除<xref:System.CLSCompliantAttribute>从其定义或将其标记为`<CLSCompliant(False)>`。  
  
## <a name="see-also"></a>请参阅

- [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)
