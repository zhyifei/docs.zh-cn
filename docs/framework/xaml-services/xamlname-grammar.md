---
title: "XamlName 语法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 92327c8ff6232e64bf8b6b2a9d78e4a9eb30f3e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="xamlname-grammar"></a>XamlName 语法
XamlName 语法是 XAML 语言规范 [MS-XAML]，这将为方便起见在此处重现中定义特定语法。  
  
## <a name="from-the-xaml-specification"></a>从 XAML 规范  
 [MS-XAML] 规范定义的语法 XamlName 来识别用于类型和属性的合法符号标识符的集。  
  
 字符串值的类型 XamlName 必须符合以下语法：  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 在 Unicode 字符数据库中定义，这假定以下常规类别值  
  
```  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 XAML 定义第二个语法，DottedXamlName，用于属性和事件限定的引用，并还附加成员。 有关详细信息，请参阅<xref:System.Windows.DependencyProperty>和[XAML 概述 (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)。  
  
 字符串值的类型 DottedXamlName 必须符合以下语法：  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>备注  
 有关完整规范，请参阅[ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525)。
