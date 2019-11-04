---
title: XamlName 语法
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: a39d25f03583ab9020878b7a659bc99489231ff9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458884"
---
# <a name="xamlname-grammar"></a>XamlName 语法
XamlName 语法是在 XAML 语言规范 [MS-CHAP] 中定义的一种特定语法，此处将在此处重现此语法。  
  
## <a name="from-the-xaml-specification"></a>从 XAML 规范  
 [MS-CHAP] 规范定义语法 XamlName，用于标识用于类型和属性的合法符号标识符集。  
  
 XamlName 类型的字符串值必须符合以下语法：  
  
```xaml  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 它假定 Unicode 字符数据库中定义的以下常规类别值  

| Unicode 类别   | 描述                   |
|--------------------|-------------------------------|
| Lu                 | 字母，大写             |
| Ll                 | 字母，小写             |
| Lt                 | 字母，首字母大写             |
| Lm                 | 字母，修饰符              |
| Lo                 | 字母，其他                 |
| Mn                 | 标记，非间距             |
| Mc                 | 标记，间距组合       |
| Nd                 | Number、Decimal               |
| Nl                 | 数字，字母                |
 
 XAML 定义了第二个语法 DottedXamlName，用于属性和事件限定引用，还用于附加成员。 有关详细信息，请参阅 <xref:System.Windows.DependencyProperty> 和[XAML 概述（WPF）](../../desktop-wpf/fundamentals/xaml.md)。  
  
 DottedXamlName 类型的字符串值必须符合以下语法：  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>备注  
 有关完整规范，请参阅[\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525)。
